Update-CMApplicationStatistic
-----------------------------




### Synopsis
Updates the statistics for an application.



---


### Description

The Update-CMApplicationStatistic cmdlet updates the statistics for a Configuration Manager application.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)





---


### Examples
#### Example 1: Update statistics for an application by ID
```PowerShell
PS XYZ:\>Update-CMApplicationStatistic -Id "16781415"
```
This command updates statistics for an application that has the ID 16781415.
#### Example 2: Update statistics for an application by name
```PowerShell
PS XYZ:\>Update-CMApplicationStatistic -Name "Test"
```
This command updates statistics for an application named Test.
#### Example 3: Update statistics for an application by name by using a variable
```PowerShell
PS XYZ:\> $App = Get-CMApplication -Name "Test"
PS XYZ:\> Update-CMApplicationStatistic -InputObject $App
```
The first command gets the application object named Test and stores the object in the $App variable.


The second command updates statistics for the application stored in $App.


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

Specifies an array of IDs of applications.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a Configuration Manager application statistic object.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |0       |True (ByValue)|Application|



#### **Name**

Specifies an array of names of applications.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Update-CMApplicationStatistic [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMApplicationStatistic [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Update-CMApplicationStatistic [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
