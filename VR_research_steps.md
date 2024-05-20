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

### Experiment Design Steps

1. **Baseline Measurement**:
   - Record baseline data for all participants in a standard VR office environment without any additional sensory stimuli. This data includes work efficiency, eye-tracking, head movements, and other relevant metrics.

2. **Repeated Measures Experiment**:
   - Each participant will take part in all experimental groups, including the control group and various experimental groups, to assess the impact of different combinations of sensory stimuli on user experience and work efficiency.

3. **Experimental Group Settings**:
   - **Control Group (C)**: Participants complete tasks in the basic VR office environment without any sensory stimuli adjustments.
   - **Experimental Group 1 (E1, Visual + Auditory)**: Adjust both visual (light intensity, color temperature) and auditory (background music, environmental sounds) stimuli.
   - **Experimental Group 2 (E2, Visual + Thermal)**: Adjust visual stimuli and thermal comfort stimuli simulated through visual and auditory cues.
   - **Experimental Group 3 (E3, Visual + Auditory + Thermal)**: Adjust visual, auditory, and simulated thermal comfort stimuli to provide a comprehensive sensory experience.

4. **Balanced Order Design**:
   - Use a Latin square or a balanced crossover design to randomize the order of different experimental conditions to avoid order effects and fatigue.

### Example of Balanced Crossover Design

Suppose there are four experimental conditions: Control (C), Experimental Group 1 (E1), Experimental Group 2 (E2), and Experimental Group 3 (E3). A Latin square can be used to arrange the experiment order:

| Participant | Order 1 | Order 2 | Order 3 | Order 4 |
|-------------|---------|---------|---------|---------|
| 1           | C       | E1      | E2      | E3      |
| 2           | E1      | E2      | E3      | C       |
| 3           | E2      | E3      | C       | E1      |
| 4           | E3      | C       | E1      | E2      |

### Implementation Steps

1. **Baseline Measurement**:
   - Conduct baseline measurements for all participants in a standard VR office environment without any sensory stimuli.

2. **Experimental Execution**:
   - According to the sequence assigned to each participant, have them sequentially experience each experimental condition.
   - For example, Participant 1 will participate in the order C → E1 → E2 → E3.

3. **Data Recording and Rest**:
   - Record data such as work efficiency, eye tracking, head movements, etc., under each experimental condition.
   - Provide sufficient rest time for participants before switching to the next experimental condition to minimize fatigue effects.

4. **Data Analysis**:
   - Compare and analyze the performance of participants under different experimental conditions to determine the impact of various sensory stimuli combinations.
   - Use statistical tests such as repeated measures ANOVA, paired t-tests, or other relevant methods to assess significant differences in the data.

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

## C (Control Group: original settings):
##### VR session: 8 min
- Activate Visual and Auditory Items
> **Interaction:** Use gaze tracking or the controller to point at and activate items without any actual interaction adjustments.
> **Observation:** Observe how participants' preferences for changing the same items in the environment vary under different experimental sequences.
- Inquire About Desire to Adjust Design Properties
> **Interaction:** After item activation, a simple interface pops up, and participants make selections using the controller. The selections are multiple choices to adjust design properties for one activated item with gif/video examples.
> **Observation:** Analyze whether participants' preferences for potential design changes differ under different experimental sequences and conditions.

##### Cognition performance test: less than 7 min [To(cpt)]
##### Survey in the virtual environment: [To(s)]

### E(a) (Galea + Survey in the real world):
##### VR session: about 15 min 
- Design adjustment: about 5 min [Ta(v01)]
> VA + AA + TA in the middle sitting position
- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.
##### Cognition performance test: less than 7 min [Ta(cpt)]
##### Survey: less than 8 min [Ta(s)]

### E(b) (Galea + Survey in the virtual world):
##### VR session: about 15 min 
- Design adjustment: about 5 min [Tb(v01)]
> VA + AA + TA in the sitting position closed to the window
- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.
##### Cognition performance test: less than 7 min [Tb(cpt)]
##### Survey: less than 8 min [Tb(s)]

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
### Prototype: data collection
#### Subjective Feedback:

#### Objective Feedback
---
## Prototype B

### Tutorial :
##### VR session: 10 min
>VA + AA + TA in an exisiting virtual enviroonment with guidances

### Game Start:
- Select positions
- move to the prefered postion, "I would like to sit here"
- hand controller point to the computer monitor
- "confirm"

### C (Control Group):
##### VR session: 8 min
- Activate Visual and Auditory Items
> **Interaction:** Use gaze tracking or the controller to point at and activate items without any actual interaction adjustments.
> **Observation:** Observe how participants' preferences for changing the same items in the environment vary under different experimental sequences.
- Inquire About Desire to Adjust Design Properties
> **Interaction:** After item activation, a simple interface pops up, and participants make selections using the controller. The selections are multiple choices to adjust design properties for one activated item with gif/video examples.
> **Observation:** Analyze whether participants' preferences for potential design changes differ under different experimental sequences and conditions.

##### Cognition performance test: less than 7 min
##### Survey: less than 8 min


### E1 (Visual + Auditory):
##### VR session: 8 min
- Design adjustment: 5 min
> - VA + AA

- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.
##### Cognition performance test: less than 7 min

### E2 (Visual + Thermal):
##### VR session: 8 min
- Design adjustment: 5 min
> - VA + TA

- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.

##### Cognition performance test: less than 7 min
##### Survey: less than 8 min

### E3 (Visual + Auditory + Thermal):
##### VR session: 8 min
- Design adjustment: 5 min
> - VA + AA + TA

- Observation and Immersive Experience: 3min
>- After a confirmation of completing the adjustment sessions, participants can stand up and look around the unmodified environment, and enjoy their optimised design outcomes. 
>- Participants are encouraged to sit again and talk their modifications in the immersive experieneces with the headset.

##### Cognition performance test: less than 7 min
##### Survey: less than 8 min

---
#### Subjective Feedback:

#### Objective Feedback:
- Observe Eye Movements and Basic Motion Behavior
> **Observation:** Use built-in eye tracking SDK to observe participants' eye movements and head orientations during the VR experience.
> **Interaction:** 
> Compare the duration and focus points of gaze pre- and post-design changes to identify shifts in attention — are participants more engaged with modified objects?
> Changes in Exploration Patterns: Examine if participants’ exploration patterns change due to design adjustments — for instance, do changes in light lead to longer stares at previously less-noticed objects?