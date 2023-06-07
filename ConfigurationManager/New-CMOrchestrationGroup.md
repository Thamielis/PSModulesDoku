New-CMOrchestrationGroup
------------------------




### Synopsis
Create a new orchestration group.



---


### Description

Use this cmdlet to create a new orchestration group.



Use orchestration groups to better control the deployment of software updates to devices. You may need to carefully manage updates for specific workloads, or automate behaviors in between. For more information, see Create and use orchestration groups in Configuration Manager (/mem/configmgr/sum/deploy-use/create-orchestration-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOrchestrationGroup](Get-CMOrchestrationGroup)



* [Invoke-CMOrchestrationGroup](Invoke-CMOrchestrationGroup)



* [Remove-CMOrchestrationGroup](Remove-CMOrchestrationGroup)



* [Set-CMOrchestrationGroup](Set-CMOrchestrationGroup)



* [About orchestration groups in Configuration Manager](About orchestration groups in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
$parameters = @{
  Name = "IT servers"
  SiteCode = "XYZ"
  Description = "An OG for IT servers with default settings"
  OrchestrationType = "Number"
  OrchestrationValue = 1
  OrchestrationTimeOutMin = 720
  MaxLockTimeOutMin = 60
  PreScript = "Write-Host 'Pre-install script'"
  PreScriptTimeoutSec = 120
  PostScript = "Write-Host 'POST-install script'"
  PostScriptTimeoutSec = 120
  MemberResourceIds = $device1.ResourceID, $device2.ResourceID
}

New-CMOrchestrationGroup @parameters
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
|`[Int32[]]`|true    |named   |False        |MogMembers|



#### **Name**

Specify a name for the orchestration group.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|true    |0       |False        |OrchestrationGroupName|



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
|`[OrchestrationTypeValue]`|true    |named   |False        |



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



#### **SiteCode**

Specify the site code for this orchestration group and its members.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
* IResultObject#SMS_MachineOrchestrationGroup






---


### Notes
This cmdlet returns an object for the SMS_MachineOrchestrationGroup WMI class.



---


### Syntax
```PowerShell
New-CMOrchestrationGroup [-Name] <String> [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaxLockTimeOutMin <Int32>] -MemberResourceIds <Int32[]> [-OrchestrationTimeOutMin <Int32>] -OrchestrationType {Number | Percentage | Sequence} [-OrchestrationValue <Int32>] [-PostScript <String>] [-PostScriptTimeoutSec <Int32>] [-PreScript <String>] [-PreScriptTimeoutSec <Int32>] -SiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
