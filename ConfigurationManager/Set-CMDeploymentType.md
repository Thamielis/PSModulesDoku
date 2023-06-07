Set-CMDeploymentType
--------------------




### Synopsis
Change a deployment type for a Configuration Manager application.



---


### Description

The Set-CMDeploymentType cmdlet changes a deployment type for an application in Configuration Manager. A deployment type is a part of the application that defines how that application installs on devices.



You can also use this cmdlet to change the priority for dependencies of the deployment type. Configuration Manager evaluates and installs dependencies of a deployment type in order of priorities before it installs the deployment type.



For more information, see Introduction to application management - Deployment types (/mem/configmgr/apps/understand/introduction-to-application-management#deployment-type).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Remove-CMDeploymentType](Remove-CMDeploymentType)





---


### Examples
#### Example 1: Increase the priority of a deployment application
```PowerShell
Set-CMDeploymentType -ApplicationName "2 - Child" -DeploymentTypeName "Configuration Manager Console - Windows Installer (Native)" -Priority Increase
```



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



#### **ApplicationName**

Specifies the name of the deployment application that contains the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ApplicationNameInWindowsStore**

Specifies the name of the application in the Windows Store.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **AppV5xInstaller**

Indicates that the deployment type detects application information and deployment types from a Application Virtualization (App-V) 5.0 .appv package file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **AppVInstaller**

Indicates that the deployment type detects application information and deployment types from an App-V .appv package file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ClearRequirements**

Indicates that this cmdlet clears the deployment type requirements.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ContentLocation**

Specifies the path of the content. The site system server requires permission to read the content files.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |InstallationFileLocation|



#### **DeploymentTypeId**

Specifies the type ID for a deployment type.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID<br/>Id|



#### **DeploymentTypeName**

Specifies the name of a deployment type.






|Type      |Required|Position|PipelineInput|Aliases                      |
|----------|--------|--------|-------------|-----------------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName<br/>Name|



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

Indicates that clients that use Windows BranchCache are allowed to download content from an on-premises distribution point. Content downloads from cloud-based distribution points can always be shared by clients that use Windows BranchCache.






|Type       |Required|Position|PipelineInput|Aliases                               |
|-----------|--------|--------|-------------|--------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowClientsToShareContentOnSameSubnet|



#### **EnableContentLocationFallback**

Indicate whether allows clients to use fall back source location for the content.






|Type       |Required|Position|PipelineInput|Aliases                                          |
|-----------|--------|--------|-------------|-------------------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowClientsToUseFallbackSourceLocationForContent|



#### **EnablePeerToPeerContentDistribution**

Indicates whether clients can distribute content to other clients.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUserUninstall**

Indicate whether to enable user uninstall.






|Type       |Required|Position|PipelineInput|Aliases                                                   |
|-----------|--------|--------|-------------|----------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowUserToUninstall<br/>AllowsUsersToUninstallThisContent|



#### **EstimatedInstallationTimeMins**

Specifies an estimated installation time in minutes.






|Type     |Required|Position|PipelineInput|Aliases                         |
|---------|--------|--------|-------------|--------------------------------|
|`[Int32]`|false   |named   |False        |EstimatedInstallationTimeMinutes|



#### **Force32BitDetectionScript**

Indicates whether to run script as 32-bit process on 64-bit clients.






|Type       |Required|Position|PipelineInput|Aliases                             |
|-----------|--------|--------|-------------|------------------------------------|
|`[Boolean]`|false   |named   |False        |RunScriptAs32BitProcessOn64BitClient|



#### **Force32BitInstaller**

Indicates whether to run installer as 32-bit process on 64-bit clients.






|Type       |Required|Position|PipelineInput|Aliases                                                      |
|-----------|--------|--------|-------------|-------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |RunInstallationAndUninstallProgramAs32BitProcessOn64BitClient|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies a deployment type object for Configuration Manager. To obtain a deployment type object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **InstallationBehaviorType**

Specifies the installation behavior of the deployment type.



Valid Values:

* InstallForUser
* InstallForSystem
* InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[InstallationBehaviorType]`|false   |named   |False        |



#### **InstallationCommandLine**

Specify the command line to install the application.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstallationProgram**

Specifies the command line for the Windows Installer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstallationProgramVisibility**

Specifies the mode in which the deployment type runs on client devices.



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



#### **Language**

Specifies an array of languages that the deployment type supports.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **LoadContentIntoAppVCacheBeforeLaunch**

Indicates whether to load the content into the AppV cache when you deploy the application.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **LogonRequirementType**

Specifies the logon requirement for the deployment type.



Valid Values:

* OnlyWhenUserLoggedOn
* WhereOrNotUserLoggedOn
* WhereOrNotUserLoggedOn
* OnlyWhenNoUserLoggedOn






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[LogonRequirementType]`|false   |named   |False        |



#### **MacInstaller**

Indicates that the deployment type detects application information and deployment types from a macOS installer (.cmmac) file that was created by using the CMAppUtil tool.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **MacRebootBehavior**

Specifies the reboot behavior for computers running macOS.



Valid Values:

* NoAction
* ForceReboot






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[MacRebootBehavior]`|false   |named   |False        |



#### **MaximumAllowedRunTimeMins**

Specifies the maximum run time in minutes.






|Type     |Required|Position|PipelineInput|Aliases                     |
|---------|--------|--------|-------------|----------------------------|
|`[Int32]`|false   |named   |False        |MaximumAllowedRunTimeMinutes|



#### **MobileMsiInstaller**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **MsiOrScriptInstaller**

Indicates that the deployment uses a script installer program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **NewDeploymentTypeName**

Specifies the name of a new deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **OnFastNetworkMode**

Specifies the installation behavior of the deployment type on a fast network.



Valid Values:

* RunLocal
* RunFromNetwork
* DownloadContentForStreaming






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[OnFastNetworkMode]`|false   |named   |False        |



#### **OnSlowNetworkMode**

Specifies the installation behavior of the deployment type on a slow network.



Valid Values:

* DoNothing
* Download
* DownloadContentForStreaming






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ContentHandlingMode]`|false   |named   |False        |



#### **PassThru**

Returns the current working object. By default, this cmdlet doesn't generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PersistContentInClientCache**

Indicates whether the deployment type saves content in cache indefinitely on the client computer.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Priority**

Specifies a change for the priority of the deployment type.



Valid Values:

* Increase
* Decrease






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[PriorityChangeType]`|false   |named   |False        |



#### **ProductCode**

Specifies the product code in the detection method for the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RebootBehavior**

Specifies the reboot behavior of the client computer.



Valid Values:

* BasedOnExitCode
* NoAction
* ProgramReboot
* ForceReboot






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[RebootBehavior]`|false   |named   |False        |



#### **RemoteComputerName**

Specifies a remote computer name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RemoveRequirement**

Removes the existing installation requirements from this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Rule[]]`|false   |named   |False        |



#### **RequireUserInteraction**

Indicates whether a user can interact with the deployment type installation to configure the installation options.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |RequiresUserInteraction|



#### **ScriptContent**

Specifies the script to detect the deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ScriptType**

Specifies the script language that you want to use to detect the deployment type.



Valid Values:

* PowerShell
* VBScript
* JavaScript






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ScriptLanguage]`|false   |named   |False        |



#### **SourceUpdateProductCode**

Specifies the Windows Installer product code to enable installation source management. Windows Source management enables an MSI represented by this deployment type to be automatically updated or repaired from content source files on an available distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TriggerVpn**

Indicates that a virtual private network (VPN) connection is used automatically.






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



#### **WindowsMobileInstaller**








|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|true    |named   |False        |WMInstaller|



#### **WindowsPhoneStoreInstaller**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **WindowsStoreInstaller**








|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[Switch]`|true    |named   |False        |DeepLinkInstaller|



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
To configure return codes on a deployment type, use the Add-CMDeploymentTypeReturnCode (Add-CMDeploymentTypeReturnCode.md)cmdlet.



---


### Syntax
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectDeploymentTypeByCustomScript] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EnableContentLocationFallback <Boolean>] [-EstimatedInstallationTimeMins <Int32>] [-Force32BitDetectionScript <Boolean>] [-Force32BitInstaller <Boolean>] [-ForceWildcardHandling] [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] [-InstallationProgram <String>] [-InstallationProgramVisibility {Normal | Minimized | Maximized | Hidden}] [-InstallationStartIn <String>] [-Language <String[]>] [-LogonRequirementType {OnlyWhenUserLoggedOn | WhereOrNotUserLoggedOn | WhetherOrNotUserLoggedOn | OnlyWhenNoUserLoggedOn}] [-MaximumAllowedRunTimeMins <Int32>] -MsiOrScriptInstaller [-NewDeploymentTypeName <String>] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-ProductCode <String>] [-RebootBehavior {BasedOnExitCode | NoAction | ProgramReboot | ForceReboot}] [-RemoveRequirement <Rule[]>] [-RequireUserInteraction <Boolean>] [-ScriptContent <String>] [-ScriptType {PowerShell | VBScript | JavaScript}] [-SourceUpdateProductCode <String>] [-UninstallProgram <String>] [-UninstallStartIn <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EnableContentLocationFallback <Boolean>] [-ForceWildcardHandling] [-Language <String[]>] [-MaximumAllowedRunTimeMins <Int32>] [-NewDeploymentTypeName <String>] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-RemoveRequirement <Rule[]>] [-TriggerVpn <Boolean>] -Windows8AppInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> -AppV5xInstaller [-ClearRequirements] -DeploymentTypeName <String> [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-EnablePeerToPeerContentDistribution <Boolean>] [-ForceWildcardHandling] [-Language <String[]>] [-NewDeploymentTypeName <String>] [-OnFastNetworkMode {RunLocal | RunFromNetwork | DownloadContentForStreaming}] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> -AppVInstaller [-ClearRequirements] -DeploymentTypeName <String> [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-EnablePeerToPeerContentDistribution <Boolean>] [-ForceWildcardHandling] [-Language <String[]>] [-LoadContentIntoAppVCacheBeforeLaunch <Boolean>] [-NewDeploymentTypeName <String>] [-OnFastNetworkMode {RunLocal | RunFromNetwork | DownloadContentForStreaming}] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-InstallationProgram <String>] [-Language <String[]>] -MacInstaller [-MacRebootBehavior {NoAction | ForceReboot}] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-EnableUserUninstall <Boolean>] [-ForceWildcardHandling] [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] -WindowsMobileInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ApplicationNameInWindowsStore <String>] [-ClearRequirements] -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Language <String[]>] [-MaximumAllowedRunTimeMins <Int32>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoteComputerName <String>] [-RemoveRequirement <Rule[]>] -WindowsStoreInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] -WebAppInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-InstallationCommandLine <String>] -Language <String[]> -MobileMsiInstaller [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-ContentLocation <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallationCommandLine <String>] -Language <String[]> -MobileMsiInstaller [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-ContentLocation <String>] [-DetectDeploymentTypeByCustomScript] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EnableContentLocationFallback <Boolean>] [-EstimatedInstallationTimeMins <Int32>] [-Force32BitDetectionScript <Boolean>] [-Force32BitInstaller <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] [-InstallationProgram <String>] [-InstallationProgramVisibility {Normal | Minimized | Maximized | Hidden}] [-InstallationStartIn <String>] [-Language <String[]>] [-LogonRequirementType {OnlyWhenUserLoggedOn | WhereOrNotUserLoggedOn | WhetherOrNotUserLoggedOn | OnlyWhenNoUserLoggedOn}] [-MaximumAllowedRunTimeMins <Int32>] -MsiOrScriptInstaller [-NewDeploymentTypeName <String>] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-ProductCode <String>] [-RebootBehavior {BasedOnExitCode | NoAction | ProgramReboot | ForceReboot}] [-RemoveRequirement <Rule[]>] [-RequireUserInteraction <Boolean>] [-ScriptContent <String>] [-ScriptType {PowerShell | VBScript | JavaScript}] [-SourceUpdateProductCode <String>] [-UninstallProgram <String>] [-UninstallStartIn <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-ContentLocation <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-ContentLocation <String>] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EnableContentLocationFallback <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-MaximumAllowedRunTimeMins <Int32>] [-NewDeploymentTypeName <String>] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-RemoveRequirement <Rule[]>] [-TriggerVpn <Boolean>] -Windows8AppInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -AppV5xInstaller [-ClearRequirements] [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-EnablePeerToPeerContentDistribution <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-NewDeploymentTypeName <String>] [-OnFastNetworkMode {RunLocal | RunFromNetwork | DownloadContentForStreaming}] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -AppVInstaller [-ClearRequirements] [-DisableWildcardHandling] [-EnableContentLocationFallback <Boolean>] [-EnablePeerToPeerContentDistribution <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-LoadContentIntoAppVCacheBeforeLaunch <Boolean>] [-NewDeploymentTypeName <String>] [-OnFastNetworkMode {RunLocal | RunFromNetwork | DownloadContentForStreaming}] [-OnSlowNetworkMode {DoNothing | Download | DownloadContentForStreaming}] [-PassThru] [-PersistContentInClientCache <Boolean>] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-ContentLocation <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallationProgram <String>] [-Language <String[]>] -MacInstaller [-MacRebootBehavior {NoAction | ForceReboot}] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-ContentLocation <String>] [-DisableWildcardHandling] [-EnableUserUninstall <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] -WindowsMobileInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ApplicationNameInWindowsStore <String>] [-ClearRequirements] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-MaximumAllowedRunTimeMins <Int32>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoteComputerName <String>] [-RemoveRequirement <Rule[]>] -WindowsStoreInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] -WebAppInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] -ApplicationName <String> [-ClearRequirements] [-ContentLocation <String>] -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] -WindowsPhoneStoreInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-AddRequirement <Rule[]>] [-AdministratorComment <String>] [-ClearRequirements] [-ContentLocation <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Language <String[]>] [-NewDeploymentTypeName <String>] [-PassThru] [-RemoveRequirement <Rule[]>] -WindowsPhoneStoreInstaller [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType -ApplicationName <String> -DeploymentTypeName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Priority {Increase | Decrease}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType -ApplicationName <String> -DeploymentTypeId <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Priority {Increase | Decrease}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDeploymentType [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Priority {Increase | Decrease}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
