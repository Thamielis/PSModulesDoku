Export-CMBaseline
-----------------




### Synopsis
Export a configuration baseline.



---


### Description

Use this cmdlet to export a configuration baseline to a cabinet (`.cab`) file. Configuration data is converted to desired configuration management (DCM) digest XML files.



You can then import it to the same or a different Configuration Manager site. You can use this export/import process to backup custom configuration data, or for development lifecycle. For example, you develop a new configuration baseline in a lab environment. Export the baseline from the test environment, and then import it into the production hierarchy.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMBaseline](Disable-CMBaseline)



* [Enable-CMBaseline](Enable-CMBaseline)



* [Get-CMBaseline](Get-CMBaseline)



* [Import-CMBaseline](Import-CMBaseline)



* [New-CMBaseline](New-CMBaseline)



* [Remove-CMBaseline](Remove-CMBaseline)



* [Set-CMBaseline](Set-CMBaseline)



* [Get-CMBaselineXMLDefinition](Get-CMBaselineXMLDefinition)



* [Get-CMBaselineSummarizationSchedule](Get-CMBaselineSummarizationSchedule)





---


### Examples
#### Example 1: Export a baseline
```PowerShell
Export-CMBaseline -Name "BLConfig01" -Path "\\Contoso01\CM\Toolbox\BaselineW2K8.cab"
```



---


### Parameters
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

Specify the CI_ID of the configuration baseline to export. For example, `16777516`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify a configuration baseline object to export. To get this object, use the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specify the name of the configuration baseline to export.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **Path**

Specify the full path of the cabinet file to export to. Include the file extension `.cab` in the path.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ExportFilePath|



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
Export-CMBaseline [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMBaseline [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMBaseline [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
