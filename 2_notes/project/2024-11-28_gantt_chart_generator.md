---
date: 2024-11-28 
tags: 
    - project
---

# gantt_chart_generator

## code
```python
import matplotlib.pyplot as plt

from matplotlib.dates import date2num

import pandas as pd

from datetime import datetime, timedelta



# Define tasks and their durations

tasks = {

    "Requirement Analysis": ("2023-11-01", "2023-11-15"),

    "System Design": ("2023-11-16", "2023-11-30"),

    "Frontend Development": ("2023-12-01", "2023-12-20"),

    "Blockchain Development": ("2023-12-01", "2023-12-30"),

    "Server Development": ("2024-01-01", "2024-01-15"),

    "Integration Testing": ("2024-01-16", "2024-01-31"),

    "Final Deployment": ("2024-02-01", "2024-02-15"),

}



# Prepare data for Gantt chart

task_names = list(tasks.keys())

start_dates = [date2num(datetime.strptime(tasks[task][0], "%Y-%m-%d")) for task in tasks]

end_dates = [date2num(datetime.strptime(tasks[task][1], "%Y-%m-%d")) for task in tasks]

durations = [end - start for start, end in zip(start_dates, end_dates)]



# Plot Gantt chart

fig, ax = plt.subplots(figsize=(10, 6))

ax.barh(task_names, durations, left=start_dates, color='skyblue', edgecolor='black')



# Format the chart

ax.set_xlabel("Timeline")

ax.set_ylabel("Tasks")

ax.set_title("Preliminary Schedule - Gantt Chart")

ax.xaxis_date()

plt.grid(axis='x', linestyle='--', alpha=0.7)

plt.tight_layout()



plt.show()

```


## output 
![[output.png]]