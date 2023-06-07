Remove-CMApplication
--------------------




### Synopsis
Removes an application from Configuration Manager.



---


### Description

The Remove-CMApplication cmdlet removes an application from Configuration Manager so that it cannot be installed by clients. This cmdlet does not remove any existing client installations.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMApplication](Convert-CMApplication)



* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [Export-CMApplication](Export-CMApplication)



* [Import-CMApplication](Import-CMApplication)



* [New-CMApplication](New-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)





---


### Examples
#### Example 1: Get an application and remove it
```PowerShell
PS XYZ:\> Get-CMApplication -Name "Application1" | Remove-CMApplication -Force
```
The first command gets the application object named Application1 and uses the pipeline operator to pass the object to Remove-CMApplication , which removes the application. Specifying the Force parameter indicates that the user is not prompted before the application is removed.
#### Example 2: Remove an application by model name
```PowerShell
PS XYZ:\> Remove-CMApplication -ModelName "ScopeId_5E88BBB4-B1D1-4B74-8A4F-9E8B03BC1EB0/Application_7aa0ed27-6240-4070-a098-3edc9281dd96" -Force
```
This command removes the application object with the specified model name. Specifying the Force parameter indicates that the user is not prompted before the application is removed.


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

Specifies the CI_ID and ModelID properties (the same value) of an application.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies an application object. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ModelName**

Specifies the model name of the application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specifies the name of the application.






|Type      |Required|Position|PipelineInput|Aliases                                 |
|----------|--------|--------|-------------|----------------------------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName<br/>ApplicationName|



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
Remove-CMApplication [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplication [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplication [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -ModelName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMApplication [-Name] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
