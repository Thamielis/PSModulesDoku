Remove-CMBaseline
-----------------




### Synopsis
Remove a configuration baseline.



---


### Description

Use this cmdlet to remove a configuration baseline. Before you can remove a configuration baseline, remove all references to it.



After you remove a configuration baseline, Configuration Manager removes the configuration baseline from the collection of devices to which you deployed it, and Configuration Manager no longer assesses their compliance with the configuration baseline.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMBaseline](Disable-CMBaseline)



* [Enable-CMBaseline](Enable-CMBaseline)



* [Export-CMBaseline](Export-CMBaseline)



* [Get-CMBaseline](Get-CMBaseline)



* [Import-CMBaseline](Import-CMBaseline)



* [New-CMBaseline](New-CMBaseline)



* [Set-CMBaseline](Set-CMBaseline)



* [Get-CMBaselineXMLDefinition](Get-CMBaselineXMLDefinition)



* [Get-CMBaselineSummarizationSchedule](Get-CMBaselineSummarizationSchedule)





---


### Examples
#### Example 1: Remove a configuration baseline by name
```PowerShell
Remove-CMBaseline -Name "BLConfigContoso02"
```

#### Example 2: Remove a dependent baseline
```PowerShell
$id = "16777366"
Set-CMBaseline -Name "Accounting department baseline" -RemoveBaseline $id
Remove-CMBaseline -Id $id -Force
```
If you don't first remove a baseline as configuration data from dependent baselines, this cmdlet returns the following error: `The configuration item cannot be deleted because there are dependent items in use.`


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the CI_ID of the configuration baseline to remove. For example, `16777516`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify a configuration baseline object to remove. To get this object, use the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specify the name of the configuration baseline to remove.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



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
Remove-CMBaseline [-Id] <Int32> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBaseline [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMBaseline [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
