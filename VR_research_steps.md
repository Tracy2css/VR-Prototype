20240808 Updated
### 设计新的实验表格

我们将引入一个新的感官调整（Visual + Thermal）和一个新的工位（D）。每个参与者将体验所有四个工位，每个工位的感官调整是随机排列的。以下是调整后的表格：

#### 实验表格

| Participant | Workstation A                | Workstation B                 | Workstation C                 | Workstation D                |
|-------------|------------------------------|-------------------------------|-------------------------------|------------------------------|
| 1           | Visual (Baseline)            | Visual + Auditory             | Visual + Auditory + Thermal   | Visual + Thermal             |
| 2           | Visual + Auditory            | Visual + Auditory + Thermal   | Visual (Baseline)             | Visual + Thermal             |
| 3           | Visual + Auditory + Thermal  | Visual (Baseline)             | Visual + Auditory             | Visual + Thermal             |
| 4           | Visual + Auditory            | Visual + Auditory + Thermal   | Visual (Baseline)             | Visual + Thermal             |
| 5           | Visual (Baseline)            | Visual + Auditory             | Visual + Auditory + Thermal   | Visual + Thermal             |
| 6           | Visual + Auditory + Thermal  | Visual (Baseline)             | Visual + Auditory             | Visual + Thermal             |

#### 数据收集表格

每个参与者在每个工位下都将测量以下数据：

| Participant | Workstation | SC   | HR   | EEG  | Comfort Score | Efficiency Score |
|-------------|-------------|------|------|------|---------------|------------------|
| 1           | A           | ...  | ...  | ...  | ...           | ...              |
| 1           | B           | ...  | ...  | ...  | ...           | ...              |
| 1           | C           | ...  | ...  | ...  | ...           | ...              |
| 1           | D           | ...  | ...  | ...  | ...           | ...              |
| 2           | A           | ...  | ...  | ...  | ...           | ...              |
| 2           | B           | ...  | ...  | ...  | ...           | ...              |
| 2           | C           | ...  | ...  | ...  | ...           | ...              |
| 2           | D           | ...  | ...  | ...  | ...           | ...              |
| ...         | ...         | ...  | ...  | ...  | ...           | ...              |

### 机器学习模型的选择

#### 分类任务
分类任务主要用于将数据分配到不同的类别。对于这个实验，我们可以进行以下分类任务：
1. **预测工位类型**：根据生理数据和主观评分预测参与者所处的工位类型（A, B, C, D）。
2. **预测感官调整**：根据生理数据和主观评分预测参与者所处的感官调整类型（Visual, Visual + Auditory, Visual + Auditory + Thermal, Visual + Thermal）。

#### 回归任务
回归任务主要用于预测连续变量。对于这个实验，我们可以进行以下回归任务：
1. **预测舒适度评分**：根据生理数据预测参与者的舒适度评分。
2. **预测效率评分**：根据生理数据预测参与者的效率评分。

#### 推荐的机器学习模型

**基础模型**：
1. **决策树**：简单易解释，适用于初步探索。
2. **随机森林**：通过多个决策树的投票减少过拟合，适用于分类和回归任务。
3. **线性回归**：用于连续变量预测，适用于回归任务。
4. **支持向量机（SVM）**：适用于小数据集的分类任务。

**高级模型**：
1. **神经网络**：适用于复杂的非线性关系，可以用于分类和回归任务。
2. **长短期记忆网络（LSTM）**：适用于时间序列数据，可以捕捉数据的时序依赖性。

### 基于现有模型和现有调整的VR调研，优化机器学习模型的方向

1. **数据预处理**：确保数据的清洗和标准化，以减少噪声和异常值的影响。
2. **特征选择和提取**：通过特征工程，选择和提取有助于模型训练的重要特征。
3. **模型验证**：使用交叉验证技术验证模型的泛化能力，防止过拟合。
4. **参数调优**：通过网格搜索或随机搜索优化模型参数，提高模型性能。
5. **模型融合**：结合多个模型的优势，提高预测的准确性和稳定性。
6. **增加数据量**：如果可能，通过增加参与者数量或多次实验，增加数据量以提高模型的训练效果。

### Conclusion

By focusing on between-participant comparisons and using various machine learning models, we can gain insights into the overall effects of sensory adjustments and workstations on participants. This data-driven approach can inform the design of more comfortable and efficient workspaces.

### Translation to English

### Experimental Design

We will introduce a new sensory adjustment (Visual + Thermal) and a new workstation (D). Each participant will experience all four workstations with sensory adjustments randomly shuffled. Below is the adjusted table:

#### Experiment Table

| Participant | Workstation A                | Workstation B                 | Workstation C                 | Workstation D                |
|-------------|------------------------------|-------------------------------|-------------------------------|------------------------------|
| 1           | Visual (Baseline)            | Visual + Auditory             | Visual + Auditory + Thermal   | Visual + Thermal             |
| 2           | Visual + Auditory            | Visual + Auditory + Thermal   | Visual (Baseline)             | Visual + Thermal             |
| 3           | Visual + Auditory + Thermal  | Visual (Baseline)             | Visual + Auditory             | Visual + Thermal             |
| 4           | Visual + Auditory            | Visual + Auditory + Thermal   | Visual (Baseline)             | Visual + Thermal             |
| 5           | Visual (Baseline)            | Visual + Auditory             | Visual + Auditory + Thermal   | Visual + Thermal             |
| 6           | Visual + Auditory + Thermal  | Visual (Baseline)             | Visual + Auditory             | Visual + Thermal             |

#### Data Collection Table

For each participant, data will be measured at each workstation:

| Participant | Workstation | SC   | HR   | EEG  | Comfort Score | Efficiency Score |
|-------------|-------------|------|------|------|---------------|------------------|
| 1           | A           | ...  | ...  | ...  | ...           | ...              |
| 1           | B           | ...  | ...  | ...  | ...           | ...              |
| 1           | C           | ...  | ...  | ...  | ...           | ...              |
| 1           | D           | ...  | ...  | ...  | ...           | ...              |
| 2           | A           | ...  | ...  | ...  | ...           | ...              |
| 2           | B           | ...  | ...  | ...  | ...           | ...              |
| 2           | C           | ...  | ...  | ...  | ...           | ...              |
| 2           | D           | ...  | ...  | ...  | ...           | ...              |
| ...         | ...         | ...  | ...  | ...  | ...           | ...              |

### Machine Learning Model Selection

#### Classification Tasks
Classification tasks can be used to categorize data into different classes. For this experiment, we can perform the following classification tasks:
1. **Predict Workstation Type**: Predict the type of workstation (A, B, C, D) based on physiological data and subjective scores.
2. **Predict Sensory Adjustment**: Predict the type of sensory adjustment (Visual, Visual + Auditory, Visual + Auditory + Thermal, Visual + Thermal) based on physiological data and subjective scores.

#### Regression Tasks
Regression tasks can be used to predict continuous variables. For this experiment, we can perform the following regression tasks:
1. **Predict Comfort Score**: Predict the comfort score based on physiological data.
2. **Predict Efficiency Score**: Predict the efficiency score based on physiological data.

#### Recommended Machine Learning Models

**Basic Models**:
1. **Decision Tree**: Simple and interpretable, suitable for initial exploration.
2. **Random Forest**: Reduces overfitting by combining multiple decision trees, suitable for both classification and regression tasks.
3. **Linear Regression**: Used for predicting continuous variables, suitable for regression tasks.
4. **Support Vector Machine (SVM)**: Suitable for classification tasks with small datasets.

**Advanced Models**:
1. **Neural Networks**: Suitable for complex nonlinear relationships, can be used for both classification and regression tasks.
2. **Long Short-Term Memory (LSTM) Networks**: Suitable for time-series data, can capture temporal dependencies in the data.

### Optimizing Machine Learning Models for VR Research

1. **Data Preprocessing**: Ensure data is cleaned and standardized to reduce noise and outliers' impact.
2. **Feature Selection and Extraction**: Use feature engineering to select and extract important features that contribute to model training.
3. **Model Validation**: Use cross-validation techniques to validate the model's generalizability and prevent over
---
20240805 Updated
"Visual" as the baseline condition,

#### Experimental Setup Overview
- **Workstation Sequence**: A -> B -> C
- **Adjustment Conditions (Sequence can be shuffled)**: Visual (Baseline), Visual + Auditory, Visual + Auditory + Thermal

### Data collection
   - Each participant can provide 3 data points
   - 3 workstations × 3 adjustment conditions = 9 combinations.
   - 3 workstations × 4 adjustment conditions = 12 combinations.
   - 3&times;30(participants)=90 data points
   - about 10 data points for per combination

#### Participant Adjustment (using 6 participants as an example) 

| Participant | Workstation A                | Workstation B                 | Workstation C                 |
|-------------|------------------------------|-------------------------------|-------------------------------|
| 1           | Visual (Baseline)            | Visual + Auditory             | Visual + Auditory + Thermal   |
| 2           | Visual + Auditory            | Visual + Auditory + Thermal   | Visual (Baseline)             |
| 3           | Visual + Auditory + Thermal  | Visual (Baseline)             | Visual + Auditory             |
| 4           | Visual + Auditory            | Visual + Auditory + Thermal   | Visual (Baseline)             |
| 5           | Visual (Baseline)            | Visual + Auditory             | Visual + Auditory + Thermal   |
| 6           | Visual + Auditory + Thermal  | Visual (Baseline)             | Visual + Auditory             |

1. **Within-Sensory Comparison: Same Sensory Adjustment Across Different Workstations (with Visual as Baseline)**
   - **Visual Adjustment** (Baseline):
     - Workstation A: Participants 1 and 5
     - Workstation B: Participants 3 and 6
     - Workstation C: Participants 2 and 4
   - **Visual + Auditory Adjustment**:
     - Workstation A: Participants 2 and 4
     - Workstation B: Participants 1 and 5
     - Workstation C: Participants 3 and 6
   - **Visual + Auditory + Thermal Adjustment**:
     - Workstation A: Participants 3 and 6
     - Workstation B: Participants 2 and 4
     - Workstation C: Participants 1 and 5

2. **Within-Workstation Comparion: Different Sensory Adjustments at the Same Workstation (Including Visual as Baseline)**
   - **Workstation A**:
     - Visual (Baseline): Participants 1 and 5
     - Visual + Auditory: Participants 2 and 4
     - Visual + Auditory + Thermal: Participants 3 and 6
   - **Workstation B**:
     - Visual (Baseline): Participants 3 and 6
     - Visual + Auditory: Participants 1 and 5
     - Visual + Auditory + Thermal: Participants 2 and 4
   - **Workstation C**:
     - Visual (Baseline): Participants 2 and 4
     - Visual + Auditory: Participants 3 and 6
     - Visual + Auditory + Thermal: Participants 1 and 5


#### Based on the investigation, we can 
1. **Evaluate the Overall Effects of Sensory Adjustments**:
   - Identify how different sensory adjustments (e.g., Visual, Visual + Auditory, Visual + Auditory + Thermal) impact participants’ physiological and subjective responses.

2. **Compare the Impact of Workstation Environments**:
   - Assess how different workstation environments (e.g., A, B, C) affect participant responses.

3. **Identify Optimal Combinations**:
   - Determine which combinations of sensory adjustments and workstations are most effective for enhancing comfort and work efficiency.

4. **Build Predictive Models**:
   - Develop machine learning models to predict participant responses under different sensory adjustments and workstation conditions, guiding future workspace design.

#### Limitations: 
- No with-in participant investigation that can reflect individual differences in the effects of sensory adjustments. 
- However, we emphasised personal control and alliethesia in the thesis 

### Question: With-in participant investigation

| Participant | Workstation A                | Workstation B                 | Workstation C                 |
|-------------|------------------------------|-------------------------------|-------------------------------|
| 1           | Visual (Baseline)            | Visual + Auditory             | Visual + Auditory + Thermal   |
| 1           | Visual + Auditory            | Visual + Auditory + Thermal   | Visual (Baseline)             |
| 1           | Visual + Auditory + Thermal  | Visual (Baseline)             | Visual + Auditory             |

| Participant | Workstation A                |
|-------------|------------------------------|
| 1           | Visual (Baseline)            |
| 1           | Visual + Auditory            |
| 1           | Visual + Auditory + Thermal  |

- For ML data analysis, it would be better if we can collect data from one participant at the same workstation with different adjustment conditions.
- Do we need to add two tests at the same workstation at least? For instance, participant 1 can have three tests at workstation A with different adjustment conditions.
- However, the added two VR scenarios may cause increased experiment time.

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

