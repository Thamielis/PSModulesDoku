ConvertFrom-CMApplication
-------------------------




### Synopsis
Converts an application SDK object to an application object.



---


### Description

The ConvertFrom-CMApplication cmdlet converts an application SDK object to an application object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Convert-CMApplication](Convert-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [Export-CMApplication](Export-CMApplication)



* [Get-CMApplication](Get-CMApplication)



* [Import-CMApplication](Import-CMApplication)



* [Remove-CMApplication](Remove-CMApplication)



* [Resume-CMApplication](Resume-CMApplication)



* [Set-CMApplication](Set-CMApplication)



* [Suspend-CMApplication](Suspend-CMApplication)





---


### Examples
#### Example 1: Convert an application object
```PowerShell
PS XYZ:\> $SdkApp = Get-CMApplication -Name "Application01" | ConvertTo-CMApplication
PS XYZ:\> $SdkApp | ConvertFrom-CMApplication
```
The first command gets the application object named Application01 and uses the pipeline operator to pass the object to ConvertTo-CMApplication , which converts the application object into an application SDK object. The command then stores the object in the $SdkApp variable.


The second command converts the application SDK object stored in $SdkApp to an application object.
#### Example 2: Convert an application object
```PowerShell
PS XYZ:\> $SdkApp = Get-CMApplication -Name "Application02" | ConvertTo-CMApplication
PS XYZ:\> ConvertFrom-CMApplication -InputObject $SdkApp
```
The first command gets the application object named Application02 and uses the pipeline operator to pass the object to ConvertTo-CMApplication , which converts the application object into an application SDK object. The command then stores the object in the $SdkApp variable.


The second command converts the application SDK object stored in $SdkApp to an application object.


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

Specifies an application SDK object. To obtain an application object, use the ConvertTo-CMApplication (ConvertTo-CMApplication.md) cmdlet or the [Convert-CMApplication](Convert-CMApplication.md)cmdlet.






|Type           |Required|Position|PipelineInput |Aliases    |
|---------------|--------|--------|--------------|-----------|
|`[Application]`|true    |named   |True (ByValue)|Application|





---


### Inputs
Microsoft.ConfigurationManagement.ApplicationManagement.Application





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
ConvertFrom-CMApplication [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <Application> [<CommonParameters>]
```
