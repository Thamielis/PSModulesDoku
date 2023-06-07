Convert-CMApplication
---------------------




### Synopsis
Converts an application object.



---


### Description

The Convert-CMApplication cmdlet converts an application object to an application SDK object or an application SDK object to an application object.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [ConvertFrom-CMApplication](ConvertFrom-CMApplication)



* [ConvertTo-CMApplication](ConvertTo-CMApplication)



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
#### Example 1: Get an application object and convert it
```PowerShell
PS XYZ:\> Get-CMApplication -ApplicationName "Application01" | Convert-CMApplication
```
This command gets the application object named Applicaton01 and uses the pipeline operator to pass the object to Convert-CMApplication , which converts the application object to an application SDK object.
#### Example 2: Get an SDK application object and convert it
```PowerShell
PS XYZ:\> $SdkApp = ConvertTo-CMApplication -InputObject (Get-CMApplication -ApplicationName "Application01")
PS XYZ:\> Convert-CMApplication -InputObject $SdkApp
```
The first command converts the application named Application01 to an application SDK object and stores the object in the $SdkApp variable.


The second command converts the SDK application object in $SdkApp to an application object.


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

Specifies an application object or application SDK object. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet. To obtain an application SDK object, use the ConvertTo-CMApplication (ConvertTo-CMApplication.md)cmdlet.






|Type        |Required|Position|PipelineInput |Aliases                                                                         |
|------------|--------|--------|--------------|--------------------------------------------------------------------------------|
|`[PSObject]`|true    |named   |True (ByValue)|IResultObject<br/>Application<br/>ProviderApplicationObject<br/>ApplicationGroup|





---


### Inputs
System.Management.Automation.PSObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Convert-CMApplication [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <PSObject> [<CommonParameters>]
```
