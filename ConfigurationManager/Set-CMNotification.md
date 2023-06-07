Set-CMNotification
------------------




### Synopsis
{{ Fill in the Synopsis }}



---


### Description

{{ Fill in the Description }}



---


### Examples
#### Example 1
```PowerShell
PS C:\> {{ Add example code here }}
```
{{ Add example description here }}


---


### Parameters
#### **DisableWildcardHandling**

{{ Fill DisableWildcardHandling Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

{{ Fill ForceWildcardHandling Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NotificationTasks**

{{ Fill NotificationTasks Description }}






|Type                      |Required|Position|PipelineInput|Aliases    |
|--------------------------|--------|--------|-------------|-----------|
|`[NotificationCollection]`|true    |named   |False        |InputObject|



#### **Period**

{{ Fill Period Description }}



Valid Values:

* OneHour
* OneDay
* OneWeek
* OneMonth






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SnoozePeriod]`|false   |named   |False        |



#### **SetStatus**

{{ Fill SetStatus Description }}



Valid Values:

* Snooze
* Dismiss






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[NotificationOption]`|true    |named   |False        |



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMNotification [-DisableWildcardHandling] [-ForceWildcardHandling] -NotificationTasks <NotificationCollection> [-Period {OneHour | OneDay | OneWeek | OneMonth}] -SetStatus {Snooze | Dismiss} [-Confirm] [-WhatIf] [<CommonParameters>]
```
