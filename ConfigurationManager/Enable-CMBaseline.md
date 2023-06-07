Enable-CMBaseline
-----------------




### Synopsis
Enable a configuration baseline.



---


### Description

Use this cmdlet to enable a configuration baseline for compliance evaluation.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMBaseline](Disable-CMBaseline)



* [Export-CMBaseline](Export-CMBaseline)



* [Get-CMBaseline](Get-CMBaseline)



* [Import-CMBaseline](Import-CMBaseline)



* [New-CMBaseline](New-CMBaseline)



* [Remove-CMBaseline](Remove-CMBaseline)



* [Set-CMBaseline](Set-CMBaseline)





---


### Examples
#### Example 1: Enable a configuration baseline
```PowerShell
Enable-CMBaseline -Name "BLConfig01"
```

#### Example 2: Enable all disabled configuration baselines
```PowerShell
$baselines = Get-CMBaseline -Fast | Where-Object { -not $_.IsEnabled }

foreach ( $baseline in $baselines ) {
  Enable-CMBaseline -InputObject $baseline
}
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

Specify the CI_ID of the configuration baseline to enable. For example, `16777516`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify a configuration baseline object to enable. To get this object, use the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specify the name of the configuration baseline to enable.






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
Enable-CMBaseline [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMBaseline [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMBaseline [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
