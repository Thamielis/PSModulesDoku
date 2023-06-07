New-CMTSStepDownloadPackageContent
----------------------------------




### Synopsis
Create a Download Package Content step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Download Package Content step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [Task sequence steps: Download package content](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_DownloadPackageContent).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepDownloadPackageContent](Get-CMTSStepDownloadPackageContent)



* [Remove-CMTSStepDownloadPackageContent](Remove-CMTSStepDownloadPackageContent)



* [Set-CMTSStepDownloadPackageContent](Set-CMTSStepDownloadPackageContent)



* [Task sequence steps: Download package content](Task sequence steps: Download package content)





---


### Examples
#### Example 1: Create a task sequence step with condition and add to a group
```PowerShell
$TaskSequenceName = "Module - Download Driver Packages"
$Model = "Latitude E7470"
$GroupName = "Dell Drivers"
$ContentPackage = Get-CMPackage -Fast -Name "Driver Dell Latitude E7470"
$StepName = $ContentPackage.Name
$ConditionQuery = "Select * From Win32_ComputerSystem Where Model = `"$Model`""
$StepCondition = New-CMTSStepConditionQueryWMI -Namespace "root\cimv2" -Query $ConditionQuery

$PackageStep = New-CMTSStepDownloadPackageContent -AddPackage $ContentPackage -Name $StepName -LocationOption TaskSequenceWorkingFolder -DestinationVariable "DRIVERS" -Condition $StepCondition

Set-CMTaskSequenceGroup -TaskSequenceName $TaskSequenceName -StepName $GroupName -AddStep $PackageStep -InsertStepStartIndex 1
```



---


### Parameters
#### **AddPackage**

Specify one or more package objects to use with the step. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases    |
|-------------------|--------|--------|-------------|-----------|
|`[IResultObject[]]`|true    |named   |False        |AddPackages|



#### **Condition**

Specify a condition object to use with this step. To get a condition object, use one of the step condition cmdlets. For example, New-CMTSStepConditionQueryWMI (New-CMTSStepConditionQueryWMI.md).






|Type               |Required|Position|PipelineInput|Aliases   |
|-------------------|--------|--------|-------------|----------|
|`[IResultObject[]]`|false   |named   |False        |Conditions|



#### **ContinueDownload**

Set this parameter to `true` to continue downloading other packages in the list if a package download fails.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |ContinueDownloadOnError|



#### **ContinueOnError**

Add this parameter to enable the step option Continue on error . When you enable this option, if the step fails, the task sequence continues.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Description**

Specify an optional description for this task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DestinationVariable**

Use this parameter to save the package's path into a custom task sequence variable.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |DestinationVariableName|



#### **Disable**

Add this parameter to disable this task sequence step.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |DisableThisStep|



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



#### **LocationOption**

Specify one of the following values for where the task sequence saves the package:


* `TaskSequenceWorkingFolder`: Use the task sequence working directory, which is also referred to as the task sequence cache.


* `ClientCache`: Use the Configuration Manager client cache. By default, this path is `%WinDir%\ccmcache`.


* `CustomPath`: The task sequence engine first downloads the package to the task sequence working directory. It then moves the content to this path you specify. The task sequence engine appends the path with the package ID. When you use this option, set the path with the Path parameter.



Valid Values:

* TaskSequenceWorkingFolder
* ClientCache
* CustomPath






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[LocationType]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **Path**

When you specify `-LocationOption CustomPath`, use this parameter to specify the local path to save the package content. The task sequence engine appends the path with the package ID.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |DestinationCustomPath|



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
* IResultObject#SMS_TaskSequence_DownloadPackageContentAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_DownloadPackageContentAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_downloadpackagecontentaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepDownloadPackageContent -AddPackage <IResultObject[]> [-Condition <IResultObject[]>] [-ContinueDownload <Boolean>] [-ContinueOnError] [-Description <String>] [-DestinationVariable <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-LocationOption {TaskSequenceWorkingFolder | ClientCache | CustomPath}] -Name <String> [-Path <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
