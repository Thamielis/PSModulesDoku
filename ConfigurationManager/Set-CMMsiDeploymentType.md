Set-CMMsiDeploymentType
-----------------------




### Synopsis
Configure a Windows Installer deployment type.



---


### Description

Use this cmdlet to configure the settings for a Windows Installer (MSI) deployment type on an application.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMMsiDeploymentType](Add-CMMsiDeploymentType)



* [Get-CMDeploymentType](Get-CMDeploymentType)



* [Remove-CMDeploymentType](Remove-CMDeploymentType)



* [Get-CMApplication](Get-CMApplication)



* [Create applications in Configuration Manager](Create applications in Configuration Manager)





---


### Examples
#### Example 1: Modify a Windows Installer deployment type
```PowerShell
Set-CMMSiDeploymentType -ApplicationName "testMsi" -DeploymentTypeName "DTMsi" -NewName "DTMsi_Updated" -AddLanguage "en-US","zh-CN" -Comment "New Deployment Type-updated" -EstimatedRuntimeMins 14 -LogonRequirementType OnlyWhenNoUserLoggedOn
```
For other examples with requirement rules and detection methods, see Set-CMScriptDeploymentType (Set-CMScriptDeploymentType.md) and [Add-CMMsiDeploymentType](Add-CMMsiDeploymentType.md).


---


### Parameters
#### **AddDetectionClause**

Specify an array of detection method clauses for this deployment type. To create a detection clause, use one of the following cmdlets:


* New-CMDetectionClauseDirectory (New-CMDetectionClauseDirectory.md)- New-CMDetectionClauseFile (New-CMDetectionClauseFile.md)- New-CMDetectionClauseRegistryKey (New-CMDetectionClauseRegistryKey.md)- New-CMDetectionClauseRegistryKeyValue (New-CMDetectionClauseRegistryKeyValue.md)- New-CMDetectionClauseWindowsInstaller (New-CMDetectionClauseWindowsInstaller.md)Save the output of these cmdlets into a variable. Then specify those variables as an array for this parameter. For example, `-AddDetectionClause $clauseFile1,$clauseFile2,$clauseFile3`.


You can also use Get-CMDeploymentTypeDetectionClause (Get-CMDeploymentTypeDetectionClause.md)to get an existing detection clause from another application.






|Type                 |Required|Position|PipelineInput|Aliases            |
|---------------------|--------|--------|-------------|-------------------|
|`[DetectionClause[]]`|false   |named   |False        |AddDetectionClauses|



#### **AddLanguage**

Specify an array of language tags that the deployment type supports. For example, to add Russian (Russia) , specify the tag `ru-RU`.


For more information and a list of language tags, see Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type        |Required|Position|PipelineInput|Aliases                                |
|------------|--------|--------|-------------|---------------------------------------|
|`[String[]]`|false   |named   |False        |AddLanguages<br/>Languages<br/>Language|



#### **AddRequirement**

Specify an array of requirement objects for the deployment type. To create a requirement rule object, use one of the following cmdlets:


* New-CMRequirementRuleActiveDirectorySiteValue (New-CMRequirementRuleActiveDirectorySiteValue.md)- New-CMRequirementRuleBooleanValue (New-CMRequirementRuleBooleanValue.md)- New-CMRequirementRuleCMSiteValue (New-CMRequirementRuleCMSiteValue.md)- New-CMRequirementRuleCommonValue (New-CMRequirementRuleCommonValue.md)- New-CMRequirementRuleDeviceOwnershipValue (New-CMRequirementRuleDeviceOwnershipValue.md)- New-CMRequirementRuleExistential (New-CMRequirementRuleExistential.md)- New-CMRequirementRuleExpression (New-CMRequirementRuleExpression.md)- New-CMRequirementRuleFileAttributeValue (New-CMRequirementRuleFileAttributeValue.md)- New-CMRequirementRuleFilePermissionValue (New-CMRequirementRuleFilePermissionValue.md)- New-CMRequirementRuleFreeDiskSpaceValue (New-CMRequirementRuleFreeDiskSpaceValue.md)- New-CMRequirementRuleInputTypeValue (New-CMRequirementRuleInputTypeValue.md)- New-CMRequirementRuleOperatingSystemLanguageValue (New-CMRequirementRuleOperatingSystemLanguageValue.md)- New-CMRequirementRuleOperatingSystemValue (New-CMRequirementRuleOperatingSystemValue.md)- New-CMRequirementRuleOUValue (New-CMRequirementRuleOUValue.md)- New-CMRequirementRuleRegistryKeyPermissionValue (New-CMRequirementRuleRegistryKeyPermissionValue.md)- New-CMRequirementRuleScreenResolutionValue (New-CMRequirementRuleScreenResolutionValue.md)Starting in version 2111, you can use the Get-CMDeploymentTypeRequirement (Get-CMDeploymentTypeRequirement.md)cmdlet to copy rules from another deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Rule[]]`|false   |named   |False        |



#### **Application**

Specify an application object for this deployment type. To get this object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ApplicationId**

Specify the ID of the application for this deployment type.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CI_ID<br/>CIId|



#### **ApplicationName**

Specify the name of the application for this deployment type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CacheContent**

Set this parameter to `$true` to save content indefinitely in the client cache.






|Type       |Required|Position|PipelineInput|Aliases                    |
|-----------|--------|--------|-------------|---------------------------|
|`[Boolean]`|false   |named   |False        |PersistContentInClientCache|



#### **Comment**

Specify an optional description for the deployment type.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |AdministratorComment|



#### **ContentFallback**

If you set this parameter to `$true`, when the content isn't available on any distribution points in the client's current or neighbor boundary groups, the client can use distribution points in the site default boundary group.






|Type       |Required|Position|PipelineInput|Aliases                                                                            |
|-----------|--------|--------|-------------|-----------------------------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |EnableContentLocationFallback<br/>AllowClientsToUseFallbackSourceLocationForContent|



#### **ContentLocation**

Specifies the network source path of the MSI file. The site system server requires permission to read the content files.


Starting in version 2107, you can specify the path of the MSI file or the path to the folder that contains the MSI.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentTypeName**

Specify the name of the deployment type to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DetectionClauseConnector**

When you use the GroupDetectionClauses parameter to group detection clauses, use this parameter to specify the connector.


The following example defines the OR connector: `@{"LogicalName"=$clauseFile3.Setting.LogicalName;"Connector"="OR"}`






|Type           |Required|Position|PipelineInput|Aliases                  |
|---------------|--------|--------|-------------|-------------------------|
|`[Hashtable[]]`|false   |named   |False        |DetectionClauseConnectors|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableBranchCache**

This parameter is deprecated. BranchCache is always enabled on clients, and they use it if the distribution point supports it.






|Type       |Required|Position|PipelineInput|Aliases                               |
|-----------|--------|--------|-------------|--------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowClientsToShareContentOnSameSubnet|



#### **EstimatedRuntimeMins**

Specify the estimated installation time, in minutes, of this deployment type for the application. Software Center displays this estimate to the user before the application installs.






|Type     |Required|Position|PipelineInput|Aliases                                                                                       |
|---------|--------|--------|-------------|----------------------------------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |EstimatedInstallationTimeMinutes<br/>EstimatedInstallationTimeMins<br/>EstimatedRunTimeMinutes|



#### **Force**

Forces the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[Switch]`|false   |named   |False        |ForceForUnknownPublisher|



#### **Force32Bit**

Set this parameter to `$true` to run the install and uninstall programs as 32-bit processes on 64-bit clients.






|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |Force32BitInstaller|



#### **ForceScriptDetection32Bit**

If you use a custom script to detect the presence of this deployment type, set this parameter to `$true` to run the script as a 32-bit process on 64-bit clients.






|Type       |Required|Position|PipelineInput|Aliases                  |
|-----------|--------|--------|-------------|-------------------------|
|`[Boolean]`|false   |named   |False        |Force32BitDetectionScript|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GroupDetectionClauses**

When you configure rules to detect the presence of this deployment type, use this parameter to group clauses. To create a detection clause, use one of the following cmdlets:


* New-CMDetectionClauseDirectory (New-CMDetectionClauseDirectory.md)- New-CMDetectionClauseFile (New-CMDetectionClauseFile.md)- New-CMDetectionClauseRegistryKey (New-CMDetectionClauseRegistryKey.md)- New-CMDetectionClauseRegistryKeyValue (New-CMDetectionClauseRegistryKeyValue.md)- New-CMDetectionClauseWindowsInstaller (New-CMDetectionClauseWindowsInstaller.md)Save the output of these cmdlets into a variable. Then use the following format to group clauses: `$clause2.Setting.LogicalName, $clause3.Setting.LogicalName`.


> [!TIP] > In the Configuration Manager console, when you select the Group action, the clauses show parentheses before and after the grouped clauses.






|Type        |Required|Position|PipelineInput|Aliases                           |
|------------|--------|--------|-------------|----------------------------------|
|`[String[]]`|false   |named   |False        |GroupDetectionClausesByLogicalName|



#### **InputObject**

Specify a deployment type object to configure. To get this object, use the Get-CMDeploymentType (Get-CMDeploymentType.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeploymentType|



#### **InstallationBehaviorType**

Specify the installation behavior for this deployment type:


* `InstallForUser`: The client only installs the application for the user to whom you deploy the application.


* `InstallForSystem`: The client installs the application only once. It's available to all users.


* `InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser`: If you deploy the application to a device, the client installs it for all users. If you deploy the application to a user, the client only installs it for that user.



Valid Values:

* InstallForUser
* InstallForSystem
* InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[InstallationBehaviorType]`|false   |named   |False        |



#### **InstallCommand**

Specify the installation program command line to install the Windows Installer package.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |named   |False        |InstallationProgram|



#### **InstallWorkingDirectory**

Specify the path to use as the working directory when the client runs the InstallCommand .






|Type      |Required|Position|PipelineInput|Aliases                              |
|----------|--------|--------|-------------|-------------------------------------|
|`[String]`|false   |named   |False        |InstallationStartIn<br/>InstallFolder|



#### **LogonRequirementType**

Specify the requirement for a signed-in user:


* `OnlyWhenNoUserLoggedOn`: Only when no user is signed into Windows.


* `OnlyWhenUserLoggedOn`: Only when a user is signed in. This option is the default.


* `WhetherOrNotUserLoggedOn`: Whether or not a user is signed in.




> [!NOTE]     > The value `WhereOrNotUserLoggedOn` is deprecated. It's replaced by `WhetherOrNotUserLoggedOn`.

If you set InstallationBehaviorType to `InstallForUser`, then you can't set this parameter.




Valid Values:

* OnlyWhenUserLoggedOn
* WhereOrNotUserLoggedOn
* WhereOrNotUserLoggedOn
* OnlyWhenNoUserLoggedOn






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[LogonRequirementType]`|false   |named   |False        |



#### **MaximumRuntimeMins**

Specify the maximum allowed run time of the deployment program for this application. Set an integer value in minutes.






|Type     |Required|Position|PipelineInput|Aliases                                                                             |
|---------|--------|--------|-------------|------------------------------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |MaximumAllowedRunTimeMinutes<br/>MaximumAllowedRunTimeMins<br/>MaximumRunTimeMinutes|



#### **NewName**

Specify a new name to rename this deployment type.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |NewDeploymentTypeName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProductCode**

Specify the MSI product code to set as the detection method. When you use this parameter, it overwrites any other detection methods.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RebootBehavior**

Specify the post-installation behavior:


* `BasedOnExitCode`: Determine behavior based on return codes.


* `NoAction`: No specific action.


* `ProgramReboot`: The software install program might force a device restart.


* `ForceReboot`: Configuration Manager client will force a mandatory device restart.


For more information on these behaviors, see Create applications in Configuration Manager (/mem/configmgr/apps/deploy-use/create-applications#deployment-type-properties-user-experience-options).



Valid Values:

* BasedOnExitCode
* NoAction
* ProgramReboot
* ForceReboot
* ForceLogOff






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[PostExecutionBehavior]`|false   |named   |False        |



#### **RemoveDetectionClause**

Specify an array of detection method clauses to remove.






|Type        |Required|Position|PipelineInput|Aliases               |
|------------|--------|--------|-------------|----------------------|
|`[String[]]`|false   |named   |False        |RemoveDetectionClauses|



#### **RemoveLanguage**

Specify an array of supported languages to remove from this deployment type.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |RemoveLanguages|



#### **RemoveRequirement**

Specify an array of requirement rules to remove from this deployment type.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Rule[]]`|false   |named   |False        |RemoveRequirements|



#### **RepairCommand**

Use this parameter to configure the repair command. Also configure the RepairWorkingDirectory parameter.


Starting in version 2006, you can specify an empty string.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|false   |named   |False        |RepairProgram|



#### **RepairWorkingDirectory**

Use this parameter to configure the repair command's working directory. Also configure the RepairCommand parameter.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|false   |named   |False        |RepairStartIn<br/>RepairFolder|



#### **RequireUserInteraction**

Set this parameter to `$true` to allow users to view and interact with the deployment type installation.






|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |RequiresUserInteraction|



#### **ScriptFile**

Specify the script file to use to detect this deployment type. Also use the ScriptLanguage parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ScriptLanguage**

If you use the ScriptFile or ScriptText parameters, use this parameter to specify the script language.



Valid Values:

* PowerShell
* VBScript
* JavaScript






|Type              |Required|Position|PipelineInput|Aliases   |
|------------------|--------|--------|-------------|----------|
|`[ScriptLanguage]`|false   |named   |False        |ScriptType|



#### **ScriptText**

Specify the text of a script to detect this deployment type. Also use the ScriptLanguage parameter.


For more information, see About custom script detection methods (/mem/configmgr/apps/deploy-use/create-applications#about-custom-script-detection-methods).






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |ScriptContent<br/>Script|



#### **SlowNetworkDeploymentMode**

When a client uses a distribution point from a neighbor boundary group or the default site boundary group, specify the deployment option:


* `DoNothing`: Don't download content


* `Download`: Download content from the distribution point and run locally



Valid Values:

* DoNothing
* Download
* DownloadContentForStreaming






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ContentHandlingMode]`|false   |named   |False        |



#### **SourceUpdateProductCode**

Specify an MSI product code. This product code is a GUID format.


Windows Source management enables an .MSI represented by this deployment type to automatically be updated or repaired from content source files on an available distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UninstallCommand**

Specifies the command line to uninstall the application.


Starting in version 2006, you can specify an empty string.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |UninstallationProgram|



#### **UninstallContentLocation**

Specify the network path to source content to use with the UninstallCommand that's different from the ContentLocation . Use this parameter when you set UninstallOption to `Different`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UninstallOption**

Specify what content to use with the UninstallCommand :


* `SameAsInstall`: The install and uninstall content are the same. This option is the default.


* `NoneRequired`: The application doesn't need content for uninstall.


* `Different`: The uninstall content is different from the install content. Use UninstallContentLocation to specify the network path to the content that's used to uninstall the application.



Valid Values:

* SameAsInstall
* NoneRequired
* Different






|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[UninstallContentSetting]`|false   |named   |False        |



#### **UninstallWorkingDirectory**

Specify the path to use as the working directory when the client runs the UninstallCommand .






|Type      |Required|Position|PipelineInput|Aliases                                  |
|----------|--------|--------|-------------|-----------------------------------------|
|`[String]`|false   |named   |False        |UninstallationStartIn<br/>UninstallFolder|



#### **UserInteractionMode**

Specify the installation program visibility:


* `Normal`: The deployment type runs in the normal mode based on system and program defaults. This mode is the default.


* `Minimized`: The deployment type runs minimized on client devices. Users might see the installation activity in the notification area or taskbar.


* `Maximized`: The deployment type runs maximized on client devices. Users see all installation activity.


* `Hidden`: The deployment type runs hidden on client devices. Users see no installation activity.



Valid Values:

* Normal
* Minimized
* Maximized
* Hidden






|Type                   |Required|Position|PipelineInput|Aliases                      |
|-----------------------|--------|--------|-------------|-----------------------------|
|`[UserInteractionMode]`|false   |named   |False        |InstallationProgramVisibility|



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
Set-CMMsiDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -Application <IResultObject> [-CacheContent <Boolean>] [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EstimatedRuntimeMins <Int32>] [-Force] [-Force32Bit <Boolean>] [-ForceScriptDetection32Bit <Boolean>] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] [-InstallCommand <String>] [-InstallWorkingDirectory <String>] [-LogonRequirementType {OnlyWhenUserLoggedOn | WhereOrNotUserLoggedOn | WhetherOrNotUserLoggedOn | OnlyWhenNoUserLoggedOn}] [-MaximumRuntimeMins <Int32>] [-NewName <String>] [-PassThru] [-ProductCode <String>] [-RebootBehavior {BasedOnExitCode | NoAction | ForceReboot | ProgramReboot}] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-RepairCommand <String>] [-RepairWorkingDirectory <String>] [-RequireUserInteraction <Boolean>] [-ScriptFile <String>] [-ScriptLanguage {PowerShell | VBScript | JavaScript}] [-ScriptText <String>] [-SlowNetworkDeploymentMode {DoNothing | Download}] [-SourceUpdateProductCode <String>] [-UninstallCommand <String>] [-UninstallContentLocation <String>] [-UninstallOption {SameAsInstall | NoneRequired | Different}] [-UninstallWorkingDirectory <String>] [-UserInteractionMode {Normal | Minimized | Maximized | Hidden}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMsiDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationId <Int32> [-CacheContent <Boolean>] [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EstimatedRuntimeMins <Int32>] [-Force] [-Force32Bit <Boolean>] [-ForceScriptDetection32Bit <Boolean>] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] [-InstallCommand <String>] [-InstallWorkingDirectory <String>] [-LogonRequirementType {OnlyWhenUserLoggedOn | WhereOrNotUserLoggedOn | WhetherOrNotUserLoggedOn | OnlyWhenNoUserLoggedOn}] [-MaximumRuntimeMins <Int32>] [-NewName <String>] [-PassThru] [-ProductCode <String>] [-RebootBehavior {BasedOnExitCode | NoAction | ForceReboot | ProgramReboot}] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-RepairCommand <String>] [-RepairWorkingDirectory <String>] [-RequireUserInteraction <Boolean>] [-ScriptFile <String>] [-ScriptLanguage {PowerShell | VBScript | JavaScript}] [-ScriptText <String>] [-SlowNetworkDeploymentMode {DoNothing | Download}] [-SourceUpdateProductCode <String>] [-UninstallCommand <String>] [-UninstallContentLocation <String>] [-UninstallOption {SameAsInstall | NoneRequired | Different}] [-UninstallWorkingDirectory <String>] [-UserInteractionMode {Normal | Minimized | Maximized | Hidden}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMsiDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] -ApplicationName <String> [-CacheContent <Boolean>] [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] -DeploymentTypeName <String> [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EstimatedRuntimeMins <Int32>] [-Force] [-Force32Bit <Boolean>] [-ForceScriptDetection32Bit <Boolean>] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] [-InstallCommand <String>] [-InstallWorkingDirectory <String>] [-LogonRequirementType {OnlyWhenUserLoggedOn | WhereOrNotUserLoggedOn | WhetherOrNotUserLoggedOn | OnlyWhenNoUserLoggedOn}] [-MaximumRuntimeMins <Int32>] [-NewName <String>] [-PassThru] [-ProductCode <String>] [-RebootBehavior {BasedOnExitCode | NoAction | ForceReboot | ProgramReboot}] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-RepairCommand <String>] [-RepairWorkingDirectory <String>] [-RequireUserInteraction <Boolean>] [-ScriptFile <String>] [-ScriptLanguage {PowerShell | VBScript | JavaScript}] [-ScriptText <String>] [-SlowNetworkDeploymentMode {DoNothing | Download}] [-SourceUpdateProductCode <String>] [-UninstallCommand <String>] [-UninstallContentLocation <String>] [-UninstallOption {SameAsInstall | NoneRequired | Different}] [-UninstallWorkingDirectory <String>] [-UserInteractionMode {Normal | Minimized | Maximized | Hidden}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMsiDeploymentType [-AddDetectionClause <DetectionClause[]>] [-AddLanguage <String[]>] [-AddRequirement <Rule[]>] [-CacheContent <Boolean>] [-Comment <String>] [-ContentFallback <Boolean>] [-ContentLocation <String>] [-DetectionClauseConnector <Hashtable[]>] [-DisableWildcardHandling] [-EnableBranchCache <Boolean>] [-EstimatedRuntimeMins <Int32>] [-Force] [-Force32Bit <Boolean>] [-ForceScriptDetection32Bit <Boolean>] [-ForceWildcardHandling] [-GroupDetectionClauses <String[]>] -InputObject <IResultObject> [-InstallationBehaviorType {InstallForUser | InstallForSystem | InstallForSystemIfResourceIsDeviceOtherwiseInstallForUser}] [-InstallCommand <String>] [-InstallWorkingDirectory <String>] [-LogonRequirementType {OnlyWhenUserLoggedOn | WhereOrNotUserLoggedOn | WhetherOrNotUserLoggedOn | OnlyWhenNoUserLoggedOn}] [-MaximumRuntimeMins <Int32>] [-NewName <String>] [-PassThru] [-ProductCode <String>] [-RebootBehavior {BasedOnExitCode | NoAction | ForceReboot | ProgramReboot}] [-RemoveDetectionClause <String[]>] [-RemoveLanguage <String[]>] [-RemoveRequirement <Rule[]>] [-RepairCommand <String>] [-RepairWorkingDirectory <String>] [-RequireUserInteraction <Boolean>] [-ScriptFile <String>] [-ScriptLanguage {PowerShell | VBScript | JavaScript}] [-ScriptText <String>] [-SlowNetworkDeploymentMode {DoNothing | Download}] [-SourceUpdateProductCode <String>] [-UninstallCommand <String>] [-UninstallContentLocation <String>] [-UninstallOption {SameAsInstall | NoneRequired | Different}] [-UninstallWorkingDirectory <String>] [-UserInteractionMode {Normal | Minimized | Maximized | Hidden}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
