Add-CMDeploymentType
--------------------




### Synopsis
Adds a deployment type for a Configuration Manager deployment application. This cmdlet is deprecated.



---


### Description

This cmdlet is deprecated.



Use one of the following cmdlets:



* Add-CMAppv5XDeploymentType (Add-CMAppv5XDeploymentType.md)* Add-CMAppvDeploymentType (Add-CMAppvDeploymentType.md)* Add-CMMacDeploymentType (Add-CMMacDeploymentType.md)* Add-CMMobileMsiDeploymentType (Add-CMMobileMsiDeploymentType.md)* Add-CMMsiDeploymentType (Add-CMMsiDeploymentType.md)* Add-CMScriptDeploymentType (Add-CMScriptDeploymentType.md)* Add-CMWebApplicationDeploymentType (Add-CMWebApplicationDeploymentType.md)* Add-CMWindowsAppxDeploymentType (Add-CMWindowsAppxDeploymentType.md)* Add-CMWindowsPhoneDeploymentType (Add-CMWindowsPhoneDeploymentType.md)* Add-CMWindowsPhoneStoreDeploymentType (Add-CMWindowsPhoneStoreDeploymentType.md)* Add-CMWindowsStoreDeploymentType (Add-CMWindowsStoreDeploymentType.md)The Add-CMDeploymentType cmdlet adds a deployment type for an application. A deployment type is contained within an application and contains the information that Configuration Manager requires to install software. A deployment type also contains rules that specify if and how the software is deployed.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Remove-CMDeploymentType](Remove-CMDeploymentType)



* [Set-CMDeploymentType](Set-CMDeploymentType)





---


### Examples
#### Example 1: Add an Windows Installer deployment type to an application
```PowerShell
PS XYZ:\>Add-CMDeploymentType -MsiInstaller -ApplicationName "App01d2012" -AutoIdentifyFromIntallationFile -InstallationFileLocation "\\CMCEN\D02\Software\RDCMan.msi" -ForceForUnknownPublisher $True
```
This command adds a Windows Installer deployment type for the application named App01d2012. The command uses the AutoIdentifyFromIntallationFile parameter to extract information about the deployment type from the content file, and specifies the path of the installation package. The command uses the ForceForUnknownPublisher parameter to specify that the deployment type verifies the signature of the content file.
#### Example 2: Add a deployment type that uses a script
```PowerShell
PS XYZ:\>Add-CMDeploymentType -ApplicationName "App02d2012" -MsiInstaller -DeploymentTypeName "Type01" -AdministratorComment "Div A script" -Language Afrikaans,Arabic -InstallationProgram 'msiexec /i "\\atd-dist01\Public\CM\DTeam\FeatureData\OSD\Tbreck\Setup1.msi"' -DetectDeploymentTypeByCustomScript -ScriptType VBScript -ScriptContent "1231231" -RunScriptAs32bitProcessOn64bitClient $True
```
This command adds a Windows Installer deployment type for the application named App02d2012. The command specifies the name Type01 for the deployment type. The command adds a description for the deployment type, and specifies that the deployment type supports Afrikaans and Arabic. The command uses the InstallationProgram to specify the command line for the Windows Installer.


The command specifies that the deployment type uses a custom script to detect the presence of this deployment type. The command specifies that the script type is VBScript and specifies the script language that you will use to detect the deployment type. The command specifies that the deployment type uses Microsoft Windows-32-on-Windows-64 (WOW64) subsystem to run a script on a 64-bit client computer.


---


### Parameters
#### **AddRequirement**

Adds an array of requirements for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Rule[]]`|false   |named   |False        |



#### **AdministratorComment**

Specifies a description for the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **AndroidGooglePlayInstaller**








|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[Switch]`|true    |named   |False        |AndroidDeepLinkInstaller|



#### **AndroidInstaller**

Indicates that the deployment type detects application information and deployment types from an app package for Android (.apk) file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ApplicationName**

Specifies the name of the application that is associated with the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ApplicationNameInWindowsStore**

Specifies the name of the application in the Windows Store.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **AppV5xInstaller**

Indicates that the deployment type detects application information and deployment types from a Application Virtualization (App-V) 5.0  .appv package file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **AppvInstaller**

Indicates that the deployment detects application information and deployment types from an App-V 4.0 manifest .xml file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **AutoIdentifyFromInstallationFile**

Indicates that the deployment type extracts information from the content file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ContentLocation**

Specifies the path of the content. The site system server requires permission to read the content files.






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[String]`|true    |named   |False        |InstallationFileLocation<br/>WebAppUrl|



#### **DeploymentTypeName**

Specifies the name of a deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DetectDeploymentTypeByCustomScript**

Indicates that the deployment type uses a custom script to detect the presence of this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableBranchCache**








|Type       |Required|Position|PipelineInput|Aliases                               |
|-----------|--------|--------|-------------|--------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowClientsToShareContentOnSameSubnet|



#### **EnableContentLocationFallback**








|Type       |Required|Position|PipelineInput|Aliases                                          |
|-----------|--------|--------|-------------|-------------------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowClientsToUseFallbackSourceLocationForContent|



#### **EnableUserUninstall**








|Type       |Required|Position|PipelineInput|Aliases                                                   |
|-----------|--------|--------|-------------|----------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowUserToUninstall<br/>AllowsUsersToUninstallThisContent|



#### **EstimatedInstallationTimeMins**








|Type     |Required|Position|PipelineInput|Aliases                         |
|---------|--------|--------|-------------|--------------------------------|
|`[Int32]`|false   |named   |False        |EstimatedInstallationTimeMinutes|



#### **Force32BitDetectionScript**








|Type       |Required|Position|PipelineInput|Aliases                             |
|-----------|--------|--------|-------------|------------------------------------|
|`[Boolean]`|false   |named   |False        |RunScriptAs32BitProcessOn64BitClient|



#### **Force32BitInstaller**








|Type       |Required|Position|PipelineInput|Aliases                                          |
|-----------|--------|--------|-------------|-------------------------------------------------|
|`[Boolean]`|false   |named   |False        |RunInstallationProgramAs32BitProcessOn64BitClient|



#### **ForceForUnknownPublisher**

Indicates whether the deployment type requires file signature verification.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|false   |named   |True (ByValue)|Application|



#### **InstallationBehaviorType**

Specifies the installation behavior of the deployment type. Valid values are:


* InstallForSystem


* InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser


* InstallForUser



Valid Values:

* InstallForUser
* InstallForSystem
* InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[InstallationBehaviorType]`|false   |named   |False        |



#### **InstallationCommandLine**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstallationProgram**

Specifies the command line for the Windows Installer package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstallationProgramVisibility**

Specifies the mode in which the deployment type runs on client devices. Valid values are:


* Normal


* Minimized


* Maximized


* Hidden



Valid Values:

* Normal
* Minimized
* Maximized
* Hidden






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[UserInteractionMode]`|false   |named   |False        |



#### **InstallationStartIn**

Specifies the folder that contains the installation program for the deployment type. This folder can be an absolute path on the client, or a path to the distribution point folder that contains the installation files.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **IosAppStoreInstaller**








|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[Switch]`|true    |named   |False        |IosDeepLinkInstaller|



#### **IosInstaller**

Indicates that the deployment type detects application information and deployment types from an app package for iOS (.ipa) file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **Language**

Specifies an array of languages that the deployment type supports.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **LogonRequirementType**

Specifies the logon requirement for the deployment type. Valid values are:


* OnlyWhenNoUserLoggedOn


* OnlyWhenUserLoggedOn


* WhereOrNotUserLoggedOn



Valid Values:

* OnlyWhenUserLoggedOn
* WhereOrNotUserLoggedOn
* WhereOrNotUserLoggedOn
* OnlyWhenNoUserLoggedOn






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[LogonRequirementType]`|false   |named   |False        |



#### **MacInstaller**

Indicates that the deployment type detects application information and deployment types from a Mac OS X Installer (.cmmac) file that was created by using the CMAppUtil tool.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ManualSpecifyDeploymentType**

Do not use. Configuration Manager does not currently use this parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MaximumAllowedRunTimeMins**








|Type     |Required|Position|PipelineInput|Aliases                     |
|---------|--------|--------|-------------|----------------------------|
|`[Int32]`|false   |named   |False        |MaximumAllowedRunTimeMinutes|



#### **MobileMsiInstaller**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **MsiInstaller**

Indicates that the deployment type detects application information and deployment types from a Windows Installer (.msi) file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **OnFastNetworkMode**

Specifies the installation behavior of the deployment type on a fast network. The acceptable values for this parameter are:


* RunFromNetwork


* RunLocal



Valid Values:

* RunLocal
* RunFromNetwork
* DownloadContentForStreaming






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[OnFastNetworkMode]`|false   |named   |False        |



#### **OnSlowNetworkMode**

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



#### **PersistContentInClientCache**

Indicates whether the deployment type saves content in cache indefinitely on the client computer.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PfxFileLocation**

Specifies the path of the Personal Information Exchange (PFX) file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PfxFilePassword**

Specifies the password, as a secure string, for the PFX file.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **RemoteComputerName**

Specifies a remote computer name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RequireUserInteraction**








|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |RequiresUserInteraction|



#### **ScriptContent**

Specifies the script language that you want to use to detect the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ScriptInstaller**

Indicates that the deployment type uses a script to detect the presence of this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ScriptType**

Specifies the script language that you want to use to detect the deployment type.



Valid Values:

* PowerShell
* VBScript
* JavaScript






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ScriptLanguage]`|true    |named   |False        |



#### **SignContentFile**

Indicates whether the deployment type requires a signed content file.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SignedContentFileLocation**

Specifies the path of the signed content file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TriggerVpn**

@{Text=}






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UninstallProgram**

Specifies the name of the uninstall program and any parameters it requires.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UninstallStartIn**

Specifies the folder that contains the uninstall program for the deployment type. This folder can be an absolute path on the client, or a path that is relative to the distribution point folder that contains the package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WebAppInstaller**

Indicates that this cmdlet uses a web application installer for the deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **Windows8AppInstaller**

Indicates that the deployment type detects application information and deployment types from a Windows app package (.appx) file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **WindowsPhone8Installer**








|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|true    |named   |False        |WinPhone8Installer|



#### **WindowsPhoneStoreInstaller**








|Type      |Required|Position|PipelineInput|Aliases                                                   |
|----------|--------|--------|-------------|----------------------------------------------------------|
|`[Switch]`|true    |named   |False        |WinPhone8DeeplinkInstaller<br/>WindowsPhone8StoreInstaller|



#### **WindowsStoreInstaller**








|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[Switch]`|true    |named   |False        |DeeplinkInstaller|



#### **WMInstaller**

Indicates that the deployment type detects application information and deployment types from a Windows Mobile cabinet (.cab) file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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
* IResultObject#SMS_DeploymentType






---


### Notes




---


### Syntax
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-Force32BitInstaller <Boolean>] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] [-InstallationProgram <String>] [-Language <String[]>] -MsiInstaller [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -AndroidInstaller [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] -AppV5xInstaller [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] [-OnFastNetworkMode {RunLocal | RunFromNetwork | DownloadContentForStreaming}] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] -AppvInstaller [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] [-OnFastNetworkMode {RunLocal | RunFromNetwork | DownloadContentForStreaming}] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] -IosAppStoreInstaller [-Language <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] -IosInstaller [-Language <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] -MacInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectDeploymentTypeByCustomScript] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EnableContentLocationFallback <Boolean>] [-EstimatedInstallationTimeMins <Int32>] [-Force32BitDetectionScript <Boolean>] [-Force32BitInstaller <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] -InstallationProgram <String> [-InstallationProgramVisibility {Normal | Minimized | Maximized | Hidden}] [-InstallationStartIn <String>] [-Language <String[]>] [-LogonRequirementType {OnlyWhenUserLoggedOn | WhereOrNotUserLoggedOn | WhetherOrNotUserLoggedOn | OnlyWhenNoUserLoggedOn}] [-ManualSpecifyDeploymentType] [-MaximumAllowedRunTimeMins <Int32>] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PersistContentInClientCache <Boolean>] [-RequireUserInteraction <Boolean>] -ScriptContent <String> -ScriptInstaller -ScriptType {PowerShell | VBScript | JavaScript} [-UninstallProgram <String>] [-UninstallStartIn <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] -WebAppInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-TriggerVpn <Boolean>] -Windows8AppInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] -ApplicationNameInWindowsStore <String> [-AutoIdentifyFromInstallationFile] [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] -RemoteComputerName <String> -WindowsStoreInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] -WindowsPhone8Installer [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] -WindowsPhoneStoreInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-EnableUserUninstall <Boolean>] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] [-ManualSpecifyDeploymentType] [-PfxFileLocation <String>] [-PfxFilePassword <SecureString>] [-SignContentFile <Boolean>] [-SignedContentFileLocation <String>] -WMInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-InstallationCommandLine <String>] [-Language <String[]>] -MobileMsiInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationName <String>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] [-ManualSpecifyDeploymentType] -MobileMsiInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeploymentType [-AdministratorComment <String>] -AndroidGooglePlayInstaller [-ApplicationName <String>] [-AutoIdentifyFromInstallationFile] -ContentLocation <String> [-DeploymentTypeName <String>] [-DisableWildcardHandling] [-ForceForUnknownPublisher <Boolean>] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-Language <String[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
