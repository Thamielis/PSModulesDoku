Get-CMDriver
------------




### Synopsis
Get a device driver.



---


### Description

Use this cmdlet to get a device driver. Configuration Manager provides a driver catalog that you can use to manage the Windows device drivers in your environment. For more information, see Manage drivers in Configuration Manager (/mem/configmgr/osd/get-started/manage-drivers).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMDriver](Disable-CMDriver)



* [Enable-CMDriver](Enable-CMDriver)



* [Import-CMDriver](Import-CMDriver)



* [Remove-CMDriver](Remove-CMDriver)



* [Set-CMDriver](Set-CMDriver)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Manage drivers in Configuration Manager](Manage drivers in Configuration Manager)





---


### Examples
#### Example 1: Get a device driver by name
```PowerShell
Get-CMDriver -Name "Surface Serial Hub Driver"
```

#### Example 2: Get specific information about drivers from a specific manufacturer
```PowerShell
Get-CMDriver -Fast -Name "Surface*" | Select-Object LocalizedDisplayName,DriverVersion,DriverDate
```

#### Example 3: Get all drivers for a specific category
```PowerShell
$category = Get-CMCategory -Name "Surface"

Get-CMDriver -Fast -AdministrativeCategory $category
```



---


### Parameters
#### **AdministrativeCategory**

Specify an array of driver category objects. You can assign a driver to a category for filtering purposes. For example, "Surface" or "Boot image".


To get this object, use the Get-CMCategory (Get-CMCategory.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                 |
|-------------------|--------|--------|-------------|------------------------|
|`[IResultObject[]]`|false   |named   |False        |AdministrativeCategories|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DriverPackageId**

Specify the ID of a driver package to get all drivers in it. This value is a standard package ID format, for example, `XYZ00204`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **DriverPackageName**

Specify the name of a driver package to get all drivers in it.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |PackageName|



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of a specific device driver. This value is the same as the CI_ID attribute, for example `66383`.






|Type     |Required|Position|PipelineInput|Aliases                    |
|---------|--------|--------|-------------|---------------------------|
|`[Int32]`|true    |named   |False        |CIId<br/>DriverId<br/>CI_ID|



#### **InputObject**

Specify a driver package object to get all drivers in it. To get this object, use the Get-CMDriverPackage (Get-CMDriverPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases      |
|-----------------|--------|--------|--------------|-------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DriverPackage|



#### **Name**

Specify the name of a specific device driver to get.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases                            |
|----------|--------|--------|-------------|-----------------------------------|
|`[String]`|false   |named   |False        |LocalizedDisplayName<br/>DriverName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_Driver


* IResultObject#SMS_Driver






---


### Notes
For more information on this return object and its properties, see SMS_Driver server WMI class (/mem/configmgr/develop/reference/osd/sms_driver-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMDriver [-AdministrativeCategory <IResultObject[]>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDriver [-DisableWildcardHandling] -DriverPackageId <String> [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDriver [-DisableWildcardHandling] -DriverPackageName <String> [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMDriver [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -Id <Int32> [<CommonParameters>]
```
```PowerShell
Get-CMDriver [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMDriver [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
