Add-CMMobileMsiDeploymentType
-----------------------------




### Synopsis
Adds a mobile Windows Installer deployment type.



---


### Description

The Add-CMMobileMsiDeploymentType cmdlet adds a mobile Windows Installer deployment type to an application.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Set-CMMobileMsiDeploymentType](Set-CMMobileMsiDeploymentType)





---


### Examples
#### Example 1: Add a deployment type
```PowerShell
PS XYZ:\>Add-CMMobileMsiDeploymentType -ApplicationName "TestMobile" -ContentLocation "\\Server01\Resources\Applications\MSI\32BitSDK\32BitCompat.msi" -DeploymentTypeName "DTMobile" -AddLanguage "en-US","zh-CN" -Comment "Mobile test"
```
This command adds the mobile Windows Installer deployment type named DTMobile from the specified location to the application named TestMobile in English and Chinese.
#### Example 2: Add a deployment type by using the pipeline
```PowerShell
PS XYZ:\> Get-CMApplication "TestMobile" | Add-CMMobileMsiDeploymentType -ContentLocation "\\127.0.0.1\c$\UnitTest\Resources\Applications\MSI\32BitSDK\32BitCompat.msi" -DeploymentTypeName "DTMobile02" -AddLanguage "en-US","zh-CN" -Comment "Mobile test"
```
This command gets the application object named TestMobile and uses the pipeline operator to pass the object to Add-CMMobileMsiDeploymentType . Add-CMMobileMsiDeploymentType adds a mobile Windows Installer deployment type named DTMobile02 from the specified location in English and Chinese.


---


### Parameters
#### **AddLanguage**

Adds an array of languages that this deployment type supports. Provide the languages in the "languagecode2-country" or "languagecode2" format, for example: en, en-US, ja-JP, zh-CN.


For more information, see CultureInfo.Name (/dotnet/api/system.globalization.cultureinfo.name#System_Globalization_CultureInfo_Name).






|Type        |Required|Position|PipelineInput|Aliases                                |
|------------|--------|--------|-------------|---------------------------------------|
|`[String[]]`|false   |named   |False        |AddLanguages<br/>Languages<br/>Language|



#### **AddRequirement**

Adds an array of requirements for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Rule[]]`|false   |named   |False        |



#### **ApplicationId**

Specifies the ID of the application that is associated with this deployment type.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CI_ID<br/>CIId|



#### **ApplicationName**

Specifies the name of the application that is associated with this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Comment**

Specifies a description for this deployment type.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |AdministratorComment|



#### **ContentLocation**

Specifies the path to an .msi file. The site system server requires permissions to read the content files.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|true    |named   |False        |InstallationFileLocation|



#### **DeploymentTypeName**

Specifies a display name for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[Switch]`|false   |named   |False        |ForceForUnknownPublisher|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies an application object. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application|



#### **InstallCommand**

Specifies the command to use to install the Windows Installer package from the command line.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RemoveLanguage**

Removes an array of existing languages from this deployment type. Provide the languages in the "languagecode2-country" or "languagecode2" format, for example: en, en-US, ja-JP, zh-CN.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |RemoveLanguages|



#### **RemoveRequirement**

Removes the existing installation requirements from this deployment type.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Rule[]]`|false   |named   |False        |RemoveRequirements|



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
Add-CMMobileMsiDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-Comment <String>] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-InstallCommand <String>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMMobileMsiDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-Comment <String>] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-InstallCommand <String>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMMobileMsiDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-Comment <String>] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallCommand <String>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
