20240805 Updated
"Visual" as the baseline condition,

#### Experimental Setup Overview
- **Workstation Sequence**: A -> B -> C
- **Adjustment Conditions**: Visual (Baseline), Visual + Auditory, Visual + Auditory + Thermal
- **Participants**: 6 participants

### Comparative Analysis for 6 Participants

1. **Same Sensory Adjustment Across Different Workstations (with Visual as Baseline)**
   - **Visual Adjustment** (Baseline):
     - Workstation A: Participants 1 and 2
     - Workstation B: Participants 5 and 6
     - Workstation C: Participants 3 and 4
   - **Visual + Auditory Adjustment**:
     - Workstation A: Participants 3 and 4
     - Workstation B: Participants 1 and 2
     - Workstation C: Participants 5 and 6
   - **Visual + Auditory + Thermal Adjustment**:
     - Workstation A: Participants 5 and 6
     - Workstation B: Participants 3 and 4
     - Workstation C: Participants 1 and 2

   **Significance**: By comparing the same sensory adjustment across different workstations, we can determine how the physical environment impacts participant responses while using the Visual adjustment as a baseline for comparison.

2. **Different Sensory Adjustments at the Same Workstation (Including Visual as Baseline)**
   - **Workstation A**:
     - Visual (Baseline): Participants 1 and 2
     - Visual + Auditory: Participants 3 and 4
     - Visual + Auditory + Thermal: Participants 5 and 6
   - **Workstation B**:
     - Visual (Baseline): Participants 5 and 6
     - Visual + Auditory: Participants 1 and 2
     - Visual + Auditory + Thermal: Participants 3 and 4
   - **Workstation C**:
     - Visual (Baseline): Participants 3 and 4
     - Visual + Auditory: Participants 5 and 6
     - Visual + Auditory + Thermal: Participants 1 and 2

   **Significance**: This comparison helps us understand how additional sensory adjustments affect participant responses at the same workstation. The baseline condition (Visual) serves as a reference point for assessing the impact of adding auditory and thermal adjustments.

### Summary of Comparisons

1. **Baseline (Visual) Comparison Across Workstations**:
   - Analyze how physiological and subjective responses to the Visual adjustment vary across different workstations.

2. **Impact of Additional Adjustments at the Same Workstation**:
   - Compare Visual (baseline) against Visual + Auditory and Visual + Auditory + Thermal adjustments at each workstation to assess the incremental impact of each adjustment.

3. **Aggregate Data Analysis**:
   - Combine data across all participants for each sensory adjustment to identify overall trends.
   - Compare aggregate data for Visual adjustment across all workstations to understand general workstation effects.
   - Compare aggregate data for Visual + Auditory and Visual + Auditory + Thermal adjustments against the baseline to see the overall impact of these adjustments.
---
20240618 Updated
### Description of Experimental Procedures for Participant 01

Participant 01 will proceed through the experiment in a fixed sequence of workstations (A -> B -> C), with different adjustment conditions randomly assigned at each workstation (Visual, Visual + Auditory, Visual + Auditory + Thermal). Below are the detailed steps of the experimental procedures:

#### Experimental Setup

1. **Workstation sequence**: A -> B -> C
2. **Adjustment conditions**: Different adjustment conditions are randomly assigned at each workstation.

### Experimental Design Plan

#### Fixed Workstation Sequence, Random Adjustment Conditions

Each participant follows a fixed workstation sequence (A -> B -> C), with different adjustment conditions randomly assigned at each workstation.

### Data Points and Number of Participants Calculation

- At least 10 data points (stream) per combination.
- 3 workstations × 3 adjustment conditions = 9 combinations.
- 10 data points per combination, totaling 90 data points.
- Each participant provides 3 data points.
- Number of required participants = 90 ÷ 3 = 30 participants.


### Experimental Steps

#### Workstation A

1. **Adjustment condition**: Visual
2. **Initial measurements**:
   - Record baseline physiological data, including Skin Conductance (SC), Heart Rate (HR), and EEG brain waves (Alpha waves).
   - Record the participant's subjective comfort score and work efficiency score (baseline).
3. **Immersion and task** (5 minutes):
   - The participant performs a designated task at workstation A, tailored to the experiment's objectives (e.g., solving simple problems, reading).
   - The adjustment condition is Visual (visual adjustment only).
4. **Measurement**:
   - Record the physiological data after the adjustment, including SC, HR, and EEG (Alpha waves).
   - Record the participant's subjective comfort score and work efficiency score.
5. **Data storage**:
   - Record all data in the experimental data table, ensuring data integrity and accuracy.

#### Workstation B

1. **Adjustment condition**: Visual + Auditory
2. **Initial measurements**:
   - Record baseline physiological data, including SC, HR, and EEG (Alpha waves).
   - Record the participant's subjective comfort score and work efficiency score (baseline).
3. **Immersion and task** (5 minutes):
   - The participant performs a designated task at workstation B, tailored to the experiment's objectives (e.g., solving simple problems, reading).
   - The adjustment condition is Visual + Auditory (visual and auditory adjustments).
4. **Measurement**:
   - Record the physiological data after the adjustment, including SC, HR, and EEG (Alpha waves).
   - Record the participant's subjective comfort score and work efficiency score.
5. **Data storage**:
   - Record all data in the experimental data table, ensuring data integrity and accuracy.

#### Workstation C

1. **Adjustment condition**: Visual + Auditory + Thermal
2. **Initial measurements**:
   - Record baseline physiological data, including SC, HR, and EEG (Alpha waves).
   - Record the participant's subjective comfort score and work efficiency score (baseline).
3. **Immersion and task** (5 minutes):
   - The participant performs a designated task at workstation C, tailored to the experiment's objectives (e.g., solving simple problems, reading).
   - The adjustment condition is Visual + Auditory + Thermal (visual, auditory, and thermal adjustments).

### Deciding Whether to Store Timestamped Data in a Single Table or Separate Tables per Participant

### Single Table Method

#### Advantages:

1. **Centralized Management**: All data are consolidated into one table, simplifying the data handling and analysis process.
2. **Uniform Processing**: Facilitates data analysis across all participants, such as calculating overall trends, mean values, or standard deviations.
3. **Suitable for ML**: Machine learning models typically require large data inputs, and having all data in one table aids in the use of various ML algorithms for training and validation.

#### Disadvantages:

1. **Size Issues**: For large-scale studies, a single table can become very large, leading to slow processing speeds or insufficient memory.
2. **Complex Data Cleaning**: If the dataset contains errors or missing data, cleaning the entire dataset can become more complicated.

For statistical analysis and machine learning model training, the single table method is generally recommended, especially when the need arises to analyze data holistically or train machine learning models. This approach not only reduces the complexity of data preprocessing but also allows direct use of existing statistical and ML tools, which often assume data is stored in a single, structured format.

### Including Timestamps and Continuous Data Recording in Research

### 1. Increased Data Points
With continuous measurement, the data points for each experimental condition are no longer limited to a single or a few measurements but can include multiple data points throughout the entire duration of the experiment. For example, if you record data every second, you can collect 60 data points per minute, significantly increasing the number of data points under each condition.

### 2. Improved Time Resolution
Data with timestamps offer higher time resolution, allowing you to observe subtle changes in physiological responses over time. This is particularly important for understanding how different adjustments lead to drastic or significant physiological changes.

### 3. Capturing Dynamic Changes
Continuous data recording can reveal dynamic changes in physiological responses, such as rapid increases in heart rate or trends in skin conductance response, which might not be observable with only a few data points.

### 4. More Complex Analyses
Complex statistical and machine learning techniques such as time series analysis, repeated measures ANOVA, and dynamic system modeling can be applied to this rich dataset to uncover deeper patterns and associations.

### Example of a Data Set
Suppose you conducted an experiment involving three sensory adjustments (Visual, Auditory, Thermal) and used timestamps to continuously record data. The table below is a possible data structure:

Certainly! If you want to expand the data set example to include at least six participants and show how their physiological responses might be recorded continuously throughout an experiment involving different sensory adjustments, here’s how you can structure the table:

### Expanded Data Set Example with Six Participants

The table below simulates an experimental setting where each participant undergoes the same sequence of sensory adjustments (Visual, Auditory, Thermal) and data is continuously recorded:

| Timestamp  | Participant ID | Adjustment Type | Heart Rate (BPM) | Skin Conductance (µS) | EEG (µV) | Comfort Level |
|------------|----------------|-----------------|------------------|-----------------------|----------|---------------|
| 14:23:45   | P1             | Visual          | 72               | 1.2                   | 8.5      | Medium        |
| 14:23:45   | P2             | Visual          | 68               | 1.0                   | 9.0      | High          |
| 14:23:45   | P3             | Visual          | 70               | 1.1                   | 8.7      | Medium        |
| 14:23:45   | P4             | Visual          | 74               | 1.3                   | 8.3      | Low           |
| 14:23:45   | P5             | Visual          | 69               | 1.2                   | 8.9      | Medium        |
| 14:23:45   | P6             | Visual          | 71               | 1.2                   | 8.6      | High          |
| 14:23:46   | P1             | Visual          | 73               | 1.3                   | 8.6      | Medium        |
| 14:23:46   | P2             | Visual          | 68               | 1.0                   | 9.1      | High          |
| 14:23:46   | P3             | Visual          | 71               | 1.1                   | 8.8      | Medium        |
| 14:23:46   | P4             | Visual          | 75               | 1.3                   | 8.2      | Low           |
| 14:23:46   | P5             | Visual          | 70               | 1.2                   | 8.8      | Medium        |
| 14:23:46   | P6             | Visual          | 72               | 1.2                   | 8.5      | High          |
| ...        | ...            | ...             | ...              | ...                   | ...      | ...           |

---

要确保实验设计中包含所有可能的感官调整组合，特别是当你有三种基本调整（Visual、Visual + Auditory、Visual + Auditory + Thermal）时，你可以创建所有可能的序列组合。这里，我们将制定一个包含所有这些组合的列表，适用于每种感官调整可以在三个工位上任意排列的情况。

### 六种感官调整组合

因为有三种调整，并且每种调整可以自由组合，且考虑到每种调整至少出现一次的条件，我们可以设计以下六种不同的组合：

1. **组合 1**：
   - 工位 A: Visual
   - 工位 B: Visual + Auditory
   - 工位 C: Visual + Auditory + Thermal

2. **组合 2**：
   - 工位 A: Visual + Auditory
   - 工位 B: Visual + Auditory + Thermal
   - 工位 C: Visual

3. **组合 3**：
   - 工位 A: Visual + Auditory + Thermal
   - 工位 B: Visual
   - 工位 C: Visual + Auditory

4. **组合 4**：
   - 工位 A: Visual
   - 工位 B: Visual + Auditory + Thermal
   - 工位 C: Visual + Auditory

5. **组合 5**：
   - 工位 A: Visual + Auditory
   - 工位 B: Visual
   - 工位 C: Visual + Auditory + Thermal

6. **组合 6**：
   - 工位 A: Visual + Auditory + Thermal
   - 工位 B: Visual + Auditory
   - 工位 C: Visual

### 使用场景

这些组合可以用于各种研究目的，比如探索不同感官调整对参与者工作效率和舒适度的影响。根据实验的具体需求，可以选择适当的组合进行深入分析。

### Unity Scripts

```csharp
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class SensoryAdjustmentManager : MonoBehaviour
{
    private string[][] combinations = new string[][]
    {
        new string[] {"Visual", "Visual_Auditory", "Visual_Auditory_Thermal"},
        new string[] {"Visual_Auditory", "Visual_Auditory_Thermal", "Visual"},
        new string[] {"Visual_Auditory_Thermal", "Visual", "Visual_Auditory"},
        new string[] {"Visual", "Visual_Auditory_Thermal", "Visual_Auditory"},
        new string[] {"Visual_Auditory", "Visual", "Visual_Auditory_Thermal"},
        new string[] {"Visual_Auditory_Thermal", "Visual_Auditory", "Visual"}
    };

    public void LoadAdjustmentSequence(int participantId)
    {
        int index = (participantId % 6) - 1;
        if (index < 0) index += 6; // Ensure index is always positive

        string[] selectedCombination = combinations[index];
        // Load scenes based on the selected combination
    }
}
```

---

### Methods for Analyzing Physiological Data

#### Skin Conductance (SC)

1. **Calculate average and standard deviation**:
   - Compute the average and standard deviation for SC at each station and under each adjustment condition to assess arousal levels.
2. **Emotional analysis**:
   - Higher SC values are typically associated with higher emotional arousal, reflecting the participant's

## 20240520 Prototype Details
### Example of Balanced Crossover Design

Suppose there are four experimental conditions: Control (C), Experimental Group 1 (E1), Experimental Group 2 (E2), and Experimental Group 3 (E3). A Latin square can be used to arrange the experiment order:

| Participant | Order 1 | Order 2 | Order 3 | Order 4 |
|-------------|---------|---------|---------|---------|
| 1           | C       | E1      | E2      | E3      |
| 2           | E1      | E2      | E3      | C       |
| 3           | E2      | E3      | C       | E1      |
| 4           | E3      | C       | E1      | E2      |

---
**Original visual settings**: mornitor, keyborads, and a mouse
**Original background sounds**: keyboard, and mouse click
> 
> **Visual Adjustments (VA)**
> - Light Adjustment: Participants adjust brightness and color temperature of individual lighting devices, natural lights through the blinder (sit closed to the window).
> - Material Adjustment: Participants select and modify object materials, including the divider, table, wall, sound box, and desk surface.
> Customized items: calendar, books, photo frames, toys, and vegetations
>
> **Auditory Adjustments (AA)** 
> - Background noise level: adjust the height and material of the divider
> - Background music: activate the sound box, switch across classic music, Jazz, anime...[original sound level will be reduced]
> - Background natural sounds: activate the sound box, switch across bird song, forest ambience, water streams, ocean waves [original sound level will be reduced]
>
> **Thermal Adjustments (TA)** 
> Portable Neck Fans can be used for cooling/warming
---
## Prototype A [from Emotiv to Galea / from Galea to Emotiv]
### Tutorial :
##### VR session: 10 min
guidance for VA + AA + TA in an exisiting virtual enviroonment 

### Game Start [Emotiv to Galea]:
Select positions
move to the prefered postion, "I would like to sit here"
hand controller point to the computer monitor
"confirm"

### C (Control Group: original settings):
***Duration:20min***
##### VR Experience session: 8 min
- Activate Visual and Auditory Items
> **Interaction:** Use gaze tracking or the controller to point at and activate items without any actual interaction adjustments.
> **Observation:** Observe how participants' preferences for changing the same items in the environment vary under different experimental sequences.
- Inquire About Desire to Adjust Design Properties
> **Interaction:** After item activation, a simple interface pops up, and participants make selections using the controller. The selections are multiple choices to adjust design properties for one activated item with gif/video examples.
> **Observation:** Analyze whether participants' preferences for potential design changes differ under different experimental sequences and conditions.

##### VR Cognition performance test: less than 7 min [To(cpt)]
##### Survey in the virtual environment: [To(s)]

### E(a) (Galea + Survey in the real world):
***Duration:20min***
##### VR Experienec session: about 8 min 
- Design adjustment: about 5 min [Ta(v01)]
> VA + AA + TA in the middle sitting position
- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.
##### VR Cognition performance test: less than 7 min [Ta(cpt)]
##### Survey: less than 8 min [Ta(s)]

### E(b) (Galea + Survey in the virtual world):
##### VR session: about 8 min 
- Design adjustment: about 5 min [Tb(v01)]
> VA + AA + TA in the sitting position closed to the window
- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.
##### Cognition performance test: less than 7 min [Tb(cpt)]
##### Survey: about 5 min [Tb(s)]

### E(c) (Emotiv + Survey in the virtual world):
### Basic Tutorial in the new headset: 5 min
##### VR session: about 15 min 
- Design adjustment: about 5 min [Tc(v01)]
> VA + AA + TA in the sitting position closed to the window
- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.
##### Cognition performance test: less than 7 min [Tc(cpt)]
##### Survey: less than 8 min [Tc(s)]
---
## Prototype A: Data collection
#### Subjective Feedback:

#### Objective Feedback
---
## Prototype B

### Tutorial :
##### VR Experience session: 10 min
>VA + AA + TA in an exisiting virtual enviroonment with guidances

### Game Start:
- Select positions
- move to the prefered postion, "I would like to sit here"
- hand controller point to the computer monitor
- "confirm"

### C (Control Group):
##### VR Experience session: 8 min
- Activate Visual and Auditory Items
> **Interaction:** Use gaze tracking or the controller to point at and activate items without any actual interaction adjustments.
> **Observation:** Observe how participants' preferences for changing the same items in the environment vary under different experimental sequences.
- Inquire About Desire to Adjust Design Properties
> **Interaction:** After item activation, a simple interface pops up, and participants make selections using the controller. The selections are multiple choices to adjust design properties for one activated item with gif/video examples.
> **Observation:** Analyze whether participants' preferences for potential design changes differ under different experimental sequences and conditions.

##### VR Cognition performance test: less than 7 min
##### Survey: less than 8 min


### E1 (Visual + Auditory):
##### VR Experience session: 8 min
- Design adjustment: 5 min
> - VA + AA

- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.
##### VR Cognition performance test: less than 7 min

### E2 (Visual + Thermal):
##### VR Experience session: 8 min
- Design adjustment: 5 min
> - VA + TA

- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.

##### VR Cognition performance test: less than 7 min
##### Survey: less than 8 min

### E3 (Visual + Auditory + Thermal):
##### VR Experience session: 8 min
- Design adjustment: 5 min
> - VA + AA + TA

- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.

##### VR Cognition Performance Test: less than 7 min
##### Survey: less than 8 min

---
## Prototype B: Data Collection
#### Subjective Feedback:

#### Objective Feedback:
- Observe Eye Movements and Basic Motion Behavior
To effectively measure the changes in user behavior and comfort in a VR environment, especially during the pre-adjustment, during-adjustment, and post-adjustment phases, you need to directly measure specific data points related to head and eye movements. These measurements will help you calculate meaningful metrics that reflect user behavior and comfort changes.

Here is a breakdown of what data to measure and how to calculate the relevant metrics in English:

### 1. **Head Movement Metrics**

#### Data to Measure

- **Head Position and Orientation**: Track the 3D position (x, y, z coordinates) and the orientation (pitch, yaw, roll angles) of the user’s head over time.

#### Metrics to Calculate

- **Head Rotation Frequency**
  - **Description**: The number of times the head orientation changes direction per unit of time, indicating how often the user is looking around.
  - **Calculation**: Count the number of times the head changes direction significantly (beyond a threshold angle) in a given period and divide by the duration of that period.
  
  ```python
  rotation_changes = sum(1 for i in range(1, len(orientations)) if abs(orientations[i] - orientations[i-1]) > threshold)
  rotation_frequency = rotation_changes / total_time
  ```

- **Head Movement Range**
  - **Description**: The range of head movement across different axes, showing how much the user moves their head.
  - **Calculation**: Find the maximum and minimum pitch, yaw, and roll angles during the observation period and compute the range for each axis.
  
  ```python
  pitch_range = max(pitch_angles) - min(pitch_angles)
  yaw_range = max(yaw_angles) - min(yaw_angles)
  roll_range = max(roll_angles) - min(roll_angles)
  ```

- **Head Stability**
  - **Description**: Measures the steadiness of the head position, indicating user comfort and focus.
  - **Calculation**: Compute the standard deviation of head positions over time. Lower values indicate more stability.
  
  ```python
  stability = sqrt(sum((x - mean_x)^2 + (y - mean_y)^2 + (z - mean_z)^2 for x, y, z in positions) / len(positions))
  ```

### 2. **Eye Tracking Metrics**

#### Data to Measure

- **Gaze Points**: Capture the coordinates of the user's gaze on the screen or within the environment over time.
- **Pupillary Response**: Track the diameter of the pupils over time.

#### Metrics to Calculate

- **Gaze Duration**
  - **Description**: The average time the user spends looking at the same object or area.
  - **Calculation**: Measure the time between when the gaze point hits an object or area and when it changes, then average these times.
  
  ```python
  gaze_durations = [end_time - start_time for start_time, end_time in gaze_periods]
  average_gaze_duration = sum(gaze_durations) / len(gaze_durations)
  ```

- **Gaze Change Frequency**
  - **Description**: The rate at which the gaze point changes from one object or area to another.
  - **Calculation**: Count the number of times the gaze point changes per unit of time.
  
  ```python
  gaze_changes = sum(1 for i in range(1, len(gaze_points)) if gaze_points[i] != gaze_points[i-1])
  gaze_change_frequency = gaze_changes / total_time
  ```

- **Pupillary Response**
  - **Description**: The average change in pupil size, reflecting cognitive load and light adaptation.
  - **Calculation**: Compute the difference between the maximum and minimum pupil sizes within the observed period.
  
  ```python
  pupillary_response = max(pupil_sizes) - min(pupil_sizes)
  ```

### 3. **Visual Exploration and Attention Distribution**

#### Data to Measure

- **Gaze Heatmap**: A distribution showing where the user's gaze falls across the visual field.

#### Metrics to Calculate

- **Visual Exploration Range**
  - **Description**: The spatial extent of gaze points across the visual field.
  - **Calculation**: Calculate the area covered by the gaze points in the visual field.
  
  ```python
  x_range = max(x_coords) - min(x_coords)
  y_range = max(y_coords) - min(y_coords)
  exploration_range = x_range * y_range
  ```

- **Attention Heatmap**
  - **Description**: A heatmap showing the density of gaze points over the visual field, indicating areas of high interest.
  - **Calculation**: Count gaze points within each region of the visual field and normalize by the total number of gaze points.
  
  ```python
  heatmap = [[0]*grid_width for _ in range(grid_height)]
  for x, y in gaze_points:
      heatmap[y // cell_height][x // cell_width] += 1
  normalized_heatmap = [[cell / total_gaze_points for cell in row] for row in heatmap]
  ```

### Application in Analysis

- **Pre-Adjustment vs. During-Adjustment Analysis**: Compare the metrics from the baseline (pre-adjustment) to those during the adjustment phase to understand how user behavior changes in response to their efforts to optimize comfort.
- **Long-Term Adaptation Analysis**: By comparing metrics from the baseline and post-adjustment phases, assess how well users adapt to the changes and whether their behavior stabilizes in a way that suggests improved comfort and satisfaction.

By measuring these metrics and analyzing them through the phases of environmental adjustment, you can gain insights into how design changes affect user comfort and behavior, guiding more effective adjustments and enhancements in VR environments.
## 20240407 Research Steps
> - Phase 01 VR training
> - Phase 02 VR experiment with the original settings
> - Phase 03 cognitive test in the VR environment
> - Phase 04 take off the VR headset and conduct the online survey 
> - Phase 05 (redo phase 02 - phase 04): add the visual stimuli
> - Phase 06 (redo phase 02 - phase 04): add the visual and auditory stimuli
> - Phase 07 (redo phase 02 - phase 04): add change the visual, auditory, and olfactory stimuli
> - **Physiological measurement during the virtual experience (phase 02 - phase 03)**
>

