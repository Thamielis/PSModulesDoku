New-CMTaskSequence
------------------




### Synopsis
Create a task sequence.



---


### Description

Use this cmdlet to create a task sequence. You typically use a task sequence to deploy an OS to a client, but you can use them for various purposes. For more information, see Manage task sequences to automate tasks (/mem/configmgr/osd/deploy-use/manage-task-sequences-to-automate-tasks).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTaskSequence](Get-CMTaskSequence)



* [Set-CMTaskSequence](Set-CMTaskSequence)



* [Copy-CMTaskSequence](Copy-CMTaskSequence)



* [Import-CMTaskSequence](Import-CMTaskSequence)



* [Export-CMTaskSequence](Export-CMTaskSequence)



* [Remove-CMTaskSequence](Remove-CMTaskSequence)



* [New-CMTaskSequenceMedia](New-CMTaskSequenceMedia)



* [New-CMTaskSequenceDeployment](New-CMTaskSequenceDeployment)



* [About task sequence steps](About task sequence steps)





---


### Examples
#### Example 1: Create a custom task sequence
```PowerShell
$parameters = @{
  CustomTaskSequence = $true
  Name = "Custom"
  Description = "NewCustom parameter set"
  HighPerformance = $false
  BootImagePackageId = "XYZ00002"
}

New-CMTaskSequence @parameters
```

#### Example 2: Create a task sequence to install an OS image
```PowerShell
$clientProps = '/mp:mp01.contoso.com CCMDEBUGLOGGING="1" CCMLOGGINGENABLED="TRUE" CCMLOGLEVEL="0" CCMLOGMAXHISTORY="5" CCMLOGMAXSIZE="10000000" SMSCACHESIZE="15000" SMSMP=mp01.contoso.com'

$parameters = @{
  InstallOperatingSystemImage = $true
  Name = "Install OS image"
  Description = "NewInstallOSImage parameter set"
  BootImagePackageId = "XYZ00002"
  HighPerformance = $true
  CaptureNetworkSetting = $true
  CaptureUserSetting = $true
  SaveLocally = $true
  CaptureLocallyUsingLink = $true
  UserStateMigrationToolPackageId = "XYZ00001"
  CaptureWindowsSetting = $true
  ConfigureBitLocker = $true
  PartitionAndFormatTarget = $true
  ApplyAll = $false
  OperatingSystemImagePackageId = "XYZ001A0"
  OperatingSystemImageIndex = 1
  ProductKey = "6NMRW-2C8FM-D24W7-TQWMY-CWH2D"
  GeneratePassword = $true
  TimeZone = Get-TimeZone -Name "Eastern Standard Time"
  JoinDomain = "DomainType"
  DomainAccount = "contoso\jqpublic"
  DomainName = "contoso"
  DomainOrganizationUnit = "LDAP://OU=Workstations,OU=Devices,DC=na,DC=contoso,DC=com"
  DomainPassword = ConvertTo-SecureString -String "w%1H6EoxjQ&70^W" -AsPlainText -Force
  ClientPackagePackageId = "XYZ00003"
  InstallationProperty = $clientProps
  ApplicationName = "Admin Console"
  IgnoreInvalidApplication = $false
  SoftwareUpdateStyle = "All"
}

New-CMTaskSequence @parameters
```

#### Example 3: Create a task sequence to build and capture an OS
```PowerShell
$clientProps = '/mp:mp01.contoso.com CCMDEBUGLOGGING="1" CCMLOGGINGENABLED="TRUE" CCMLOGLEVEL="0" CCMLOGMAXHISTORY="5" CCMLOGMAXSIZE="10000000" SMSCACHESIZE="15000" SMSMP=mp01.contoso.com'

$parameters = @{
  BuildOperatingSystemImage = $true
  Name = "Build and capture"
  Description = "NewBuildOSImage parameter set"
  BootImagePackageId = "XYZ00002"
  HighPerformance = $true
  ApplyAll = $false
  OperatingSystemImagePackageId = "XYZ001A0"
  OperatingSystemImageIndex = 1
  ProductKey = "6NMRW-2C8FM-D24W7-TQWMY-CWH2D"
  GeneratePassword = $true
  TimeZone = Get-TimeZone -Name "Eastern Standard Time"
  JoinDomain = "WorkgroupType"
  WorkgroupName = "groupwork"
  ClientPackagePackageId = "XYZ00003"
  InstallationProperty = $clientProps
  ApplicationName = "Admin Console"
  IgnoreInvalidApplication = $true
  SoftwareUpdateStyle = "All"
  OperatingSystemFilePath = "\\server1\images\capture.wim"
  ImageDescription = "image description"
  ImageVersion = "image version 1"
  CreatedBy = "jqpublic"
  OperatingSystemFileAccount = "contoso\jqpublic" 
  OperatingSystemFileAccountPassword = ConvertTo-SecureString -String "w%1H6EoxjQ&70^W" -AsPlainText -Force
}

New-CMTaskSequence @parameters
```

#### Example 4: Create a task sequence to upgrade an OS
```PowerShell
New-CMTaskSequence -UpgradeOperatingSystem -Name "In-place upgrade" -UpgradePackageId "XYZ02EBA" -SoftwareUpdateStyle All
```



---


### Parameters
#### **ApplicationName**

Specify an array of application names to install during the task sequence. This parameter configures the Install Application (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_InstallApplication)task sequence step.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **ApplyAll**

In the build and capture scenario, the state of this parameter determines the following behaviors:


* `$true`: The task sequence doesn't format & partition the disk before it applies the OS image.


* `$false`: The task sequence includes the Format and Partition Disk (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_FormatandPartitionDisk)steps before it applies the OS image.






|Type       |Required|Position|PipelineInput|Aliases       |
|-----------|--------|--------|-------------|--------------|
|`[Boolean]`|false   |named   |False        |ApplyAllImages|



#### **BootImagePackageId**

Specify the ID of a boot image package to use with a task sequence that deploys an OS. This value is a standard package ID, for example `XYZ00005`.


This parameter configures the task sequence properties.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **BuildOperatingSystemImage**

Add this parameter to create a task sequence for the build and capture scenario. For more information, see Create a task sequence to capture an OS (/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-capture-an-operating-system).






|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[Switch]`|true    |named   |False        |BuildOperatingSystemImageOption|



#### **CaptureLocallyUsingLink**

When you enable the SaveLocally parameter to save user settings and files locally, set this parameter to $true to capture locally by using links instead of by copying files. The links that Configuration Manager uses to store the user state locally are referred to as hard-links.


The cmdlet ignores this parameter if SaveLocally is $false .


This parameter configures the Capture User State (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureUserState)step.






|Type       |Required|Position|PipelineInput|Aliases                 |
|-----------|--------|--------|-------------|------------------------|
|`[Boolean]`|false   |named   |False        |CaptureLocallyUsingLinks|



#### **CaptureNetworkSetting**

Set this parameter to $true to enable the task sequence to capture network settings. When you enable this option, the task sequence includes the Capture Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureNetworkSettings)step.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CaptureUserSetting**

Set this parameter to $true to enable the task sequence to capture user settings and files. When you enable this option, the task sequence includes the Capture User State (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureUserState)step. Also use the UserStateMigrationToolPackageId parameter.


Use SaveLocally and CaptureLocallyUsingLink to configure where the task sequence saves the user state.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CaptureWindowsSetting**

Set this parameter to $true to enable the task sequence to capture Windows settings. When you enable this option, the task sequence includes the Capture Windows Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureWindowsSettings)step.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientPackagePackageId**

Specify the ID of the client package to install when the task sequence runs. This value is a standard package ID, for example, `XYZ00003`. Site assignment and client configuration happen automatically. You can specify extra installation parameters with the InstallationProperty parameter.


This parameter configures the Setup Windows and ConfigMgr (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_SetupWindowsandConfigMgr)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ConfigureBitLocker**

Set this parameter to $true to configure the task sequence for use with BitLocker. When you enable this option, the task sequence includes the following steps:


* Disable BitLocker (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_DisableBitLocker)- Pre-provision BitLocker (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_PreProvisionBitLocker)- Enable BitLocker (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_EnableBitLocker)






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CreatedBy**

For the build and capture scenario, specify an optional string that's on the captured image file for who created it. The maximum length is 255 characters.


This parameter configures the Capture OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CustomTaskSequence**

Add this parameter to create a custom task sequence that contains no steps. For more information, see Create a custom task sequence (/mem/configmgr/osd/deploy-use/create-a-custom-task-sequence).


You can then use the 35 New-CMTSStep cmdlets to add steps to the custom task sequence. For more information, see About task sequence steps (/mem/configmgr/osd/understand/task-sequence-steps). Each section describes the task sequence steps, with links to the associated cmdlets.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[Switch]`|true    |named   |False        |CustomOption|



#### **Description**

Specify an optional description for the task sequence. The maximum length is 512 characters. This parameter configures the task sequence properties.






|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[String]`|false   |named   |False        |TaskSequenceDescription|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DomainAccount**

Specify an account that has the necessary permissions to join the computer to the domain. Use the following format: `Domain\User`. For more information, see ask sequence domain join account (/mem/configmgr/core/plan-design/hierarchy/accounts#task-sequence-domain-join-account).


Use the DomainName parameter to specify the domain name, and DomainPassword to specify this account's password.


This parameter configures the Apply Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DomainName**

Specify the name of a domain to have the computer join when it runs the task sequence. This parameter configures the Apply Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings)task sequence step.


Use the DomainAccount parameter to specify an account that has permissions to join this domain. You can also use the DomainOrganizationUnit parameter to specify an OU in which to create the computer account.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DomainOrganizationUnit**

Specify a domain organizational unit (OU) in which to create the computer account in the domain. The format of this value is the Lightweight Directory Access Protocol (LDAP) path, for example: `LDAP//OU=OSD staging,DC=contoso,DC=com`. Specify an OU in the domain that you specified in the DomainName parameter.


If an existing computer account is already in an OU, Active Directory doesn't allow you to change the OU and it ignores this setting.


This parameter configures the Apply Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DomainPassword**

Specify a secure string for the password of the account that you specified with the DomainAccount parameter.


This parameter configures the Apply Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings)task sequence step.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GeneratePassword**

Set this parameter to $true to randomly generate the local administrator password and disable the account. This configuration is recommended.


This parameter configures the Apply Windows Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyWindowsSettings)task sequence step.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **HighPerformance**

Set this parameter to $true to enable the task sequence option to run as high-performance power plan. This parameter configures the task sequence properties. For more information, see Performance improvements for power plans (/mem/configmgr/osd/deploy-use/manage-task-sequences-to-automate-tasks#bkmk_perf).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IgnoreInvalidApplication**

If you set this parameter to $true , the task sequence continues installing applications in the list if an application installation fails. Use this parameter with the ApplicationName parameter.


This parameter configures the Install Application (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_InstallApplication)task sequence step.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ImageDescription**

For the build and capture scenario, specify an optional string that describes the captured image file. The maximum length is 255 characters.


This parameter configures the Capture OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ImageVersion**

For the build and capture scenario, specify an optional string as the version of the captured image file. You define this value, it doesn't have to be the OS version. The maximum length is 32 characters.


This parameter configures the Capture OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstallationLicensingMode**

This setting only applies to legacy versions of Windows that are no longer supported. Starting in version 2010, the setting is no longer visible in the task sequence editor. Existing task sequences that still use this setting will continue to function the same.



Valid Values:

* NonSpecify
* PerSeat
* PerServer






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ServerLicensingMode]`|false   |named   |False        |



#### **InstallationProperty**

Specify any extra installation properties to use when the task sequence installs the Configuration Manager client. Site assignment and the default configuration are automatically specified by the task sequence. To enter multiple installation properties, separate them with a space. If a property contains spaces, surround it by quotation marks (`"`). For more information, see About client installation parameters and properties in Configuration Manager (/mem/configmgr/core/clients/deploy/about-client-installation-properties).


This list can't include SMSSITECODE .


This parameter configures the Setup Windows and ConfigMgr (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_SetupWindowsandConfigMgr)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InstallOperatingSystemImage**

Add this parameter to create a task sequence for the install OS image scenario. For more information, see Create a task sequence to install an OS (/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system).






|Type      |Required|Position|PipelineInput|Aliases                          |
|----------|--------|--------|-------------|---------------------------------|
|`[Switch]`|true    |named   |False        |InstallOperatingSystemImageOption|



#### **JoinDomain**

Use this parameter to configure the Apply Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings)task sequence step. The computer needs to either join a workgroup or a domain.


* `DomainType`: Join a domain. Also specify DomainName , DomainAccount , and DomainPassword . You can also use DomainOrganizationUnit .


* `WorkgroupType`: Join a workgroup. Also specify WorkgroupName . Use this value with the BuildOperatingSystemImage parameter. In the build and capture scenario, the task sequence always joins a workgroup before it captures the image.



Valid Values:

* DomainType
* WorkgroupType






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[JoinType]`|true    |named   |False        |



#### **LocalAdminPassword**

If you don't use the recommended option to GeneratePassword , use this parameter to specify a secure string as the local Administrator password.


This parameter configures the Apply Windows Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyWindowsSettings)task sequence step.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **MaximumServerConnection**

This setting only applies to legacy versions of Windows that are no longer supported. Starting in version 2010, the setting is no longer visible in the task sequence editor. Existing task sequences that still use this setting will continue to function the same.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Name**

Specify a name for the task sequence. The maximum length is 50 characters. This parameter configures the task sequence properties.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|true    |named   |False        |TaskSequenceName|



#### **OperatingSystemFileAccount**

For the build and capture scenario, specify the name of a domain account that has permissions to the network share that you specify in the OperatingSystemFilePath parameter. Use OperatingSystemFileAccountPassword to set the account password.


This parameter configures the Capture OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|Aliases                          |
|----------|--------|--------|-------------|---------------------------------|
|`[String]`|true    |named   |False        |CaptureOperatingSystemFileAccount|



#### **OperatingSystemFileAccountPassword**

For the build and capture scenario, specify a secure string for the password of the OperatingSystemFileAccount .


This parameter configures the Capture OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureOperatingSystemImage)task sequence step.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **OperatingSystemFilePath**

For the build and capture scenario, specify the file path to the network location that Configuration Manager uses to store the captured OS image. The path includes the file name with a `.wim` file extension. Use OperatingSystemFileAccount and OperatingSystemFileAccountPassword to specify an account that has access to this location.


This parameter configures the Capture OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|true    |named   |False        |CaptureOperatingSystemFilePath|



#### **OperatingSystemImageIndex**

Specify the index of the OS image to install for the Apply OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|true    |named   |False        |



#### **OperatingSystemImagePackageId**

Specify the ID of the OS image package to install. Use OperatingSystemImageIndex to specify the image index. This value is a standard package ID, for example `XYZ00050`.


This parameter configures the Apply OS Image (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PartitionAndFormatTarget**

Set this parameter to $true for the task sequence to partition and format the target computer before it installs the OS.


This parameter configures the Format and Partition Disk (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_FormatandPartitionDisk)task sequence step.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ProductKey**

Specify the Windows product key for the OS installation.


This parameter configures the Apply Windows Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyWindowsSettings)task sequence step.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|false   |named   |False        |InstallationProductKey|



#### **SaveLocally**

If you enable the CaptureUserSetting parameter, then use this parameter to determine where the task sequence saves the captured user state:


* `$true`: The task sequence configures the local state location, and captures locally by using links instead of by copying files. This value configures the Capture User State (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureUserState)step.


* Use the CaptureLocallyUsingLink parameter to configure the use of hard-links.


* `$false`: The task sequence includes steps to use a state migration point. It configures the following steps:


* Request State Store (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RequestStateStore)- Capture User State (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureUserState)- Release State Store (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ReleaseStateStore)






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SoftwareUpdateStyle**

Specify whether to install software updates during the task sequence. The values determine the type of software update deployment:


* `All`: Available for installation, all software updates


* `Mandatory`: Required for installation, mandatory software updates only


* `NoInstall`: Don't install any software updates




This parameter configures the Install Software Updates (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_InstallSoftwareUpdates)task sequence step.




Valid Values:

* All
* Mandatory
* NoInstall






|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[SoftwareUpdateStyleType]`|false   |named   |False        |



#### **TimeZone**

Specify the default time zone for this installation of Windows. To get a time zone object, use the built-in Get-TimeZone (/powershell/module/microsoft.powershell.management/get-timezone)cmdlet.


This parameter configures the Apply Windows Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyWindowsSettings)task sequence step.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeZoneInfo]`|false   |named   |False        |



#### **UpgradeOperatingSystem**

Add this parameter to create a task sequence for the OS upgrade scenario. For more information, see Create a task sequence to upgrade an OS (/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system).






|Type      |Required|Position|PipelineInput|Aliases                     |
|----------|--------|--------|-------------|----------------------------|
|`[Switch]`|true    |named   |False        |UpgradeOperatingSystemOption|



#### **UpgradePackageId**

Specify the ID of the OS upgrade package to use. This value is a standard package ID, for example `XYZ00052`.


This parameter configures the Upgrade OS (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyOperatingSystemImage)task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserStateMigrationToolPackageId**

When you set CaptureUserSetting to $true , use this parameter to specify the ID of the User State Migration Tool (USMT) package. This value is a standard package ID, for example `XYZ00012`.


This parameter configures the Capture User State (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureUserState) and [Restore User State](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RestoreUserState)steps.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **WorkgroupName**

If you set the JoinDomain parameter to `WorkgroupType`, use this parameter to specify the workgroup name. This parameter configures the Apply Network Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings)task sequence step.






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
None





---


### Outputs
* IResultObject#SMS_TaskSequencePackage






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequencePackage server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequencepackage-server-wmi-class).

On the Apply Windows Settings (/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyWindowsSettings)task sequence step, this cmdlet sets the User name value to the user that runs the cmdlet, and the Organization name to the computer name where the cmdlet runs.

You can't configure all task sequence and step settings with this cmdlet. To configure other settings, use Set-CMTaskSequence (Set-CMTaskSequence.md) and the **Set-CMTSStep** cmdlets, for example, [Set-CMTSStepApplyOperatingSystem](Set-CMTSStepApplyOperatingSystem.md).



---


### Syntax
```PowerShell
New-CMTaskSequence [-ApplicationName <String[]>] [-ApplyAll <Boolean>] -BootImagePackageId <String> -BuildOperatingSystemImage [-ClientPackagePackageId <String>] [-CreatedBy <String>] [-Description <String>] [-DisableWildcardHandling] [-DomainAccount <String>] [-DomainName <String>] [-DomainOrganizationUnit <String>] [-DomainPassword <SecureString>] [-ForceWildcardHandling] [-GeneratePassword <Boolean>] [-HighPerformance <Boolean>] [-IgnoreInvalidApplication <Boolean>] [-ImageDescription <String>] [-ImageVersion <String>] [-InstallationLicensingMode {NonSpecify | PerSeat | PerServer}] [-InstallationProperty <String>] -JoinDomain {DomainType | WorkgroupType} [-LocalAdminPassword <SecureString>] [-MaximumServerConnection <Int32>] -Name <String> -OperatingSystemFileAccount <String> [-OperatingSystemFileAccountPassword <SecureString>] -OperatingSystemFilePath <String> -OperatingSystemImageIndex <UInt32> -OperatingSystemImagePackageId <String> [-ProductKey <String>] [-SoftwareUpdateStyle {All | Mandatory | NoInstall}] [-TimeZone <TimeZoneInfo>] [-WorkgroupName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequence [-ApplicationName <String[]>] [-ApplyAll <Boolean>] -BootImagePackageId <String> [-CaptureLocallyUsingLink <Boolean>] [-CaptureNetworkSetting <Boolean>] [-CaptureUserSetting <Boolean>] [-CaptureWindowsSetting <Boolean>] [-ClientPackagePackageId <String>] [-ConfigureBitLocker <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-DomainAccount <String>] [-DomainName <String>] [-DomainOrganizationUnit <String>] [-DomainPassword <SecureString>] [-ForceWildcardHandling] [-GeneratePassword <Boolean>] [-HighPerformance <Boolean>] [-IgnoreInvalidApplication <Boolean>] [-InstallationLicensingMode {NonSpecify | PerSeat | PerServer}] [-InstallationProperty <String>] -InstallOperatingSystemImage -JoinDomain {DomainType | WorkgroupType} [-LocalAdminPassword <SecureString>] -Name <String> -OperatingSystemImageIndex <UInt32> -OperatingSystemImagePackageId <String> [-PartitionAndFormatTarget <Boolean>] [-ProductKey <String>] [-SaveLocally <Boolean>] [-SoftwareUpdateStyle {All | Mandatory | NoInstall}] [-TimeZone <TimeZoneInfo>] [-UserStateMigrationToolPackageId <String>] [-WorkgroupName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequence [-ApplicationName <String[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-HighPerformance <Boolean>] [-IgnoreInvalidApplication <Boolean>] -Name <String> [-ProductKey <String>] [-SoftwareUpdateStyle {All | Mandatory | NoInstall}] -UpgradeOperatingSystem -UpgradePackageId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTaskSequence [-BootImagePackageId <String>] -CustomTaskSequence [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-HighPerformance <Boolean>] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
