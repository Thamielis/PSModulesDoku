Disable-CMDriver
----------------




### Synopsis
Disables a device driver.



---


### Description

The Disable-CMDriver cmdlet disables a device driver in Configuration Manager. To enable the driver, use the Enable-CMDriver (Enable-CMDriver.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Enable-CMDriver](Enable-CMDriver)



* [Import-CMDriver](Import-CMDriver)



* [Get-CMDriver](Get-CMDriver)



* [Remove-CMDriver](Remove-CMDriver)



* [Set-CMDriver](Set-CMDriver)



* [Get-CMDriverPackage](Get-CMDriverPackage)





---


### Examples
#### Example 1: Disable a device driver
```PowerShell
PS XYZ:\> $Driver = Get-CMDriver -Name "Driver01"
PS XYZ:\> Disable-CMDriver -InputObject $Driver
```
The first command gets the driver object named Driver01 and stores the object in the $Driver variable.


The second command disables the driver stored in $Driver.
#### Example 2: Disable a device driver by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDriver -Name "Driver02" | Disable-CMDriver
```
This command gets the driver object named Driver02 and uses the pipeline operator to pass the object to Disable-CMDriver , which disables the driver object.


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

Specifies the ID of a driver.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a driver object. To obtain a driver object, use the Enable-CMDriver (Enable-CMDriver.md)cmdlet.






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
Disable-CMDriver [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMDriver [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Disable-CMDriver [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
