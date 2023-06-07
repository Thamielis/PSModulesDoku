Set-CMOrchestrationGroup
------------------------




### Synopsis
Configure an orchestration group.



---


### Description

Use this cmdlet to configure an orchestration group.



Use orchestration groups to better control the deployment of software updates to devices. You may need to carefully manage updates for specific workloads, or automate behaviors in between. For more information, see Create and use orchestration groups in Configuration Manager (/mem/configmgr/sum/deploy-use/create-orchestration-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOrchestrationGroup](Get-CMOrchestrationGroup)



* [Invoke-CMOrchestrationGroup](Invoke-CMOrchestrationGroup)



* [New-CMOrchestrationGroup](New-CMOrchestrationGroup)



* [Remove-CMOrchestrationGroup](Remove-CMOrchestrationGroup)



* [About orchestration groups in Configuration Manager](About orchestration groups in Configuration Manager)





---


### Examples
#### Example 1: Change the type and specify the sequence
```PowerShell
$og = Get-CMOrchestrationGroup -Name "IT servers"

$devices = @()
foreach ( $id in $og.MOGMembers ) {
  $devices += Get-CMDevice -Id $id -Fast
}

$sortedIDs = ( $devices | Sort-Object -Property Name | Select-Object ResourceId ).ResourceId

$parameters = @{
  InputObject = $og
  Description = "Change type and sequence"
  OrchestrationType = "Sequence"
  MemberResourceIds = $sortedIDs
}

Set-CMOrchestrationGroup @parameters
```
This example shows how to do a programmatic sort of the existing members. If the membership of the orchestration group doesn't change, it uses the following general process:


1. Use the existing member resource IDs. 1. Get more information about each resource. 1. Sort the list on that information. 1. Return the resource IDs for the newly sorted list.


This example uses Get-CMDevice to get more information, but you can replace it with any cmdlet that uses the device resource ID as an input. You can also replace the sorting mechanism with another function.
#### Example 2: Get script content from a file
```PowerShell
$postScript - Get-Content -Path "D:\Scripts\OG\Post1.ps1"
Set-CMOrchestrationGroup -InputObject $og -PostScript $postScript
```



---


### Parameters
#### **Description**

Specify an optional description for the orchestration group to help identify it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **Id**

Specify the ID of orchestration group to configure. This value is the MOGID property, which is an integer. For example, `16777217`.






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|true    |0       |False        |MOGID  |



#### **InputObject**

Specify an object for the orchestration group to configure. To get this object, use the Get-CMOrchestrationGroup (Get-CMOrchestrationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases           |
|-----------------|--------|--------|--------------|------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|OrchestrationGroup|



#### **MaxLockTimeOutMin**

Specify an integer value for the orchestration group member timeout in minutes. This value is the time limit for a single device in the group to install the updates.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MemberResourceIds**

Specify an array of resource IDs for the devices to add as members of this orchestration group. The resource ID is an integer, for example, `16777220`. It's the ResourceId property on a device or resource object. To get a device object, use the Get-CMDevice (Get-CMDevice.md) or [Get-CMResource](Get-CMResource.md)cmdlets.


When you set the OrchestrationType parameter to `Sequence`, use this parameter to determine the order.






|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Int32[]]`|false   |named   |False        |MogMembers|



#### **Name**

Specify the name of the orchestration group to configure.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|true    |0       |False        |OrchestrationGroupName|



#### **NewName**

Specify a new name for this orchestration group. Use this parameter to rename the orchestration group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OrchestrationTimeOutMin**

Specify an integer value for the orchestration group timeout in minutes. This value is the time limit for all group members to install the updates.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **OrchestrationType**

Specify one of the following values for the type of orchestration group:


* `Number`: Allow a number of the devices to update at the same time. Use this setting to always limit to a specific number of devices, whatever the overall size of the orchestration group. To specify the number of devices, use the OrchestrationValue parameter.


* `Percentage`: Allow a percentage of the devices to update at the same time. Use this setting to allow for future flexibility of the size of the orchestration group. To specify the percentage, use the OrchestrationValue parameter.


* `Sequence`: Explicitly define the order in which devices run the software update deployment. The order is determined by the sort of the device resource IDs in the MemberResourceIds parameter.



Valid Values:

* Number
* Percentage
* Sequence






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[OrchestrationTypeValue]`|false   |named   |False        |



#### **OrchestrationValue**

Specify an integer for the number or percentage of devices to update at the same time. Use this parameter when you set the OrchestrationType parameter to `Number` or `Percentage`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PostScript**

Specify the PowerShell script to run on each device after the deployment runs and the device restarts, if required.


This string value is the text of the script itself. If you have a script in a file that you want to use, first read it into a variable. For example, use the built-in Get-Content (/powershell/module/microsoft.powershell.management/get-content)cmdlet.


The scripts should return a value of `0` for success. Any non-zero value is considered a script failure. You can't use a script with parameters. The maximum script length is 50,000 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PostScriptTimeoutSec**

Specify the integer value for the allowed time in seconds for the post-script to run before it times out.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PreScript**

Specify the PowerShell script to run on each device before the deployment runs.


This string value is the text of the script itself. If you have a script in a file that you want to use, first read it into a variable. For example, use the built-in Get-Content (/powershell/module/microsoft.powershell.management/get-content)cmdlet.


The scripts should return a value of `0` for success. Any non-zero value is considered a script failure. You can't use a script with parameters. The maximum script length is 50,000 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PreScriptTimeoutSec**

Specify the integer value for the allowed time in seconds for the pre-script to run before it times out.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
* IResultObject#SMS_MachineOrchestrationGroup






---


### Notes
This cmdlet returns an object for the SMS_MachineOrchestrationGroup WMI class.



---


### Syntax
```PowerShell
Set-CMOrchestrationGroup [-Id] <Int32> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaxLockTimeOutMin <Int32>] [-MemberResourceIds <Int32[]>] [-NewName <String>] [-OrchestrationTimeOutMin <Int32>] [-OrchestrationType {Number | Percentage | Sequence}] [-OrchestrationValue <Int32>] [-PostScript <String>] [-PostScriptTimeoutSec <Int32>] [-PreScript <String>] [-PreScriptTimeoutSec <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOrchestrationGroup [-InputObject] <IResultObject> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaxLockTimeOutMin <Int32>] [-MemberResourceIds <Int32[]>] [-NewName <String>] [-OrchestrationTimeOutMin <Int32>] [-OrchestrationType {Number | Percentage | Sequence}] [-OrchestrationValue <Int32>] [-PostScript <String>] [-PostScriptTimeoutSec <Int32>] [-PreScript <String>] [-PreScriptTimeoutSec <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMOrchestrationGroup [-Name] <String> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaxLockTimeOutMin <Int32>] [-MemberResourceIds <Int32[]>] [-NewName <String>] [-OrchestrationTimeOutMin <Int32>] [-OrchestrationType {Number | Percentage | Sequence}] [-OrchestrationValue <Int32>] [-PostScript <String>] [-PostScriptTimeoutSec <Int32>] [-PreScript <String>] [-PreScriptTimeoutSec <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
