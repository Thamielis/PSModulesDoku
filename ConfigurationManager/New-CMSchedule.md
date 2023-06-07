New-CMSchedule
--------------




### Synopsis
Create a Configuration Manager schedule token.



---


### Description

The New-CMSchedule cmdlet creates a schedule token in Configuration Manager. Create schedule tokens to schedule events with differing frequencies such as daily, weekly, and monthly.



To decode and encode schedule tokens into and from an interval string, use the Convert-CMSchedule (Convert-CMSchedule.md)cmdlet. You can then use the interval strings to set schedule properties when you define or modify Configuration Manager objects.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMSchedule](Convert-CMSchedule)





---


### Examples
#### Example 1: Create a schedule token
```PowerShell
$schedToken1 = New-CMSchedule -DayOfMonth 0 -Start "2020-08-05T17:46:03.7236084-07:00"
```

#### Example 2: Create an offset schedule
```PowerShell
$schedToken2 = New-CMSchedule -Start (Get-Date) -DayOfWeek Monday -WeekOrder Second -RecurCount 1 -OffsetDay 0
```

#### Example 3: Create a schedule to run daily
```PowerShell
New-CMSchedule -DurationInterval Days -DurationCount 0 -RecurInterval Days -RecurCount 1
```



---


### Parameters
#### **DayOfMonth**

Specifies the day of the month when the event occurs. Valid values range from 0 through 31. The default value is `0`, which indicates the last day of the month.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **DayOfWeek**

Specifies the day of the week when the event occurs.



Valid Values:

* Sunday
* Monday
* Tuesday
* Wednesday
* Thursday
* Friday
* Saturday






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[DayOfWeek]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DurationCount**

Specifies the number of days during which the scheduled event occurs. Valid values range from 0 through 31. The default value is `0`, which indicates that the scheduled action continues indefinitely.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **DurationInterval**

Specifies the time when the event occurs.



Valid Values:

* Minutes
* Hours
* Days






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[ScheduleInterval]`|true    |named   |False        |



#### **End**

Specifies the date and time when the scheduled event ends.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IsUtc**

Indicates that the time is Coordinated Universal Time (UTC).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **LastDayOfMonth**

Indicates that the event occurs monthly on the last day of the month.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **Nonrecurring**

Indicates that the scheduled event doesn't recur.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **OffsetDay**

Use this parameter to configure an offset such as monthly by weekday.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **RecurCount**

Specifies the number of recurrences of the scheduled event.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **RecurInterval**

Specifies the time when the scheduled event recurs.



Valid Values:

* Minutes
* Hours
* Days






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[ScheduleInterval]`|true    |named   |False        |



#### **ScheduleString**

Indicates that the schedule token is converted to an interval string.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Start**

Specifies the date and time when the scheduled event occurs.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **WeekOrder**

Specifies the week of the month when the event occurs. The default value is `Last` (0).



Valid Values:

* Last
* First
* Second
* Third
* Fourth






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[ScheduleWeekOrder]`|true    |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None





---


### Outputs
* IResultObject#SMS_ScheduleToken


* [String](https://learn.microsoft.com/en-us/dotnet/api/System.String)






---


### Notes




---


### Syntax
```PowerShell
New-CMSchedule -DayOfMonth <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsUtc] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfMonth <Int32> [-DisableWildcardHandling] -DurationCount <Int32> -DurationInterval {Minutes | Hours | Days} [-ForceWildcardHandling] [-IsUtc] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfMonth <Int32> [-DisableWildcardHandling] -End <DateTime> [-ForceWildcardHandling] [-IsUtc] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday} [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsUtc] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday} [-DisableWildcardHandling] -DurationCount <Int32> -DurationInterval {Minutes | Hours | Days} [-ForceWildcardHandling] [-IsUtc] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday} [-DisableWildcardHandling] -End <DateTime> [-ForceWildcardHandling] [-IsUtc] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday} [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsUtc] [-OffsetDay <Int32>] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] -WeekOrder {Last | First | Second | Third | Fourth} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday} [-DisableWildcardHandling] -DurationCount <Int32> -DurationInterval {Minutes | Hours | Days} [-ForceWildcardHandling] [-IsUtc] [-OffsetDay <Int32>] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] -WeekOrder {Last | First | Second | Third | Fourth} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule -DayOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday} [-DisableWildcardHandling] -End <DateTime> [-ForceWildcardHandling] [-IsUtc] [-OffsetDay <Int32>] [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] -WeekOrder {Last | First | Second | Third | Fourth} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] -DurationCount <Int32> -DurationInterval {Minutes | Hours | Days} [-ForceWildcardHandling] [-IsUtc] -Nonrecurring [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] -DurationCount <Int32> -DurationInterval {Minutes | Hours | Days} [-ForceWildcardHandling] [-IsUtc] -LastDayOfMonth [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] -DurationCount <Int32> -DurationInterval {Minutes | Hours | Days} [-ForceWildcardHandling] [-IsUtc] -RecurCount <Int32> -RecurInterval {Minutes | Hours | Days} [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] -End <DateTime> [-ForceWildcardHandling] [-IsUtc] -Nonrecurring [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] -End <DateTime> [-ForceWildcardHandling] [-IsUtc] -LastDayOfMonth [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] -End <DateTime> [-ForceWildcardHandling] [-IsUtc] -RecurCount <Int32> -RecurInterval {Minutes | Hours | Days} [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsUtc] -LastDayOfMonth [-RecurCount <Int32>] [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsUtc] -Nonrecurring [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSchedule [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsUtc] -RecurCount <Int32> -RecurInterval {Minutes | Hours | Days} [-ScheduleString] [-Start <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
