Enable-CMDriver
---------------




### Synopsis
Enables a device driver.



---


### Description

The Enable-CMDriver cmdlet enables a device driver in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMDriver](Disable-CMDriver)



* [Get-CMDriver](Get-CMDriver)



* [Import-CMDriver](Import-CMDriver)



* [Remove-CMDriver](Remove-CMDriver)



* [Set-CMDriver](Set-CMDriver)



* [Get-CMDriverPackage](Get-CMDriverPackage)





---


### Examples
#### Example 1: Enable a driver by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDriver -Name "Driver02" | Enable-CMDriver
```
This command gets the driver object named Driver02 and uses the pipeline operator to pass the object to Enable-CMDriver , which enables the driver object.
#### Example 2: Enable a device driver that is specified by its name
```PowerShell
PS XYZ:\> $Driver = Get-CMDriver -Name "Driver01"
PS XYZ:\> Enable-CMDriver -InputObject $Driver
```
The first command gets the driver object named Driver01 and stores the object in the $Driver variable.


The second command enables the driver stored in $Driver.


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

Specifies a driver object. To obtain a driver object, use the Get-CMDriver (Get-CMDriver.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies the name of a driver.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



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
Enable-CMDriver [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMDriver [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Enable-CMDriver [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
