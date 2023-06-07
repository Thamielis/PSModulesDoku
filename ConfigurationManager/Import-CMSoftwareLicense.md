Import-CMSoftwareLicense
------------------------




### Synopsis
Imports a software license.



---


### Description

The Import-CMSoftwareLicense cmdlet imports Microsoft and non-Microsoft licensing information into the Asset Intelligence catalog in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Import a software license
```PowerShell
PS XYZ:\>Import-CMSoftwareLicense -MlsFilePath "\\ContosoFS01\Mid\SWLicense01.xml" -ImportType MicrosftVolumeLicenseStatement
```
This command imports a MVLS license statement from the licensing information file named SWLicense01.xml.


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



#### **ImportType**

Specifies an import type for the software license. The acceptable values for this parameter are: GeneralLicenseStatement and MicrosoftVolumeLicenseStatement.


A general license statement contains information about the purchased licenses for any publisher. A Microsoft Volume License Statement (MVLS) license statement contains information about the license entitlements, or number of purchased licenses, for Microsoft products.



Valid Values:

* MicrosoftVolumeLicenseStatement
* GeneralLicenseStatement






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[ImportType]`|true    |named   |False        |



#### **MlsFilePath**

Specifies the Universal Naming Convention (UNC) path of a valid XML-formatted licensing information file.






|Type      |Required|Position|PipelineInput|Aliases                                          |
|----------|--------|--------|-------------|-------------------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ImportFilePath<br/>Path|



#### **Timeout**

{{ Fill Timeout Description }}






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[TimeSpan]`|false   |named   |False        |



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
Import-CMSoftwareLicense [-DisableWildcardHandling] [-ForceWildcardHandling] -ImportType {MicrosoftVolumeLicenseStatement | GeneralLicenseStatement} -MlsFilePath <String> [-Timeout <TimeSpan>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
