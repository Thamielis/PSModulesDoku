Remove-CMDriver
---------------




### Synopsis
Removes a device driver from Configuration Manager.



---


### Description

The Remove-CMDriver cmdlet removes a device driver from the Driver Catalog. The source is not affected.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMDriver](Disable-CMDriver)



* [Enable-CMDriver](Enable-CMDriver)



* [Get-CMDriver](Get-CMDriver)



* [Import-CMDriver](Import-CMDriver)



* [Set-CMDriver](Set-CMDriver)



* [Get-CMDriverPackage](Get-CMDriverPackage)





---


### Examples
#### Example 1: Remove a driver specified by a driver object
```PowerShell
PS XYZ:\> $Driver = Get-CMDriver -Name "Driver01"
PS XYZ:\> Remove-CMDriver -InputObject $Driver -Force
```
The first command gets the driver object named Driver01 and stores the object in the $Driver variable.


The second command removes the driver stored in $Driver. Specifying the Force parameter indicates that the user is not prompted before the driver is removed.
#### Example 2: Remove a driver by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDriver -Name "Driver02" | Remove-CMDriver -Force
```
This command gets the driver object named Driver02 and uses the pipeline operator to pass the object to Remove-CMDriver , which removes the driver object. Specifying the Force parameter indicates that the user is not prompted before the driver is removed.


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

Specifies the ID of a driver.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a driver object. To obtain a driver object, use the Get-CMDriver (Get-CMDriver.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of a driver.






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
Remove-CMDriver [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Id <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriver [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDriver [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
