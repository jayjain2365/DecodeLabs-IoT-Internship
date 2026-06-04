# Task 4 – IoT Automation Logic

## Objective

To automate industrial safety actions based on sensor readings.

## Automation Rules

### Gas Detection

Condition:
Gas Value > Threshold

Action:

* Turn ON Fan
* Activate Buzzer
* Display Alert

### High Temperature

Condition:
Temperature > Threshold

Action:

* Turn ON Fan
* Display Warning

### Flame Detection

Condition:
Flame Detected

Action:

* Activate Emergency Alert
* Turn ON Red LED

## Code Snippet

```cpp
bool gasAlarm = (mqRaw > MQ_THRESHOLD);
bool tempAlarm = (t > TEMP_THRESHOLD);
bool flameAlarm = (flame == 0);

bool alarm = gasAlarm || tempAlarm || flameAlarm;

setRelay(alarm);
setBuzzer(alarm);
```
