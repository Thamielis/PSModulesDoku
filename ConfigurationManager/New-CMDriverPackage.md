New-CMDriverPackage
-------------------




### Synopsis
Create a driver package.



---


### Description

Use this cmdlet to create a driver package. Group similar device drivers in packages to help streamline OS deployments. For example, create a driver package for each computer manufacturer on your network. For more information, see Manage drivers in Configuration Manager (/mem/configmgr/osd/get-started/manage-drivers).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMDriverPackage](Export-CMDriverPackage)



* [Get-CMDriverPackage](Get-CMDriverPackage)



* [Import-CMDriverPackage](Import-CMDriverPackage)



* [Remove-CMDriverPackage](Remove-CMDriverPackage)



* [Set-CMDriverPackage](Set-CMDriverPackage)



* [Manage drivers in Configuration Manager](Manage drivers in Configuration Manager)





---


### Examples
#### Example 1: Create a new driver package
```PowerShell
New-CMDriverPackage -Name "Pckg01" -Path "\\Contoso01\Users\pattifuller\Desktop\pckg"
```

#### Example 2: Create a driver package with manufacturer and model
```PowerShell
New-CMDriverPackage -Name "Surface Book 2 Drivers" -Description "Some descriptive text" -DriverManufacturer "Microsoft" -DriverModel "Surface 2"
```



---


### Parameters
#### **Description**

Specify an optional description of a driver package. The maximum length is 127 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DriverManufacturer**

Use this parameter to set the manufacturer of the device. The maximum length is 100 characters.


Use it with the DriverModel parameter. You can use them for managing the driver catalog, and with task sequence pre-caching. For more information, see Configure pre-cache content for task sequences (/mem/configmgr/osd/deploy-use/configure-precache-content).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DriverModel**

Use this parameter to set the model of the device. The maximum length is 100 characters.


Use it with the DriverManufacturer parameter. You can use them for managing the driver catalog, and with task sequence pre-caching. For more information, see Configure pre-cache content for task sequences (/mem/configmgr/osd/deploy-use/configure-precache-content).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specify a name for a driver package. The maximum length is 50 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Path**

Specify a file path to the network location to source the driver files.


When you create a driver package, the source location of the package must point to an empty network share that's not used by another driver package. The SMS Provider must have Full control permissions to that location.


When you add device drivers to a driver package, Configuration Manager copies it to this path. You can add to a driver package only device drivers that you've imported and that are enabled in the driver catalog.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|true    |named   |False        |PackageSourcePath|



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
None





---


### Outputs
* IResultObject#SMS_DriverPackage






---


### Notes
For more information on this return object and its properties, see SMS_DriverPackage server WMI class (/mem/configmgr/develop/reference/osd/sms_driverpackage-server-wmi-class).



---


### Syntax
```PowerShell
New-CMDriverPackage [-Description <String>] [-DisableWildcardHandling] [-DriverManufacturer <String>] [-DriverModel <String>] [-ForceWildcardHandling] -Name <String> -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
