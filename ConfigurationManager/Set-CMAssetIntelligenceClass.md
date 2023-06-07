Set-CMAssetIntelligenceClass
----------------------------




### Synopsis
Modifies the Asset Intelligence hardware inventory reporting classes.



---


### Description

The Set-CMAssetIntelligenceClass cmdlet modifies the Asset Intelligence hardware inventory reporting classes. The Hardware Inventory Client Agent collects inventory from Configuration Manager clients based on the Asset Intelligence hardware inventory reporting classes that you enable.



You can modify the categorization information, which includes product name, vendor, software category, and software family, for inventoried software only at the top-level site in your hierarchy. After you modify the categorization information for predefined software, the validation state for the software changes from Validated to User Defined.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Send-CMAssetIntelligenceCatalogUpdateRequest](Send-CMAssetIntelligenceCatalogUpdateRequest)



* [Sync-CMAssetIntelligenceCatalog](Sync-CMAssetIntelligenceCatalog)





---


### Examples
#### Example 1: Change the Asset Intelligence hardware inventory reporting classes
```PowerShell
PS XYZ:\> Set-CMAssetIntelligenceClass -EnableReportingClassName SMS_InstalledExecutable -DisableReportingClassName MS_InstalledSoftware
```
This command enables the reporting class named SMS_InstalledExecutable and disables the reporting class named MS_InstalledSoftware.
#### Example 2: Enable all Asset Intelligence hardware inventory reporting classes
```PowerShell
PS XYZ:\> Set-CMAssetIntelligenceClass -EnableAllReportingClass
```
This command enables all the Asset Intelligence hardware inventory reporting classes.


---


### Parameters
#### **DisableReportingClass**

Specifies an array of Asset Intelligence reporting classes to disable. The acceptable values for this parameter are:


* SMS_AutoStartSoftware


* SMS_BrowserHelperObject


* SMS_InstalledExecutable


* SMS_InstalledSoftware


* SMS_SoftwareShortcut


* SMS_SoftwareTag


* SMS_SystemConsoleUsage


* SMS_SystemConsoleUser


* SoftwareLicensingProduct


* SoftwareLicensingService


* Win32_USBDevice



Valid Values:

* SMS_AutoStartSoftware
* SMS_BrowserHelperObject
* SMS_InstalledExecutable
* SMS_InstalledSoftware
* SMS_SoftwareShortcut
* SMS_SystemConsoleUsage
* SMS_SystemConsoleUser
* SoftwareLicensingProduct
* SoftwareLicensingService
* Win32_USBDevice
* SMS_SoftwareTag






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[ClassNameType[]]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAllReportingClass**

Indicates that all Asset Intelligence reporting classes are enabled.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **EnableReportingClass**

Specifies an array of Asset Intelligence reporting classes to enable. The acceptable values for this parameter are:


* SMS_AutoStartSoftware


* SMS_BrowserHelperObject


* SMS_InstalledExecutable


* SMS_InstalledSoftware


* SMS_SoftwareShortcut


* SMS_SoftwareTag


* SMS_SystemConsoleUsage


* SMS_SystemConsoleUser


* SoftwareLicensingProduct


* SoftwareLicensingService


* Win32_USBDevice



Valid Values:

* SMS_AutoStartSoftware
* SMS_BrowserHelperObject
* SMS_InstalledExecutable
* SMS_InstalledSoftware
* SMS_SoftwareShortcut
* SMS_SystemConsoleUsage
* SMS_SystemConsoleUser
* SoftwareLicensingProduct
* SoftwareLicensingService
* Win32_USBDevice
* SMS_SoftwareTag






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[ClassNameType[]]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






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
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMAssetIntelligenceClass [-DisableReportingClass {SMS_AutoStartSoftware | SMS_BrowserHelperObject | SMS_InstalledExecutable | SMS_InstalledSoftware | SMS_SoftwareShortcut | SMS_SystemConsoleUsage | SMS_SystemConsoleUser | SoftwareLicensingProduct | SoftwareLicensingService | Win32_USBDevice | SMS_SoftwareTag}] [-DisableWildcardHandling] [-EnableReportingClass {SMS_AutoStartSoftware | SMS_BrowserHelperObject | SMS_InstalledExecutable | SMS_InstalledSoftware | SMS_SoftwareShortcut | SMS_SystemConsoleUsage | SMS_SystemConsoleUser | SoftwareLicensingProduct | SoftwareLicensingService | Win32_USBDevice | SMS_SoftwareTag}] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAssetIntelligenceClass [-DisableWildcardHandling] -EnableAllReportingClass [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
