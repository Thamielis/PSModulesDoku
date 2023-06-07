Add-CMWindowsAppxDeploymentType
-------------------------------




### Synopsis
Adds a Windows app package deployment type.



---


### Description

The Add-CMWindowsAppxDeploymentType cmdlet adds a Windows app package deployment type to an application.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMApplication](Get-CMApplication)



* [Set-CMWindowsAppxDeploymentType](Set-CMWindowsAppxDeploymentType)





---


### Examples
#### Example 1: Add a Windows app package deployment type
```PowerShell
PS XYZ:\>Add-CMWindowsAppxDeploymentType -ApplicationName "Application1" -DeploymentTypeName "DT1" -ContentLocation "\\Server1\Resources\Applications\appx\sccm_custom.appx" -AddLanguage "en-US","zh-CN" -Comment "New Deployment Type" -SlowNetworkDeploymentMode DoNothing -ContentFallback -TriggerVpn
```
This command adds the Windows app package deployment type named DT1 from the specified location to the application named Application1 in English and Chinese. Specifying the TriggerVpn parameter indicates that a VPN connection is used.
#### Example 2: Add a Windows app package deployment type by using the pipeline
```PowerShell
PS XYZ:\> Get-CMApplication -Name "Application1" | Add-CMWindowsAppxDeploymentType -DeploymentTypeName "DT1" -ContentLocation "\\Server1\Resources\Applications\appx\sccm_custom.appx" -AddLanguage "en-US","zh-CN" -Comment "New Deployment Type" -SlowNetworkDeploymentMode DoNothing -ContentFallback -TriggerVpn
```
This command gets the application object named Application1 and uses the pipeline operator to pass the object to Add-CMWindowsAppxDeploymentType . Add-CMWindowsAppxDeploymentType adds a Windows app package named Dt1 from the specified location in English and Chinese. Specifying the TriggerVpn parameter indicates that a VPN connection is used.


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



#### **ContentFallback**

Indicates that a client can use a fallback location provided by a management point. A fallback location point provides an alternate location for source content when the content for the deployment type is not available on any of the preferred distribution points.






|Type      |Required|Position|PipelineInput|Aliases                                                                            |
|----------|--------|--------|-------------|-----------------------------------------------------------------------------------|
|`[Switch]`|false   |named   |False        |EnableContentLocationFallback<br/>AllowClientsToUseFallbackSourceLocationForContent|



#### **ContentLocation**

Specifies the path of the content. The site system server requires permissions to read the content files.






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



#### **TriggerVpn**

Indicates that a virtual private network (VPN) connection is used automatically.






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
Add-CMWindowsAppxDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-Comment <String>] [-ContentFallback] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-SlowNetworkDeploymentMode {DoNothing | Download}] [-TriggerVpn] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMWindowsAppxDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-Comment <String>] [-ContentFallback] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-SlowNetworkDeploymentMode {DoNothing | Download}] [-TriggerVpn] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMWindowsAppxDeploymentType [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-Comment <String>] [-ContentFallback] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-SlowNetworkDeploymentMode {DoNothing | Download}] [-TriggerVpn] [-Confirm] [-WhatIf] [<CommonParameters>]
```
