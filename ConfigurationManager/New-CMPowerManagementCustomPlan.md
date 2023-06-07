New-CMPowerManagementCustomPlan
-------------------------------




### Synopsis
Creates a custom power management plan.



---


### Description

The New-CMPowerManagementCustomPlan cmdlet creates a custom power management plan.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMCollectionPowerManagement](Set-CMCollectionPowerManagement)





---


### Examples
#### Example 1: Create parameters for a custom power management plan and store them in a variable
```PowerShell
PS XYZ:\>$PlanParams = @{
    Name = "test"
    Description = "comments"
    DisplayOffMinAC = 20
    DisplayOffMinDC = 20
    SleepMinAC = 65
    SleepMinDC = 20
    RequirePasswordOnWakeAC = $true
    RequirePasswordOnWakeDC = $false
    PowerButtonAC = "None"
    PowerButtonDC = "Sleep"
    StartButtonAC = "Hibernate"
    StartButtonDC = "Sleep"
    SleepButtonAC= "None"
    SleepButtonDC = "Sleep"
    LidDownAC = "None"
    LidDownDC = "Sleep"
    HardDiskIdleMinAC = 25
    HardDiskIdleMinDC = 10
    HibernateMinAC = 10
    HibernateMinDC = 5
    LowBatteryAC = "None"
    LowBatteryDC = "Sleep"
    CriticalBatteryAC = "None"
    CriticalBatteryDC = "ShutDown"
    AllowHybridSleepAC = $false
    AllowHybridSleepDC = $true
    AllowStandbyAC= $false
    AllowStandbyDC = $true
    SleepIdlePctDC = 10
    SleepIdlePctAC = 15
    WakeOnTimerAC = $true
    WakeOnTimerDC = $false
}
```
This command creates an array of parameters and their settings for a custom power management plan, and then stores the array in the $PlanParams variable. This variable can now be used to create a custom plan.
#### Example 2: Create a custom peak power management plan to configure a device collection
```PowerShell
PS XYZ:\> $PeakPlan = New-CMPowerManagementCustomPlan -Peak @planParams
PS XYZ:\> Set-CMCollectionPowerManagement -CollectionName "deviceCol1" -PeakPlan $PeakPlan
```
The first command uses the parameters set in Example 1 to create a custom peak power management plan object, which it then stores in the $PeakPlan variable.


The second command uses the custom plan stored in $PeakPlan to configure the power management settings for the device collection named deviceCol01.
#### Example 3: Create a custom non-peak power management plan to configure a device collection
```PowerShell
PS XYZ:\> $NonPeakPlan = New-CMPowerManagementCustomPlan -NonPeak @planParams
PS XYZ:\> Set-CMCollectionPowerManagement -CollectionName "deviceCol2" -NonPeakPlan $NonPeakPlan
```
The first command uses the parameters set in Example 1 to create a custom non-peak power management plan object, which it then stores in the $NonPeakPlan variable.


The second command uses the custom plan stored in $NonPeakPlan to configure the power management settings for the device collection named deviceCol02.


---


### Parameters
#### **AllowHybridSleepAC**

Indicates whether Windows saves a hibernation file when entering sleep when the device is plugged in. A hibernation file can be used to restore the computer's state in the event of power loss while it has entered sleep.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowHybridSleepDC**

Indicates whether Windows saves a hibernation file when entering sleep when the device is running on battery power. A hibernation file can be used to restore the computer's state in the event of power loss while it has entered sleep.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowStandbyAC**

Indicates whether to allow the computer to be on standby when the device is plugged in. This still consumes some power, but enables the computer to wake faster.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowStandbyDC**

Indicates whether to allow the computer to be on standby when the device running on battery power. This still consumes some power, but enables the computer to wake faster.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CriticalBatteryAC**

Specifies the action to take when the computer's battery reaches the specified critical battery notification when the device is plugged in. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **CriticalBatteryDC**

Specifies the action to take when the computer's battery reaches the specified critical battery notification when the device is running on batter power. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **Description**

Specifies a description for the power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisplayOffMinAC**

Specifies the length of time, in minutes, that the computer must be inactive before the display is turned off when the device is plugged in.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DisplayOffMinDC**

Specifies the length of time, in minutes, that the computer must be inactive before the display is turned off when the device running on battery power.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **HardDiskIdleMinAC**

Specifies the length of time, in minutes, that the computer's hard disk must be inactive before it is turned off when the device is plugged in.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **HardDiskIdleMinDC**

Specifies the length of time, in minutes, that the computer's hard disk must be inactive before it is turned off when the device is running on battery power.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **HibernateMinAC**

Specifies the length of time, in minutes, that the computer must be inactive before it enters hibernate when the device is plugged in.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **HibernateMinDC**

Specifies the length of time, in minutes, that the computer must be inactive before it enters hibernate when the device is running on battery power.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **LidDownAC**

Specifies the action that occurs when the user closes the lid of a portable computer when the device is plugged in. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **LidDownDC**

Specifies the action that occurs when the user closes the lid of a portable computer when the device is running on battery power. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **LowBatteryAC**

Specifies the action that occurs when the computer's battery reaches the specified low battery notification level when the device is plugged in. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **LowBatteryDC**

Specifies the action that occurs when the computer's battery reaches the specified low battery notification level when the device is running on battery power. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **Name**

Specifies a name for the power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NoAllowStandby**

Indicates that the "Allow standby state when sleeping action" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoCriticalBattery**

Indicates that the "Critical battery action" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoDisplayOff**

Indicates that the "Turn off display after (minutes)" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoHardDiskIdle**

Indicates that the "Turn off hard disk after (minutes)" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoHibernate**

Indicates that the "Hibernate after (minutes)" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoHybridSleep**

Indicates that the "Allow hybrid sleep" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoLidDown**

Indicates that the "Lid close action" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoLowBattery**

Indicates that the "Low battery action" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NonPeak**

Indicates that this is a non-peak plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **NoPowerButton**

Indicates that the "Power button action" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoRequirePasswordOnWake**

Indicates that the "Require a password on wakeup" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoSleep**

Indicates that the "Sleep after (minutes)" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoSleepButton**

Indicates that the "Sleep button action" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoSleepIdle**

Indicates that the "Required idleness to sleep (%)" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoStartButton**

Indicates that the "Start menu power button" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **NoWakeOnTimer**

Indicates that the "Enable Windows wake up timer for desktop computers" property is not included in this power management plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Peak**

Indicates that this is a peak plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **PowerButtonAC**

Specifies the action that is taken when the computer's power button is pressed when the device is plugged in. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **PowerButtonDC**

Specifies the action that is taken when the computer's power button is pressed when the device is running on battery power. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **RequirePasswordOnWakeAC**

Indicates whether a password is required to unlock the computer when it enters wake from sleep when the device is plugged in.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RequirePasswordOnWakeDC**

Indicates whether a password is required to unlock the computer when it enters wake from sleep when the device is running on battery power.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SleepButtonAC**

Specifies the action that occurs when you press the computer's Sleep button when the device is plugged in. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **SleepButtonDC**

Specifies the action that occurs when you press the computer's Sleep button when the device is running on battery power. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **SleepIdlePctAC**

Specifies the percentage of idle time on the computer processor time required for the computer to enter sleep when the device is plugged in.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SleepIdlePctDC**

Specifies the percentage of idle time on the computer processor time required for the computer to enter sleep when the device is running on battery power.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SleepMinAC**

Specifies the length of time, in minutes, that the computer must be in active before it enters sleep when the device is plugged in.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SleepMinDC**

Specifies the length of time, in minutes, that the computer must be in active before it enters sleep when the device is running on battery power.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **StartButtonAC**

Specifies the action that occurs when you press the computer's Start menu power button when the device is plugged in. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **StartButtonDC**

Specifies the action that occurs when you press the computer's Start menu power button when the device is running on battery power. Valid values are:


* None


* Sleep


* Hibernate


* Shutdown



Valid Values:

* None
* Sleep
* Hibernate
* Shutdown






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PowerSettingAction]`|false   |named   |False        |



#### **WakeOnTimerAC**

Indicates whether the build-in Windows timer is enabled when the device is plugged in. Power management can use the Windows timer to wake a desktop computer. When a desktop computer is woken by using the Windows wake up timer, it will remain awake for 10 minutes by default to allow time for the computer to install any updates or to receive policy.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WakeOnTimerDC**

Indicates whether the build-in Windows timer is enabled when the device is running on battery power. Power management can use the Windows timer to wake a desktop computer. When a desktop computer is woken by using the Windows wake up timer, it will remain awake for 10 minutes by default to allow time for the computer to install any updates or to receive policy.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.AdminConsole.CollectionProperty.PowerSchema






---


### Notes




---


### Syntax
```PowerShell
New-CMPowerManagementCustomPlan [-AllowHybridSleepAC <Boolean>] [-AllowHybridSleepDC <Boolean>] [-AllowStandbyAC <Boolean>] [-AllowStandbyDC <Boolean>] [-CriticalBatteryAC {None | Sleep | Hibernate | Shutdown}] [-CriticalBatteryDC {None | Sleep | Hibernate | Shutdown}] [-Description <String>] [-DisableWildcardHandling] [-DisplayOffMinAC <Int32>] [-DisplayOffMinDC <Int32>] [-ForceWildcardHandling] [-HardDiskIdleMinAC <Int32>] [-HardDiskIdleMinDC <Int32>] [-HibernateMinAC <Int32>] [-HibernateMinDC <Int32>] [-LidDownAC {None | Sleep | Hibernate | Shutdown}] [-LidDownDC {None | Sleep | Hibernate | Shutdown}] [-LowBatteryAC {None | Sleep | Hibernate | Shutdown}] [-LowBatteryDC {None | Sleep | Hibernate | Shutdown}] [-Name <String>] [-NoAllowStandby] [-NoCriticalBattery] [-NoDisplayOff] [-NoHardDiskIdle] [-NoHibernate] [-NoHybridSleep] [-NoLidDown] [-NoLowBattery] -NonPeak [-NoPowerButton] [-NoRequirePasswordOnWake] [-NoSleep] [-NoSleepButton] [-NoSleepIdle] [-NoStartButton] [-NoWakeOnTimer] [-PowerButtonAC {None | Sleep | Hibernate | Shutdown}] [-PowerButtonDC {None | Sleep | Hibernate | Shutdown}] [-RequirePasswordOnWakeAC <Boolean>] [-RequirePasswordOnWakeDC <Boolean>] [-SleepButtonAC {None | Sleep | Hibernate | Shutdown}] [-SleepButtonDC {None | Sleep | Hibernate | Shutdown}] [-SleepIdlePctAC <Int32>] [-SleepIdlePctDC <Int32>] [-SleepMinAC <Int32>] [-SleepMinDC <Int32>] [-StartButtonAC {Sleep | Hibernate | Shutdown}] [-StartButtonDC {Sleep | Hibernate | Shutdown}] [-WakeOnTimerAC <Boolean>] [-WakeOnTimerDC <Boolean>] [<CommonParameters>]
```
```PowerShell
New-CMPowerManagementCustomPlan [-AllowHybridSleepAC <Boolean>] [-AllowHybridSleepDC <Boolean>] [-AllowStandbyAC <Boolean>] [-AllowStandbyDC <Boolean>] [-CriticalBatteryAC {None | Sleep | Hibernate | Shutdown}] [-CriticalBatteryDC {None | Sleep | Hibernate | Shutdown}] [-Description <String>] [-DisableWildcardHandling] [-DisplayOffMinAC <Int32>] [-DisplayOffMinDC <Int32>] [-ForceWildcardHandling] [-HardDiskIdleMinAC <Int32>] [-HardDiskIdleMinDC <Int32>] [-HibernateMinAC <Int32>] [-HibernateMinDC <Int32>] [-LidDownAC {None | Sleep | Hibernate | Shutdown}] [-LidDownDC {None | Sleep | Hibernate | Shutdown}] [-LowBatteryAC {None | Sleep | Hibernate | Shutdown}] [-LowBatteryDC {None | Sleep | Hibernate | Shutdown}] [-Name <String>] [-NoAllowStandby] [-NoCriticalBattery] [-NoDisplayOff] [-NoHardDiskIdle] [-NoHibernate] [-NoHybridSleep] [-NoLidDown] [-NoLowBattery] [-NoPowerButton] [-NoRequirePasswordOnWake] [-NoSleep] [-NoSleepButton] [-NoSleepIdle] [-NoStartButton] [-NoWakeOnTimer] -Peak [-PowerButtonAC {None | Sleep | Hibernate | Shutdown}] [-PowerButtonDC {None | Sleep | Hibernate | Shutdown}] [-RequirePasswordOnWakeAC <Boolean>] [-RequirePasswordOnWakeDC <Boolean>] [-SleepButtonAC {None | Sleep | Hibernate | Shutdown}] [-SleepButtonDC {None | Sleep | Hibernate | Shutdown}] [-SleepIdlePctAC <Int32>] [-SleepIdlePctDC <Int32>] [-SleepMinAC <Int32>] [-SleepMinDC <Int32>] [-StartButtonAC {Sleep | Hibernate | Shutdown}] [-StartButtonDC {Sleep | Hibernate | Shutdown}] [-WakeOnTimerAC <Boolean>] [-WakeOnTimerDC <Boolean>] [<CommonParameters>]
```
