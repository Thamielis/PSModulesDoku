Remove-CMTaskSequence
---------------------




### Synopsis
Remove a task sequence.



---


### Description

The Remove-CMTaskSequence cmdlet removes a task sequence from Configuration Manager.



All related deployments are automatically removed.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMTaskSequence](New-CMTaskSequence)



* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Set-CMTaskSequence](Set-CMTaskSequence)



* [Copy-CMTaskSequence](Copy-CMTaskSequence)



* [Import-CMTaskSequence](Import-CMTaskSequence)



* [Export-CMTaskSequence](Export-CMTaskSequence)





---


### Examples
#### Example 1: Remove a task sequence by using a variable
```PowerShell
PS XYZ:\> $TaskSequence = Get-CMTaskSequence -Name "TaskSequence01"
PS XYZ:\> Remove-CMTaskSequence -InputObject $TaskSequence
Remove
Are you sure you wish to remove TaskSequence: Name="General Sequence 11"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

#### Example 2: Remove a task sequence by using the pipeline
```PowerShell
Get-CMTaskSequence -Name "TaskSequence02" | Remove-CMTaskSequence -Force
```



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



#### **InputObject**

Specifies a task sequence object. To get a task sequence object, use the Get-CMTaskSequence (Get-CMTaskSequence.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of a task sequence to remove.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TaskSequencePackageId**

Specifies the ID of a task sequence to remove.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



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
Remove-CMTaskSequence [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequence [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMTaskSequence [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -TaskSequencePackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
