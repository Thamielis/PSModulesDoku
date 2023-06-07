Remove-CMAppVVirtualEnvironment
-------------------------------




### Synopsis
Removes an App-V virtual environment.



---


### Description

The Remove-CMAppVVirtualEnvironment cmdlet removes one or more Microsoft Application Virtualization (App-V) virtual environment objects from Configuration Manager. You can specify App-V virtual environments by name or ID, or you can provide an App-V virtual environment object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMAppVVirtualEnvironment](Get-CMAppVVirtualEnvironment)



* [New-CMAppVVirtualEnvironment](New-CMAppVVirtualEnvironment)



* [Set-CMAppVVirtualEnvironment](Set-CMAppVVirtualEnvironment)





---


### Examples
#### Example 1: Remove a virtual environment by name
```PowerShell
PS XYZ:\> Remove-CMAppVVirtualEnvironment -Name "Test"
```
This command removes an App-V virtual environment named Test.
#### Example 2: Remove a virtual environment by ID
```PowerShell
PS XYZ:\> Remove-CMAppVVirtualEnvironment -Id "16781806"
```
This command removes an App-V virtual environment that has the ID 16781806.
#### Example 3: Remove a virtual environment by name by using a wildcard
```PowerShell
PS XYZ:\> $AppV = Get-CMAppVVirtualEnvironment -Name "T*"
PS XYZ:\> Remove-CMAppVVirtualEnvironment -InputObject $AppV
```
The first command gets all App-V virtual environments that have names that begin with the letter T and stores them in the $AppV variable.


The second command removes all the environments stored in $AppV.


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

Specifies an array of IDs of virtual environments.






|Type       |Required|Position|PipelineInput|Aliases       |
|-----------|--------|--------|-------------|--------------|
|`[Int32[]]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies an App-V virtual environment object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of names of App-V virtual environment objects. You can use a wildcard.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



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
Remove-CMAppVVirtualEnvironment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAppVVirtualEnvironment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMAppVVirtualEnvironment [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
