Set-CMBootImage
---------------




### Synopsis
Modify an OS boot image.



---


### Description

Use this cmdlet to modify an OS boot image. Boot images are Windows Preinstallation Environment (Windows PE) images into which you boot a client computer before you install an OS.



You can add device drivers to a boot image or change its properties. Before you can add a new device driver, you must first import the driver to the Configuration Manager driver catalog and enable it.



Each version of Configuration Manager supports a specific version of the Windows Assessment and Deployment Kit (Windows ADK). You can service, or customize, boot images when they're based on a Windows PE version from the supported version of Windows ADK.



For more information, see Manage boot images with Configuration Manager (/mem/configmgr/osd/get-started/manage-boot-images).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBootImage](Get-CMBootImage)



* [New-CMBootImage](New-CMBootImage)



* [Remove-CMBootImage](Remove-CMBootImage)



* [Get-CMWinPEOptionalComponentInfo](Get-CMWinPEOptionalComponentInfo)



* [Manage boot images with Configuration Manager](Manage boot images with Configuration Manager)





---


### Examples
#### Example 1: Rename a boot image
```PowerShell
Set-CMBootimage -Id "CM100004" -NewName "Custom boot image"
```

#### Example 2: Set descriptive properties
```PowerShell
Set-CMBootImage -Name "Custom boot image (x64)" -Version "Contoso v2.1" -Description "Managed by jqpublic"
```

#### Example 3: Set the keyboard layout
```PowerShell
Set-CMBootimage -Id "CM100004" -InputLocale "ru-ru"
```

#### Example 4: Add optional components
```PowerShell
$netfxOC = Get-CMWinPEOptionalComponentInfo -Architecture 'x64' -Name 'WinPE-NetFX' -LanguageId 1033
$pwshOC = Get-CMWinPEOptionalComponentInfo -Architecture 'x64' -Name 'WinPE-PowerShell' -LanguageId 1033
$OCs = @($netfxOC, $pwshOC)

Set-CMBootImage -Id 'XYZ00556' -AddOptionalComponent $OCs
```



---


### Parameters
#### **AddOptionalComponent**

Specify an array of optional component objects to add to the boot image. To get this object, use the Get-CMWinPEOptionalComponentInfo (Get-CMWinPEOptionalComponentInfo.md)cmdlet.


The following components are commonly used:


* Microsoft .NET (WinPE-NetFX): This component is a prerequisite for PowerShell. It's one of the larger optional components.


* Windows PowerShell (WinPE-PowerShell): This component requires .NET, and adds limited PowerShell support. If you run custom PowerShell scripts during the WinPE phase of your task sequence, add this component. There are other components that may be required for other PowerShell cmdlets.


* HTML (WinPE-HTA): If you run custom HTML applications during the WinPE phase of your task sequence, add this component.




For more information, see Manage boot images - optional components (/mem/configmgr/osd/get-started/manage-boot-images#optional-components).







|Type               |Required|Position|PipelineInput|Aliases              |
|-------------------|--------|--------|-------------|---------------------|
|`[IResultObject[]]`|false   |named   |False        |AddOptionalComponents|



#### **BackgroundBitmapPath**

Specify the network file path of a custom background image file to use in Windows PE.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CopyToPackageShareOnDistributionPoint**

Clients can always download a boot image from a distribution point. If you set this parameter to $true , the site makes it available via a named network share on distribution points. Use CustomPackageShareName to specify a custom share name.


When you enable this option, more space is required on distribution points. It applies to all distribution points to which you distribute this boot image.






|Type       |Required|Position|PipelineInput|Aliases                               |
|-----------|--------|--------|-------------|--------------------------------------|
|`[Boolean]`|false   |named   |False        |CopyToPackageShareOnDistributionPoints|



#### **CustomPackageShareName**

If you enable CopyToPackageShareOnDistributionPoint , you can use this parameter to customize the share name. The maximum length is 127 characters, and can't include any of the following characters: `" / [ ] : | < > + = ; , ? *`. You can specify a share name and a folder name, but then the maximum for each is 80 characters. For example, `ShareName\FolderName`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeployFromPxeDistributionPoint**

Set this parameter to $true to make this boot image available from a PXE-enabled distribution point. For more information, see Use PXE to deploy Windows over the network (/mem/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Description**

Specify an optional description of a boot image to help you identify it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisconnectUserFromDistributionPoint**

This option is deprecated. It sets the ForcedDisconnectEnabled property of the boot image.






|Type       |Required|Position|PipelineInput|Aliases                              |
|-----------|--------|--------|-------------|-------------------------------------|
|`[Boolean]`|false   |named   |False        |DisconnectUsersFromDistributionPoints|



#### **DisconnectUserFromDistributionPointMins**

This option is deprecated. It sets the ForcedDisconnectDelay property of the boot image.






|Type      |Required|Position|PipelineInput|Aliases                                     |
|----------|--------|--------|-------------|--------------------------------------------|
|`[UInt32]`|false   |named   |False        |DisconnectUsersFromDistributionPointsMinutes|



#### **DisconnectUserFromDistributionPointRetryCount**

This option is deprecated. It sets the ForcedDisconnectNumRetries property of the boot image.






|Type      |Required|Position|PipelineInput|Aliases                                     |
|----------|--------|--------|-------------|--------------------------------------------|
|`[UInt32]`|false   |named   |False        |DisconnectUsersFromDistributionPointsRetries|



#### **DistributionPointUpdateSchedule**

Use this parameter to update distribution points on a schedule. To get a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **EnableBinaryDeltaReplication**

Set this parameter to $true to enable binary differential replication (BDR). For more information, see Fundamental concepts for content management in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management#binary-differential-replication).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableCommandSupport**

In non-production, test environments only, you can set this parameter to $true to enable command support. When a device boots to this image, you can press F8 to open an administrative command prompt. This option is useful for troubleshooting while you're testing your deployment. Using this setting in a production deployment isn't advised because of security concerns.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePrestartCommand**

Set this parameter to $true to enable a prestart command. This command line runs before the task sequence starts.


Also configure the following parameters: IncludeFilesForPrestart , PrestartCommandLine , PrestartIncludeFilesDirectory .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify a boot image ID to configure. This value is a standard package ID, for example: `XYZ00002`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **IncludeFilesForPrestart**

If you enable EnablePrestartCommand , use this parameter if your prestart command requires other files to run. Then use the PrestartIncludeFilesDirectory parameter to specify the location of the files to include.


For example, if you want to run a batch script, use this option to include the script file.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputLocale**

Use this parameter to configure the default keyboard layout for a boot image. Specify the language tag . For example, to set the input locale to Russian (Russia), specify the string `ru-ru`. For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InputObject**

Specify a boot image object to configure. To get this object, use the Get-CMBootImage (Get-CMBootImage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a boot image to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specify a new name for the boot image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

Specify the network path of the Windows PE image that this boot image uses. You can't change the path for default boot images.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |ImagePath|



#### **PersistContentInCache**

If you don't want the content of this package to age out of the client cache to make room for other content, set this parameter to $true to persist it in the client cache.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **PrestageBehavior**

Specify the behavior when you enable a distribution point for prestaged content:


* `ManualCopy`: Manually copy the content in this package to the distribution point


* `DownloadDelta`: Download only content changes to the distribution point


* `OnDemand`: Automatically download content when packages are assigned to distribution points




For more information, see Use prestaged content (/mem/configmgr/core/servers/deploy/configure/deploy-and-manage-content#bkmk_prestage).




Valid Values:

* ManualCopy
* DownloadDelta
* OnDemand






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[PrestageBehavior]`|false   |named   |False        |



#### **PrestartCommandLine**

If you enable EnablePrestartCommand , use this parameter to specify the command line to run. The maximum length is 4096 characters.


If the command line requires files that aren't in Windows PE, use the IncludeFilesForPrestart and PrestartIncludeFilesDirectory parameters.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |CommandLine|



#### **PrestartIncludeFilesDirectory**

If you enable EnablePrestartCommand and IncludeFilesForPrestart , use this parameter to specify the network path of the files to include in the boot image.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Priority**

Specify the order in which the site sends the content to other sites and the distribution points in this site.


The site sends high priority content before packages with medium or low priority. Packages with equal priority are sent in the order in which they're created.



Valid Values:

* High
* Medium
* Low






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Priority]`|false   |named   |False        |



#### **Reload**

Applies to version 2006 and later. If the versions of the Windows ADK components in the boot image are out of date, add this parameter to reload the boot image with the current Windows PE version from the Windows ADK. For more information, see Update distribution points with the boot image (/mem/configmgr/osd/get-started/manage-boot-images#update-distribution-points-with-the-boot-image).






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |ReloadImage|



#### **RemoveOptionalComponent**

Specify an array of optional component objects to remove from the boot image. To get this object, use the Get-CMWinPEOptionalComponentInfo (Get-CMWinPEOptionalComponentInfo.md)cmdlet.


Don't remove the following components, which are required by Configuration Manager:


* Scripting (WinPE-Scripting)


* Startup (WinPE-SecureStartup)


* Network (WinPE-WDS-Tools)


* Scripting (WinPE-WMI)






|Type               |Required|Position|PipelineInput|Aliases                 |
|-------------------|--------|--------|-------------|------------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveOptionalComponents|



#### **ScratchSpace**

Configure the Windows PE scratch space, which is temporary storage (RAM drive) used by WinPE. For example, when an application is run within WinPE and needs to write temporary files, WinPE redirects the files to the scratch space in memory to simulate the presence of a hard disk. By default, this amount is 512 MB for devices with more than 1 GB of RAM, otherwise the default is 32 MB.



Valid Values:

* 32
* 64
* 128
* 256
* 512






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |



#### **SendToPreferredDistributionPoint**

If you want to enable on-demand content distribution to preferred distribution points, set this parameter to $true . When you enable this setting, if a client requests the content for the package and the content isn't available on any distribution points, then the management point distributes the content. For more information, see On-demand content distribution (/mem/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management#on-demand-content-distribution).






|Type       |Required|Position|PipelineInput|Aliases                          |
|-----------|--------|--------|-------------|---------------------------------|
|`[Boolean]`|false   |named   |False        |SendToPreferredDistributionPoints|



#### **Version**

Specify the version of the boot image. This value isn't the OS version, but a string that you manage.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Set-CMBootImage [-AddOptionalComponent <IResultObject[]>] [-BackgroundBitmapPath <String>] [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-DeployFromPxeDistributionPoint <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-EnableCommandSupport <Boolean>] [-EnablePrestartCommand <Boolean>] [-Force] [-ForceWildcardHandling] -Id <String> [-IncludeFilesForPrestart <Boolean>] [-InputLocale <String>] [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-PrestartCommandLine <String>] [-PrestartIncludeFilesDirectory <String>] [-Priority {High | Medium | Low}] [-Reload] [-RemoveOptionalComponent <IResultObject[]>] [-ScratchSpace {32 | 64 | 128 | 256 | 512}] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBootImage [-AddOptionalComponent <IResultObject[]>] [-BackgroundBitmapPath <String>] [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-DeployFromPxeDistributionPoint <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-EnableCommandSupport <Boolean>] [-EnablePrestartCommand <Boolean>] [-Force] [-ForceWildcardHandling] [-IncludeFilesForPrestart <Boolean>] [-InputLocale <String>] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-PrestartCommandLine <String>] [-PrestartIncludeFilesDirectory <String>] [-Priority {High | Medium | Low}] [-Reload] [-RemoveOptionalComponent <IResultObject[]>] [-ScratchSpace {32 | 64 | 128 | 256 | 512}] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMBootImage [-AddOptionalComponent <IResultObject[]>] [-BackgroundBitmapPath <String>] [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-DeployFromPxeDistributionPoint <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetryCount <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-EnableCommandSupport <Boolean>] [-EnablePrestartCommand <Boolean>] [-Force] [-ForceWildcardHandling] [-IncludeFilesForPrestart <Boolean>] [-InputLocale <String>] -Name <String> [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-PrestartCommandLine <String>] [-PrestartIncludeFilesDirectory <String>] [-Priority {High | Medium | Low}] [-Reload] [-RemoveOptionalComponent <IResultObject[]>] [-ScratchSpace {32 | 64 | 128 | 256 | 512}] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
