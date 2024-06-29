### Experimental Design Plan

#### Fixed Workstation Sequence, Random Adjustment Conditions

Each participant follows a fixed workstation sequence (A -> B -> C), with different adjustment conditions randomly assigned at each workstation.

### Data Points and Number of Participants Calculation

- At least 10 data points (stream) per combination.
- 3 workstations × 3 adjustment conditions = 9 combinations.
- 10 data points per combination, totaling 90 data points.
- Each participant provides 3 data points.
- Number of required participants = 90 ÷ 3 = 30 participants.


## Prototype A: about 15 particiapants (statistical anlysis)
to address participant's hardware and software preferences
to check the feasibility of the experiment

## Prototype B: about 35 particiapants (ML anlysis)
to demonstrate crossed effects of participant's multisensory perception and cognitions




---

### Timestamp Explanation
The provided timestamps `1623658701.491566` and `1623658723.788441` are in Unix time format (also known as Epoch time), which represents the number of seconds that have elapsed since January 1, 1970 (00:00:00 UTC).

- **Start Timestamp**: `1623658701.491566`
  - This timestamp represents the start time of the experiment.
  - It can be converted to a human-readable format to know the exact date and time.

- **Stop Timestamp**: `1623658723.788441`
  - This timestamp represents the end time of the experiment.
  - Similarly, it can be converted to a human-readable format.


### Converting Unix Time to Human-Readable Format

You can convert these Unix timestamps to a human-readable format using Python:

```python
import datetime

# Define the Unix timestamps
start_timestamp = 1623658701.491566
stop_timestamp = 1623658723.788441

# Convert to human-readable format
start_time = datetime.datetime.fromtimestamp(start_timestamp)
stop_time = datetime.datetime.fromtimestamp(stop_timestamp)

print("Start Time:", start_time)
print("Stop Time:", stop_time)
```