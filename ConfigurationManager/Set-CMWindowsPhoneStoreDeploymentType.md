Set-CMWindowsPhoneStoreDeploymentType
-------------------------------------




### Synopsis
Sets a Windows Phone app package (in the Windows Store) deployment type.



---


### Description

The Set-CMWindowsPhoneStoreDeploymentType cmdlet changes the settings for a Windows Phone app package (in the Windows Store) deployment type.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMWindowsPhoneStoreDeploymentType](Add-CMWindowsPhoneStoreDeploymentType)



* [Get-CMApplication](Get-CMApplication)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Change the display name of a deployment type by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDeploymentType -ApplicationName "Application1" -DeploymentTypeName "DT1" | Set-CMWindowsPhoneStoreDeploymentType -NewName "DT1_New" -AddLanguage "en-US","zh-CN" -Comment "Deployment Type updated"
```
This command gets the Windows Phone app package deployment type object named DT1 for the application named Application1 and uses the pipeline operator to pass the object to Set-CMWindowsPhoneStoreDeploymentType . Set-CMWindowsPhoneStoreDeploymentType changes the name of the deployment type to DT1_New, and adds English and Chinese as supported languages.
#### Example 2: Rename a deployment type
```PowerShell
PS XYZ:\> Set-CMWindowsPhoneStoreDeploymentType -ApplicationName "Application1" -DeploymentTypeName "DT1" -NewName "DT1_New" -AddLanguage "en-US","zh-CN" -Comment "Deployment Type updated"
```
This command changes the name of the Windows Phone app package deployment type named DT1 for the application named Application1 to DT1_New and adds English and Chinese as supported languages. Additionally, the command updates the comment.


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

Specifies a description for the deployment type.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |AdministratorComment|



#### **DeploymentTypeName**

Specifies a display name for the deployment type.






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

Specifies a deployment type object. To obtain a deployment type object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **NewName**

Specifies a new name for the deployment type.






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



#### **Url**

Specifies the URL of an application in the Windows Store.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |ContentLocation|



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
Set-CMWindowsPhoneStoreDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -Application <IResultObject> [-Comment <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Url <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsPhoneStoreDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-Comment <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Url <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsPhoneStoreDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-Comment <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Url <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMWindowsPhoneStoreDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-Comment <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-Url <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
