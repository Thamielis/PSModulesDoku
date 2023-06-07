Set-CMCollectionPowerManagement
-------------------------------




### Synopsis
Configures power management settings for a device collection.



---


### Description

The Set-CMCollectionPowerManagement cmdlet configures power management settings for a device collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMPowerManagementSchema](Get-CMPowerManagementSchema)



* [New-CMPowerManagementCustomPlan](New-CMPowerManagementCustomPlan)





---


### Examples
#### Example 1: Configure power management settings by using the pipeline
```PowerShell
PS XYZ:\> Get-CMCollection -Name "DeviceCol1" | Set-CMCollectionPowerManagement -NeverApply -PassThru
```
This command gets the device collection object named DeviceCol1 and uses the pipeline operator to pass the object to Set-CMCollectionPowerManagement . Set-CMCollectionPowerManagagement configures deviceCol1 to never apply power management settings to the computers in that collection.
#### Example 2: Configure power management settings by name
```PowerShell
PS XYZ:\> Set-CMCollectionPowerManagement -CollectionName "DeviceCol2" -Apply -PeakStartTime 8:00am -PeakEndTime 6:00pm -PeakPlan (Get-CMPowerManagementSchema -Peak -Name "Balanced (ConfigMgr)") -NonPeakPlan (Get-CMPowerManagementSchema -NonPeak -Name "Power Saver (ConfigMgr)") -WakeupTime 4:00am
```
This command specifies power management settings for the device collection DeviceCol2. During the peak hours of 8:00 AM to 6:00 PM, the peak power management plan named Balanced (ConfigMgr) is in effect. During non-peak hours, the non-peak power management plan named Power Saver (ConfigMgr) is in effect. The Windows timer is set to wake desktop computers install scheduled updates or software installations at 4:00 AM.


---


### Parameters
#### **Apply**

Indicates that power management settings can be set for a specified device collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **CollectionId**

Specifies the collection ID of the device collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specifies the name of the device collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a device collection object. To obtain a device collection object, use the Get-CMCollection or the Get-CMDeviceCollection cmdlets.






|Type             |Required|Position|PipelineInput |Aliases                          |
|-----------------|--------|--------|--------------|---------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection<br/>CollectionSettings|



#### **NeverApply**

Indicates that power management settings will never be applied to computers in the specified collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **None**

Indicates that no power management settings are set for the specified collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **NonPeakPlan**

Specifies a power management plan object for non-peak or non-business hours. To obtain a power plan object , use the Get-CMPowerManagementSchema cmdlet. To create a customized power plan, use New-CMPowerManagementCustomPlan cmdlet.






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[PowerSchema]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PeakEndTime**

Specifies the end time for peak hours.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **PeakPlan**

Specifies a power management plan object for peak or business hours. To obtain a power plan object, use Get-CMPowerManagementSchema cmdlet. To create a customized power plan, use New-CMPowerManagementCustomPlan cmdlet.






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[PowerSchema]`|false   |named   |False        |



#### **PeakStartTime**

Specifies the start time for peak hours.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[DateTime]`|false   |named   |False        |PeakStartHour|



#### **WakeupTime**

Specifies a time when the Windows timer wakes a desktop computer from sleep or hibernate to install scheduled updates or software installations.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMCollectionPowerManagement [-Apply] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NonPeakPlan <PowerSchema>] [-PassThru] [-PeakEndTime <DateTime>] [-PeakPlan <PowerSchema>] [-PeakStartTime <DateTime>] [-WakeupTime <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement [-Apply] -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NonPeakPlan <PowerSchema>] [-PassThru] [-PeakEndTime <DateTime>] [-PeakPlan <PowerSchema>] [-PeakStartTime <DateTime>] [-WakeupTime <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement [-Apply] -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-NonPeakPlan <PowerSchema>] [-PassThru] [-PeakEndTime <DateTime>] [-PeakPlan <PowerSchema>] [-PeakStartTime <DateTime>] [-WakeupTime <DateTime>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -None [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -NeverApply [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -None [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -NeverApply [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -None [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionPowerManagement [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -NeverApply [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
