Set-CMAppvDeploymentType
------------------------




### Synopsis
Sets an App-V deployment type.



---


### Description

The Set-CMAppvDeploymentType cmdlet changes the settings for a Microsoft Application Virtualization (App-V) deployment type.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMAppvDeploymentType](Add-CMAppvDeploymentType)



* [Get-CMApplication](Get-CMApplication)



* [Get-CMDeploymentType](Get-CMDeploymentType)





---


### Examples
#### Example 1: Change the name of the deployment type
```PowerShell
PS XYZ:\> Set-CMAppvDeploymentType -ApplicationName "testApp" -DeploymentTypeName "Appv" -NewName "newAppv"
```
This command changes the display name of the deployment type for the application named testApp from AppV to newAppv.
#### Example 2: Change the name of the deployment type by using the pipeline
```PowerShell
PS XYZ:\> Get-CMDeploymentType -DeploymentTypeName "Appv" -ApplicationName "testApp" | Set-CMAppvDeploymentType -NewName "newAppv"
```
This command gets the deployment type object named Appv for the applicaton named testApp and uses the pipeline operator to pass the object to Set-CMAppvDeploymentType , which changes the name of the deployment type object to newAppv.


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



#### **ContentFallback**

Indicates whether clients are allowed to use a fallback source location for content files.






|Type       |Required|Position|PipelineInput|Aliases                                                                            |
|-----------|--------|--------|-------------|-----------------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |EnableContentLocationFallback<br/>AllowClientsToUseFallbackSourceLocationForContent|



#### **ContentLocation**

Specifies the path of the content. The site system server requires permissions to read the content files.






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



#### **FastNetworkDeploymentMode**

Specifies the installation behavior of the deployment type on a fast network. Valid values are:


* DownloadContentForStreaming


* Download


* DoNothing



Valid Values:

* DoNothing
* Download
* DownloadContentForStreaming






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ContentHandlingMode]`|false   |named   |False        |



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

Specifies an App-V deployment type object. To obtain a deployment type object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



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



#### **SlowNetworkDeploymentMode**

Specifies the installation behavior of the deployment type on a slow network. Valid values are:


* DoNothing


* Download


* DownloadContentForStreaming



Valid Values:

* DoNothing
* Download
* DownloadContentForStreaming






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ContentHandlingMode]`|false   |named   |False        |



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
Set-CMAppvDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -Application <IResultObject> [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-FastNetworkDeploymentMode {DownloadContentForStreaming | Download}] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-SlowNetworkDeploymentMode {DoNothing | Download | DownloadContentForStreaming}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAppvDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-FastNetworkDeploymentMode {DownloadContentForStreaming | Download}] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-SlowNetworkDeploymentMode {DoNothing | Download | DownloadContentForStreaming}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAppvDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-FastNetworkDeploymentMode {DownloadContentForStreaming | Download}] [-Force] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-SlowNetworkDeploymentMode {DoNothing | Download | DownloadContentForStreaming}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMAppvDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] [-DisableWildcardHandling] [-FastNetworkDeploymentMode {DownloadContentForStreaming | Download}] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-SlowNetworkDeploymentMode {DoNothing | Download | DownloadContentForStreaming}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
