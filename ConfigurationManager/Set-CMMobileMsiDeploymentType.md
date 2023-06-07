Set-CMMobileMsiDeploymentType
-----------------------------




### Synopsis
Sets a mobile Windows Installer deployment type.



---


### Description

The Set-CMMobileMsiDeploymentType cmdlet changes the settings for a mobile Windows Installer deployment type.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMMobileMsiDeploymentType](Add-CMMobileMsiDeploymentType)



* [Get-CMApplication](Get-CMApplication)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Modify a mobile Windows Installer deployment type
```PowerShell
PS XYZ:\> Set-CMMobileMsiDeploymentType -ApplicationName "testMobile" -DeploymentTypeName "DTMobile" -NewName "DTMobile_Updated" -ContentLocation "\\Server01\Resources\Applications\MSI\32BitSDK\test\32BitCompat.msi" -PassThru -Confirm -Comment "test-set-CMMobileMsiDeploymentType"
```
This command changes the name of the mobile Windows Installer deployment type named DTMobile for the application named testMobile to DTMobile_Updated, and adds a description. The PassThru parameter indicates that an object will be returned from this command, and the Confirm parameter indicates that the user will be prompted for confirmation before the command runs.
#### Example 2: Modify a mobile Windows Installer deployment type by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDeploymentType -ApplicationName "testMobile" -DeploymentTypeName "DTMobile_Updated" | Set-CMMobileMsiDeploymentType -NewName "DTMobile" -ContentLocation "\\Server01\Resources\Applications\MSI\32BitSDK\32BitCompat.msi" -PassThru -DisableWildcardHandling -Comment "test-set-CMMobileMsiDeploymentType"
```
This command gets the mobile Windows Installer deployment type object named DTMobile_Updated for the application named testMobile and uses the pipeline operator to pass the object to Set-CMMobileMsiDeploymentType . Set-CMMobileMsiDeploymentType changes the name of the deployment type to DTMobile, disables wildcard handling, and adds a description. The PassThru parameter indicates that an object will be returned from this command.


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



#### **Application**

Specifies an application object that is associated with this deployment type. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



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






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentTypeName**

Specifies a display name for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specifies a mobile MSI deployment type object. To obtain a deployment type object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **InstallCommand**

Specifies the command to use to install the Windows Installer package from the command line.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NewName**

Specifies a new name for this deployment type.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |NewDeploymentTypeName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Set-CMMobileMsiDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -Application <IResultObject> [-Comment <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-InstallCommand <String>] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMobileMsiDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-Comment <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-InstallCommand <String>] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMobileMsiDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-Comment <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-InstallCommand <String>] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMobileMsiDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-Comment <String>] [-ContentLocation <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallCommand <String>] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
