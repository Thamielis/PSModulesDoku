Set-CMPackage
-------------




### Synopsis
Modify a package.



---


### Description

Use this cmdlet to change the settings of a package. For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMPackage](Export-CMPackage)



* [Get-CMPackage](Get-CMPackage)



* [Import-CMPackage](Import-CMPackage)



* [New-CMPackage](New-CMPackage)



* [Remove-CMPackage](Remove-CMPackage)



* [Packages and programs in Configuration Manager](Packages and programs in Configuration Manager)





---


### Examples
#### Example 1: Rename a package and add a description
```PowerShell
Set-CMPackage -Id "ST120001" -NewName "ScriptsPackage02" -Description "This package deploys scripts that run on a recurring schedule."
```

#### Example 2: Change the package source path
```PowerShell
$pkg = Get-CMPackage -Id "ST120001"
Set-CMPackage -InputObject $pkg -Path "\\sources\cmpkg$\newpkg01"
```



---


### Parameters
#### **CopyToPackageShareOnDistributionPoint**

Clients can always download a package from a distribution point. If you set this parameter to $true , the site makes it available via a named network share on distribution points. Use CustomPackageShareName to specify a custom share name.


When you enable this option, more space is required on distribution points. It applies to all distribution points to which you distribute this package.






|Type       |Required|Position|PipelineInput|Aliases                                                |
|-----------|--------|--------|-------------|-------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |ShareContent<br/>CopyToPackageShareOnDistributionPoints|



#### **CustomPackageShareName**

If you enable CopyToPackageShareOnDistributionPoint , you can use this parameter to customize the share name. The maximum length is 127 characters, and can't include any of the following characters: `" / [ ] : | < > + = ; , ? *`. You can specify a share name and a folder name, but then the maximum for each is 80 characters. For example, `ShareName\FolderName`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|false   |named   |False        |ShareName|



#### **Description**

Specify an optional description of the package to help you identify it. You can use a maximum of 128 characters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisconnectUserFromDistributionPoint**

This option is deprecated. It sets the ForcedDisconnectEnabled property of the driver package.






|Type       |Required|Position|PipelineInput|Aliases                                                         |
|-----------|--------|--------|-------------|----------------------------------------------------------------|
|`[Boolean]`|false   |named   |False        |ForceDisconnectEnabled<br/>DisconnectUsersFromDistributionPoints|



#### **DisconnectUserFromDistributionPointMins**

This option is deprecated. It sets the ForcedDisconnectDelay property of the driver package.






|Type      |Required|Position|PipelineInput|Aliases                                                                                                                                                            |
|----------|--------|--------|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|`[UInt32]`|false   |named   |False        |ForcedDisconnectDelay<br/>DisconnectUsersFromDistributionPointsMinutes<br/>DisconnectUserFromDistributionPointsMins<br/>DisconnectUserFromDistributionPointsMinutes|



#### **DisconnectUserFromDistributionPointRetry**

This option is deprecated. It sets the ForcedDisconnectNumRetries property of the driver package.






|Type      |Required|Position|PipelineInput|Aliases                                                                   |
|----------|--------|--------|-------------|--------------------------------------------------------------------------|
|`[UInt32]`|false   |named   |False        |ForceDisconnectNumRetries<br/>DisconnectUsersFromDistributionPointsRetries|



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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of a package to configure. This value is a standard package ID, for example: `XYZ00020`.






|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |PackageId|



#### **InputObject**

Specify a package object to configure. To get this object, use the Get-CMPackage (Get-CMPackage.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Language**

Specify a language string for the package. You can use a maximum of 32 characters in a format that you choose to use to identify the language version. To identify a package, Configuration Manager uses the Language , Manufacturer , Name , and Version parameters. For example, you can have an English version and a German version of the same package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Manufacturer**

Specify the manufacturer name for the software. You can use a maximum of 32 characters. To identify a package, Configuration Manager uses the Language , Manufacturer , Name , and Version parameters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MifFileName**

Specify the name of the Management Information Format (MIF) file that contains the package status. The file name extension must be `.mif`. Use a status MIF file to generate detailed status reporting. To generate a status MIF file, your application must call the InstallStatusMIF function. For more information, see Status MIF Functions (/mem/configmgr/develop/reference/core/servers/manage/status-mif-functions).


If you set this parameter, when the client runs the deployment, the Configuration Manager client looks in the `%TEMP%` directory or the `%windir%` directory for the installation status MIF file that you specify. The installation status indicates whether the program successfully ran.


If the client doesn't find the file, it searches for all MIF files in those directories. It makes a case-insensitive comparison of the values that you specify for MifName , MifPublisher , and MifVersion to the values that the MIF file specifies. If the client finds a match, it uses the status that the MIF file specifies as the installation status for the program. If it can't find a match, or if you don't specify MifFileName , the client uses the program exit code to set the installation status for the program. An exit code of zero indicates that the program successfully ran. Any other values indicate application-specific error codes.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MifName**

Specify the name of the package for MIF matching, up to 50 characters. For more information, see the MifFileName parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MifPublisher**

Specify the software publisher of the package for MIF matching, up to 32 characters. For more information, see the MifFileName parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MifVersion**

Specify the version number of the package for MIF matching, up to 32 characters. For more information, see the MifFileName parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MulticastAllow**

Set this parameter to $true to allow this package to be transferred via multicast. For more information, see Use multicast to deploy Windows over the network with Configuration Manager (/mem/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MulticastEncrypt**

If you enable MulticastAllow , set this parameter to $true to encrypt multicast packages.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MulticastTransferOnly**

If you enable MulticastAllow , set this parameter to $true to only transfer this driver package via multicast.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify a package name. You can use a maximum of 250 characters. To identify a package, Configuration Manager uses the Language , Manufacturer , Name , and Version parameters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Use this parameter to rename a package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Path**

If the package contains source files, specify the location of the files. You can specify either a full local path on the site server, or a network path. Make sure that this location contains all the files and subdirectories that the program needs to run, including any scripts.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|false   |named   |False        |PackageSourcePath|



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



#### **Priority**

Specify the order in which the site sends the content to other sites and the distribution points in this site.


The site sends high priority content before packages with normal or low priority. Packages with equal priority are sent in the order in which they're created.



Valid Values:

* High
* Normal
* Low






|Type          |Required|Position|PipelineInput|Aliases             |
|--------------|--------|--------|-------------|--------------------|
|`[Priorities]`|false   |named   |False        |DistributionPriority|



#### **SendToPreferredDistributionPoint**

If you want to enable on-demand content distribution to preferred distribution points, set this parameter to $true . When you enable this setting, if a client requests the content for the package and the content isn't available on any distribution points, then the management point distributes the content. For more information, see On-demand content distribution (/mem/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management#on-demand-content-distribution).






|Type       |Required|Position|PipelineInput|Aliases                          |
|-----------|--------|--------|-------------|---------------------------------|
|`[Boolean]`|false   |named   |False        |SendToPreferredDistributionPoints|



#### **Version**

Specify a version number for the software. The maximum length of this string is 32 characters. To identify a package, Configuration Manager uses the Language , Manufacturer , Name , and Version parameters.






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
Set-CMPackage [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetry <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] -Id <String> [-Language <String>] [-Manufacturer <String>] [-MifFileName <String>] [-MifName <String>] [-MifPublisher <String>] [-MifVersion <String>] [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Normal | Low}] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMPackage [-InputObject] <IResultObject> [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetry <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] [-Language <String>] [-Manufacturer <String>] [-MifFileName <String>] [-MifName <String>] [-MifPublisher <String>] [-MifVersion <String>] [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Normal | Low}] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMPackage [-CopyToPackageShareOnDistributionPoint <Boolean>] [-CustomPackageShareName <String>] [-Description <String>] [-DisableWildcardHandling] [-DisconnectUserFromDistributionPoint <Boolean>] [-DisconnectUserFromDistributionPointMins <UInt32>] [-DisconnectUserFromDistributionPointRetry <UInt32>] [-DistributionPointUpdateSchedule <IResultObject>] [-EnableBinaryDeltaReplication <Boolean>] [-ForceWildcardHandling] [-Language <String>] [-Manufacturer <String>] [-MifFileName <String>] [-MifName <String>] [-MifPublisher <String>] [-MifVersion <String>] [-MulticastAllow <Boolean>] [-MulticastEncrypt <Boolean>] [-MulticastTransferOnly <Boolean>] -Name <String> [-NewName <String>] [-PassThru] [-Path <String>] [-PersistContentInCache <Boolean>] [-PrestageBehavior {ManualCopy | DownloadDelta | OnDemand}] [-Priority {High | Normal | Low}] [-SendToPreferredDistributionPoint <Boolean>] [-Version <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
