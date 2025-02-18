>*Artificial intelligence was used to dynamically allocate furniture and other elements from the 3D scene into a dynamic scene [229]. It is concluded that the use of these techniques allowed a better use of the 3D environment, with the arrangement of elements starting from an environment with only walls and floors.*


python ..\scripts\colmap2nerf.py --video_in tracyd\Room_Video.mp4 --video_fps 2 --run_colmap --overwrite

---

在虚拟现实 (VR) 环境中，注视点 (Fixation) 的确定通常不是直接由眼动追踪设备直接提供的原始数据，而是需要通过对眼部注视位置和停留时间的分析计算得出的。这一过程涉及从眼动追踪设备收集的原始数据中提取有意义的信息，并通过特定的分析方法来识别用户的注视行为。

### 如何确定注视点

注视点的确定通常需要以下步骤和数据处理：

#### 1. **收集原始眼动追踪数据**
- **眼动追踪设备**提供的基本数据通常包括：
  - **Gaze Point Coordinates (视线坐标)**：这是用户眼睛注视的屏幕或空间中的点，通常是二维或三维坐标。
  - **Gaze Direction (视线方向)**：用户眼睛注视的方向，通常表示为一个向量。
  - **Timestamps (时间戳)**：每个眼动数据点的记录时间。
  - **Pupil Size (瞳孔大小)**：反映认知负荷的生理指标。

#### 2. **分析眼动数据以确定注视点**
- 注视点的识别通常依赖于以下分析：
  - **空间稳定性**：在连续的时间窗口中，如果视线坐标在空间上的变动小于某个阈值（如1°视角或屏幕上的一定像素距离），这段时间内的视线点可以被认为是一次注视。
  - **时间阈值**：只有当视线在一个小区域内稳定注视超过一个最小时间阈值（通常是 100-200 毫秒）时，该区域才被判断为注视点。

#### 3. **计算注视点**
- 使用滑动窗口技术计算注视点：
  - **窗口内稳定性**：在滑动窗口中，如果所有的视线点都在第一个点的一个小邻域内，这个窗口对应的时间段内的视线可以被认为是注视。
  - **提取注视中心**：窗口内的视线点的中心或平均点通常被记录为注视点的坐标。

### 示例：注视点计算

以下是一个简单的示例，展示如何使用 Python 处理眼动数据来计算注视点。这个过程在实际应用中通常需要根据具体设备和数据格式调整：

```python
import numpy as np

# 示例数据：时间戳，视线点 X 坐标，视线点 Y 坐标
timestamps = np.array([0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1.0])
gaze_points_x = np.array([100, 102, 103, 101, 100, 250, 249, 251, 248, 247, 249])
gaze_points_y = np.array([200, 202, 201, 203, 205, 300, 299, 301, 298, 297, 295])

# 设置空间和时间阈值
space_threshold = 5  # 像素
time_threshold = 0.2  # 秒

# 计算注视点
fixations = []
start = 0

while start < len(timestamps):
    end = start
    while end < len(timestamps) and (timestamps[end] - timestamps[start] < time_threshold):
        if np.max(np.abs(gaze_points_x[start:end+1] - gaze_points_x[start])) > space_threshold or \
           np.max(np.abs(gaze_points_y[start:end+1] - gaze_points_y[start])) > space_threshold:
            break
        end += 1
    
    # 如果当前窗口是一个有效的注视
    if end - start > 1 and (timestamps[end - 1] - timestamps[start]) >= time_threshold:
        fixation_x = np.mean(gaze_points_x[start:end])
        fixation_y = np.mean(gaze_points_y[start:end])
        fixations.append((fixation_x, fixation_y))
    
    start += 1

print("Identified Fixations:", fixations)
```

### 在 Unity 中处理注视点

在 Unity 中，你可以按照类似的逻辑处理从眼动追踪设备获取的数据。以下是一个基本框架，展示如何在 Unity 脚本中处理这些数据：

```csharp
using System.Collections.Generic;
using UnityEngine;

public class GazeAnalysis : MonoBehaviour {
    // 假设这是从眼动追踪设备接收的视线点数据
    List<Vector2> gazePoints = new List<Vector2>();
    List<float> timestamps = new List<float>();

    // 空间和时间阈值
    float spaceThreshold = 5.0f; // 像素
    float timeThreshold = 0.2f; // 秒

    void Update() {
        // 假设有一个方法来更新视线点数据
        UpdateGazeData();

        // 计算注视点
        List<Vector2> fixations = CalculateFixations(gazePoints, timestamps, spaceThreshold, timeThreshold);
        foreach (var fixation in fixations) {
            // 在 Unity 中可视化注视点
            Debug.DrawRay(Camera.main.ScreenToWorldPoint(new Vector3(fixation.x, fixation.y, Camera.main.nearClipPlane)), Vector3.forward, Color.red, 2.0f);
        }
    }

    List<Vector2> CalculateFixations(List<Vector2> gazePoints, List<float> timestamps, float spaceThreshold, float timeThreshold) {
        List<Vector2> fixations = new List<Vector2>();
        int start = 0;
        
        while (start < gazePoints.Count) {
            int end = start;
            while (end < gazePoints.Count && (timestamps[end] - timestamps[start] < timeThreshold)) {
                if ((gazePoints[start] - gazePoints[end]).magnitude > spaceThreshold) {
                    break;
                }
                end++;
            }

            if (end - start > 1 && (timestamps[end - 1] - timestamps[start]) >= time_threshold) {
                Vector2 fixationPoint = Vector2.zero;
                for (int i = start; i < end; i++) {
                    fixationPoint += gazePoints[i];
                }
                fixationPoint /= (end - start);
                fixations.Add(fixationPoint);
            }

            start = end;
        }

        return fixations;
    }

    void UpdateGazeData() {
        // 更新视线数据，这里只是一个示意，具体实现应根据设备 SDK 调整
        Vector2 newGazePoint = new Vector2(Input.mousePosition.x, Input.mousePosition.y);
        gazePoints.Add(newGazePoint);
        timestamps.Add(Time.time);
    }
}
```

### 总结

注视点的确定是一个基于眼动追踪数据的分析过程，需要通过识别用户视线在时间和空间上的稳定性来完成。这一过程不仅提供了用户视觉注意的深入视角，而且是理解用户行为和设计优化用户界面的重要工具。在 VR 环境中，这种分析尤其关键，因为它可以直接影响到用户体验和界面设计的有效性。
---
要在虚拟现实 (VR) 环境中结合使用 Unity 和 VR 设备来完成头部和眼部数据的过滤，并分析用户行为，你可以遵循以下步骤和方法。这些方法涵盖了数据收集、过滤、分析，以及利用 AI 工具来增强行为检测和分析的准确性。

### 1. **设置 Unity 和 VR 环境**

首先，确保你的 Unity 环境配置了适合 VR 开发的插件和设置，例如使用 Unity XR 插件框架，以及配置相应的 VR 设备支持。

- **安装和配置 Unity XR 插件**：
  - 在 Unity 中，通过 **Window > Package Manager**，安装如 **XR Plugin Management** 和对应的设备插件（如 Oculus, OpenVR, Windows Mixed Reality 等）。

- **设置 XR Rig**：
  - 在 Unity 中，添加一个 **XR Rig** 对象（如使用预制体 Prefabs），这代表玩家的 VR 环境设置。
  - 确保 **XR Rig** 包括 **Camera** 和 **Trackers** 以追踪头部和手部位置。

### 2. **数据收集：头部和眼动追踪**

利用 Unity 的 XR 接口和相应的 SDK 来收集头部位置、头部转向以及眼动数据。

- **头部位置和转向**：
  - 使用 Unity 的 **InputTracking** 或 XRNode 类来获得头部的实时位置和旋转。
  
  ```csharp
  using UnityEngine;
  using UnityEngine.XR;

  public class HeadTracking : MonoBehaviour {
      void Update() {
          // 获取头部位置和旋转
          Vector3 headPosition = InputTracking.GetLocalPosition(XRNode.Head);
          Quaternion headRotation = InputTracking.GetLocalRotation(XRNode.Head);

          Debug.Log("Head Position: " + headPosition);
          Debug.Log("Head Rotation: " + headRotation);
      }
  }
  ```

- **眼动追踪**：
  - 如果使用支持眼动追踪的设备（如 HTC Vive Pro Eye），可以通过设备的 SDK 获取眼动数据。
  - 对于 Oculus 设备，可以使用 Oculus Integration 包中的 `OVRInput` 类。

  ```csharp
  using UnityEngine;
  using UnityEngine.XR;

  public class EyeTracking : MonoBehaviour {
      void Update() {
          // 假设使用 Oculus 的眼动追踪
          if (OVRInput.IsControllerConnected(OVRInput.Controller.LTouch)) {
              Vector3 gazeDirection = OVRInput.GetLocalControllerPosition(OVRInput.Controller.LTouch);
              Debug.Log("Gaze Direction: " + gazeDirection);
          }
      }
  }
  ```

### 3. **数据过滤：忽略界面交互影响**

为了过滤掉用户在交互界面上的视线和头部数据，你可以定义界面元素的区域，并在数据处理时排除这些区域。

- **定义界面元素区域**：
  - 在 Unity 中，为所有 UI 元素（如 Canvas 下的 Buttons, Panels 等）计算屏幕空间的边界。
  - 利用摄像机的视角将这些边界转换为视线射线可识别的空间。

  ```csharp
  using UnityEngine;

  public class UIElementBounds : MonoBehaviour {
      public RectTransform uiElement;

      void Start() {
          // 计算 RectTransform 的屏幕空间边界
          Rect rect = RectTransformUtility.PixelAdjustRect(uiElement, GetComponent<Canvas>());
          Debug.Log("UI Element Screen Bounds: " + rect);
      }
  }
  ```

- **过滤视线数据**：
  - 在收集眼动和头部数据时，检查视线焦点是否落在已定义的 UI 元素边界内，如果是，则忽略这些数据点。

  ```csharp
  using UnityEngine;

  public class GazeDataFilter : MonoBehaviour {
      public Camera mainCamera;
      public LayerMask uiLayer;

      bool IsGazeOnUI(Vector3 gazePoint) {
          Ray ray = mainCamera.ScreenPointToRay(gazePoint);
          return Physics.Raycast(ray, Mathf.Infinity, uiLayer);
      }
  }
  ```

### 4. **AI 工具使用：行为模式识别**

利用机器学习和 AI 工具，可以进一步分析和识别用户行为模式，特别是在大量数据中寻找模式和异常。

- **训练模型识别行为模式**：
  - 使用如 TensorFlow 或 PyTorch 的机器学习库，基于收集的数据训练模型识别用户的行为模式。
  - 训练数据包括头部位置、头部旋转和眼动数据，以及用户的交互行为标签。

  ```python
  import tensorflow as tf
  from sklearn.model_selection import train_test_split
  from sklearn.preprocessing import StandardScaler

  # 假设已经加载了数据 X (features) 和 y (labels)
  X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

  # 数据标准化
  scaler = StandardScaler()
  X_train = scaler.fit_transform(X_train)
  X_test = scaler.transform(X_test)

  # 使用 TensorFlow 构建并训练模型
  model = tf.keras.models.Sequential([
      tf.keras.layers.Dense(64, activation='relu', input_shape=(X_train.shape[1],)),
      tf.keras.layers.Dense(64, activation='relu'),
      tf.keras.layers.Dense(1, activation='sigmoid')
  ])

  model.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
  model.fit(X_train, y_train, epochs=10, batch_size=32)

  # 评估模型
  test_loss, test_acc = model.evaluate(X_test, y_test)
  print('Test accuracy:', test_acc)
  ```

- **动态调整和实时反馈**：
  - 根据 AI 模型的预测结果动态调整 VR 环境，提高用户舒适度。
  - 实时反馈模型预测的用户行为和舒适度趋势，帮助进一步调整和优化。

通过以上方法，你可以在 Unity 中有效地收集和分析 VR 环境中的用户行为数据，同时利用 AI 工具提高行为分析的准确性和深度，最终为用户提供更优质的 VR 体验。

### 策略与方法

#### 1. **区分交互界面与环境视觉探索**

- **视觉焦点分离**：在分析过程中，明确区分用户视线焦点是在交互界面上，还是在环境本身的元素上。这可以通过设置不同的视觉标记 (visual markers) 或利用深度信息 (depth information) 来实现。
  
  ```python
  def is_focusing_on_ui(gaze_point, ui_elements):
      for ui_element in ui_elements:
          if ui_element.contains(gaze_point):
              return True
      return False
  ```

- **使用视线射线**：利用视线射线 (gaze ray) 技术确定用户的视线终点，通过射线与对象的交互来判断用户的注意力是否在界面上。

  ```python
  def get_gaze_intersection(gaze_ray, objects):
      intersections = [obj for obj in objects if obj.intersects(gaze_ray)]
      return intersections
  ```

#### 2. **时间窗口分析**

- **忽略短暂的视线转移**：当用户操作界面时，忽略那些短暂的视线转向界面的时间段，只分析用户在没有与界面交互时的眼动和头部数据。

  ```python
  def filter_gaze_durations(gaze_data, min_duration):
      return [data for data in gaze_data if data['duration'] >= min_duration]
  ```

- **设定操作前后的分析窗口**：在用户开始和完成界面交互前后设定一个时间窗口，只在这些窗口中分析头部和眼部的行为，以避免界面操作直接影响的数据。

  ```python
  def extract_relevant_periods(activity_log, pre_post_duration):
      relevant_periods = []
      for activity in activity_log:
          if activity['type'] == 'adjustment':
              start = activity['time'] - pre_post_duration
              end = activity['time'] + pre_post_duration
              relevant_periods.append((start, end))
      return relevant_periods
  ```

#### 3. **空间区域分析**

- **利用空间信息**：定义环境中的关键空间区域 (如不包含UI的区域)，并在分析中主要关注用户对这些区域的眼动和头部运动。

  ```python
  def is_in_relevant_area(gaze_point, relevant_areas):
      for area in relevant_areas:
          if area.contains(gaze_point):
              return True
      return False
  ```

- **视角过滤**：根据头部转向和视线角度，过滤掉明显朝向交互界面的数据点，保留朝向主要环境区域的数据。

  ```python
  def filter_by_view_angle(gaze_data, max_angle_to_ui):
      return [data for data in gaze_data if data['angle'] > max_angle_to_ui]
  ```

#### 4. **用户行为建模**

- **行为标记**：在用户与UI交互时，记录这一行为，后续分析中可以将这些时段的数据标记为低信度 (low confidence) 或从分析中排除。

  ```python
  def mark_ui_interaction_periods(gaze_data, ui_interaction_periods):
      marked_data = []
      for data in gaze_data:
          if any(start <= data['time'] <= end for start, end in ui_interaction_periods):
              marked_data.append({**data, 'confidence': 'low'})
          else:
              marked_data.append({**data, 'confidence': 'high'})
      return marked_data
  ```

- **动态行为调整**：实时监测用户的头部和眼部行为，当检测到用户开始与界面交互时，动态调整数据记录策略，减少这段时间内的数据权重或忽略这段数据。

  ```python
  def adjust_behavior_recording(gaze_data, interaction_log):
      adjusted_data = []
      for data in gaze_data:
          if any(interaction['start'] <= data['time'] <= interaction['end'] for interaction in interaction_log):
              continue  # Skip this data point
          adjusted_data.append(data)
      return adjusted_data
  ```

