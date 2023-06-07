Get-CMTaskSequence
------------------




### Synopsis
Get a task sequence.



---


### Description

Use this cmdlet to get a Configuration Manager task sequence. You typically use a task sequence to deploy an OS to a client, but you can use them for various purposes. To create a task sequence, use the New-CMTaskSequence (New-CMTaskSequence.md) cmdlet, or the Configuration Manager console. For more information, see [Manage task sequences to automate tasks](/mem/configmgr/osd/deploy-use/manage-task-sequences-to-automate-tasks).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequence](New-CMTaskSequence)



* [Set-CMTaskSequence](Set-CMTaskSequence)



* [Copy-CMTaskSequence](Copy-CMTaskSequence)



* [Import-CMTaskSequence](Import-CMTaskSequence)



* [Export-CMTaskSequence](Export-CMTaskSequence)



* [Remove-CMTaskSequence](Remove-CMTaskSequence)



* [Manage task sequences to automate tasks](Manage task sequences to automate tasks)





---


### Examples
#### Example 1: Get a task sequence by name
```PowerShell
Get-CMTaskSequence -Name "Upgrade to Windows 10 latest"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specify the name of a task sequence to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TaskSequencePackageId**

Specify the package ID of the task sequence to get. This value is a standard package ID, for example, `XYZ007C0`.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|true    |named   |False        |PackageId<br/>Id|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_TaskSequence_Step


* IResultObject#SMS_TaskSequence_Step






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_Step server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_step-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMTaskSequence [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
```PowerShell
Get-CMTaskSequence [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -TaskSequencePackageId <String> [<CommonParameters>]
```
