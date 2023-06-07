ConvertTo-CMApplication
-----------------------




### Synopsis
Converts an application object to an application SDK object.



---


### Description

The ConvertTo-CMApplication cmdlet converts an application object to an application SDK object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMApplication](Convert-CMApplication)



* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [Export-CMApplication](Export-CMApplication)



* [Import-CMApplication](Import-CMApplication)



* [New-CMApplication](New-CMApplication)



* [Remove-CMApplication](Remove-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)





---


### Examples
#### Example 1: Get an application and convert it
```PowerShell
PS XYZ:\> Get-CMApplication -Name "Application01" | ConvertTo-CMApplication
```
This command gets the application object named Application01 and uses the pipeline operator to pass the object to ConvertTo-CMApplication , which converts the application object to an application SDK object.
#### Example 2: Convert an application
```PowerShell
PS XYZ:\>ConvertTo-CMApplication -InputObject (Get-CMApplication -Name "Application02")
```
This command gets the application object named Application02 and converts the application object to an application SDK object.


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



#### **InputObject**

Specifies an application object. To obtain an application object, use the Get-CMApplication (./Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                                            |
|-----------------|--------|--------|--------------|---------------------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application<br/>DeploymentType<br/>ApplicationGroup|





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
ConvertTo-CMApplication [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
