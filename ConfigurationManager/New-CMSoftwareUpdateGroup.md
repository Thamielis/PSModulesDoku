New-CMSoftwareUpdateGroup
-------------------------




### Synopsis
Creates a software update group.



---


### Description

The New-CMSoftwareUpdateGroup cmdlet creates a software update group for Configuration Manager. A software update group is a collection of one or more software updates. You can add software updates to a software update group and then deploy the group to clients. After you deploy a software update group, you can add new software updates to the group and Configuration Manager automatically deploys them.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareUpdateGroup](Get-CMSoftwareUpdateGroup)



* [Remove-CMSoftwareUpdateGroup](Remove-CMSoftwareUpdateGroup)



* [Set-CMSoftwareUpdateGroup](Set-CMSoftwareUpdateGroup)





---


### Examples
#### Example 1: Create a software update group
```PowerShell
PS XYZ:\> New-CMSoftwareUpdateGroup -Name "ClientUpdateGroup01" -UpdateID 100027 -Description "Client software update group 01 for Accounts Payable"
```
This command creates a software update group named ClientUpdateGroup01 that includes the software update that has the update ID 100027.


---


### Parameters
#### **Description**

Specifies a description of a software update group.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



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

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type               |Required|Position|PipelineInput |Aliases                           |
|-------------------|--------|--------|--------------|----------------------------------|
|`[IResultObject[]]`|false   |named   |True (ByValue)|SoftwareUpdates<br/>SoftwareUpdate|



#### **Name**

Specifies a name of a software update group.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **SoftwareUpdateId**








|Type        |Required|Position|PipelineInput|Aliases          |
|------------|--------|--------|-------------|-----------------|
|`[String[]]`|false   |named   |False        |SoftwareUpdateIds|



#### **SoftwareUpdateName**








|Type        |Required|Position|PipelineInput|Aliases            |
|------------|--------|--------|-------------|-------------------|
|`[String[]]`|false   |named   |False        |SoftwareUpdateNames|



#### **UpdateId**

Specifies an array of IDs of software updates.






|Type       |Required|Position|PipelineInput|Aliases|
|-----------|--------|--------|-------------|-------|
|`[Int32[]]`|false   |named   |False        |Updates|



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* IResultObject#SMS_AuthorizationList






---


### Notes




---


### Syntax
```PowerShell
New-CMSoftwareUpdateGroup [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject[]>] -Name <String> [-SoftwareUpdateId <String[]>] [-SoftwareUpdateName <String[]>] [-UpdateId <Int32[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
