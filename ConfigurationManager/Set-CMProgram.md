Set-CMProgram
-------------




### Synopsis
Modify a program of a package.



---


### Description

Use this cmdlet to modify a program of a package. Programs identify the actions that occur when the client receives the client package. You can associate multiple programs with the same package. For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMProgram](Disable-CMProgram)



* [Enable-CMProgram](Enable-CMProgram)



* [Get-CMProgram](Get-CMProgram)



* [New-CMProgram](New-CMProgram)



* [Remove-CMProgram](Remove-CMProgram)



* [Packages and programs in Configuration Manager](Packages and programs in Configuration Manager)





---


### Examples
#### Example 1: Modify a standard program
```PowerShell
Set-CMProgram -Name "Test" -StandardProgramName SPM -Comment "Standard Upgrades" -CommandLine "RunThisNow" -RunType Maximized -AfterRunningType ProgramControlsRestart -Category "Laptops" -DiskSpaceRequirement 50 -DiskSpaceUnit MB -Duration 150 -Requirement 4 -Reconnect $False -SuppressProgramNotifications $False -DisableProgram $True -EnableTaskSequence $True -DisableMomAlertOnRun $True -GenerateMomAlertOnFail $True
```

#### Example 2: Modify a device program
```PowerShell
Set-CMProgram -Name "Test" -DeviceProgramName DPM -Comment "Upgrades for December" -CommandLine "RunMe" -WorkingDirectory "\TempWork" -CommandLineFolder "C:\Windows" -DiskSpaceRequirement 30 -DiskSpaceUnit MB -DownloadProgramType AsSoonAsPossible -Requirement "All previous device updates"
```

#### Example 3: Add a supported OS platform
```PowerShell
$ProgramName = 'Script'
$PackageID = 'XYZ0000D'
$Platform = 'All Windows 10 (64-bit) Client'
$OS = Get-CMSupportedPlatform -Name $Platform -Fast

Set-CMProgram -PackageID $PackageID -ProgramName $ProgramName -AddSupportedOperatingSystemPlatform $OS -StandardProgram
```



---


### Parameters
#### **AddSupportedOperatingSystemPlatform**

Specify one or more supported OS platforms to add for the program. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                             |
|-------------------|--------|--------|-------------|------------------------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSupportedOperatingSystemPlatforms|



#### **AfterRunningType**

Specify the action that occurs after the program completes successfully.



Valid Values:

* NoActionRequired
* ConfigurationManagerRestartsComputer
* ProgramControlsRestart
* ConfigurationManagerLogsUserOff






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[AfterRunningType]`|false   |named   |False        |



#### **Category**

Specify the category under which the program is displayed on the client computer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CommandLine**

Specify the command line for the program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CommandLineFolder**

Specify the folder that contains the executable program. This folder can be an absolute path on the client, or a path relative to the distribution folder that contains the package.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Comment**

Specify optional text about the program, such as a description. On client computers, this text displays with the program in Software Center.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeviceProgram**

Add this parameter to configure this program as a device program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableMomAlertOnRun**

Indicates whether the computer running the program is in maintenance mode for the duration of the program. When in maintenance mode, System Center Operations Manager disables alerts while the program runs.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableProgram**

Set this parameter to `$true` to temporarily disable all deployments that contain this program. You can also use the Disable-CMProgram (Disable-CMProgram.md)cmdlet.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DiskSpaceRequirement**

Specify the amount of disk space that the software program requires to run on the computer. The value must be greater than or equal to zero. If you specify a value, use the DiskSpaceUnit parameter to specify units for the value.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DiskSpaceUnit**

Specify an accepted unit for the DiskSpaceRequirement parameter.



Valid Values:

* KB
* MB
* GB






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[DiskSpaceUnitType]`|false   |named   |False        |



#### **DownloadProgramType**

Specify when the program is to run.



Valid Values:

* AsSoonAsPossible
* OnlyOverFastNetwork
* OnlyWhenTheDeviceIsDocked






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[DownloadProgramType]`|false   |named   |False        |



#### **DriveLetter**

If you use the DriveMode parameter, specify a drive letter for the location.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DriveMode**

Indicates whether the program requires a specific drive letter, specified in the DriveLetter parameter.


* `RunWithUnc`: Run the program from the UNC path. This value is the default. Starting in version 2010, this value was renamed from `RenameWithUnc`.


* `RequiresDriveLetter`: The program uses any available drive letter.


* `RequiresSpecificDriveLetter`: The program only runs if the drive isn't already in use.



Valid Values:

* RunWithUnc
* RequiresDriveLetter
* RequiresSpecificDriveLetter






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[DriveModeType]`|false   |named   |False        |



#### **Duration**

Specifies the maximum amount of time that you expect the program to run. The default value is 120 minutes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **EnableTaskSequence**

Indicates whether this program can be installed from the Install Package task sequence step.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateMomAlertOnFail**

Indicates whether Configuration Manager generates an application log event entry if the program fails.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specify a program object to configure. To get this object, use the Get-CMProgram (Get-CMProgram.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases                               |
|-----------------|--------|--------|--------------|--------------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ProgramPackage<br/>Package<br/>Program|



#### **PackageId**

Specify a package ID with the program to configure.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **PackageName**

Specify a package name with the program to configure.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ProgramAssignedType**

Specify whether the program runs once on the computer, or once for every user who signs in to the computer. The default value is `RunOnceForTheComputer`. The program is only assigned to users when the ProgramRunType parameter is set to `OnlyWhenUserIsLoggedOn`.



Valid Values:

* RunOnceForTheComputer
* RunOnceForEveryUserWhoLogsOn






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[ProgramAssignedType]`|false   |named   |False        |



#### **ProgramName**

Specify the name of the program to configure.






|Type      |Required|Position|PipelineInput|Aliases                                  |
|----------|--------|--------|-------------|-----------------------------------------|
|`[String]`|true    |named   |False        |StandardProgramName<br/>DeviceProgramName|



#### **ProgramRunType**

Specify the logon conditions that are necessary for the program to run. The default value is `OnlyWhenUserIsLoggedOn`.



Valid Values:

* OnlyWhenUserIsLoggedOn
* WhetherOrNotUserIsLoggedOn
* OnlyWhenNoUserIsLoggedOn






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ProgramRunType]`|false   |named   |False        |



#### **Reconnect**

Indicates whether the client computer reconnects to the distribution point when the user signs in.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RemoveSupportedOperatingSystemPlatform**

Specify one or more supported OS platforms to remove for the program. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                                |
|-------------------|--------|--------|-------------|---------------------------------------|
|`[IResultObject[]]`|false   |named   |False        |RemoveSupportedOperatingSystemPlatforms|



#### **Requirement**

Specify any additional requirements for standard or device programs.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RunMode**

Specify the credentials the client computer requires to run the program.



Valid Values:

* RunWithUserRights
* RunWithAdministrativeRights






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[RunModeType]`|false   |named   |False        |



#### **RunOnAnyPlatform**

Add this parameter to clear all supported OS platforms from this program.






|Type      |Required|Position|PipelineInput|Aliases                               |
|----------|--------|--------|-------------|--------------------------------------|
|`[Switch]`|false   |named   |False        |ClearSupportedOperatingSystemPlatforms|



#### **RunType**

Specify the mode in which the program runs on the client computer. The default value is `Normal`.



Valid Values:

* Normal
* Minimized
* Maximized
* Hidden






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[RunType]`|false   |named   |False        |



#### **StandardProgram**

Indicates that the program type in the deployment package is standard program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SuppressProgramNotification**

Set this parameter to `$true` to suppress program notifications.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **UserInteraction**

Indicates whether to allow users to interact with the program.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WorkingDirectory**

Specify a working directory for the program.






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
Set-CMProgram [-AddSupportedOperatingSystemPlatform <IResultObject[]>] [-AfterRunningType {NoActionRequired | ConfigurationManagerRestartsComputer | ProgramControlsRestart | ConfigurationManagerLogsUserOff}] [-Category <String>] [-CommandLine <String>] [-Comment <String>] [-DisableMomAlertOnRun <Boolean>] [-DisableProgram <Boolean>] [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DriveLetter <String>] [-DriveMode {RunWithUnc | RequiresDriveLetter | RequiresSpecificDriveLetter}] [-Duration <Int32>] [-EnableTaskSequence <Boolean>] [-ForceWildcardHandling] [-GenerateMomAlertOnFail <Boolean>] -InputObject <IResultObject> [-PassThru] [-ProgramAssignedType {RunOnceForTheComputer | RunOnceForEveryUserWhoLogsOn}] [-ProgramRunType {OnlyWhenUserIsLoggedOn | WhetherOrNotUserIsLoggedOn | OnlyWhenNoUserIsLoggedOn}] [-Reconnect <Boolean>] [-RemoveSupportedOperatingSystemPlatform <IResultObject[]>] [-Requirement <String>] [-RunMode {RunWithUserRights | RunWithAdministrativeRights}] [-RunOnAnyPlatform] [-RunType {Normal | Minimized | Maximized | Hidden}] -StandardProgram [-SuppressProgramNotification <Boolean>] [-UserInteraction <Boolean>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMProgram [-AddSupportedOperatingSystemPlatform <IResultObject[]>] [-AfterRunningType {NoActionRequired | ConfigurationManagerRestartsComputer | ProgramControlsRestart | ConfigurationManagerLogsUserOff}] [-Category <String>] [-CommandLine <String>] [-Comment <String>] [-DisableMomAlertOnRun <Boolean>] [-DisableProgram <Boolean>] [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DriveLetter <String>] [-DriveMode {RunWithUnc | RequiresDriveLetter | RequiresSpecificDriveLetter}] [-Duration <Int32>] [-EnableTaskSequence <Boolean>] [-ForceWildcardHandling] [-GenerateMomAlertOnFail <Boolean>] -PackageName <String> [-PassThru] [-ProgramAssignedType {RunOnceForTheComputer | RunOnceForEveryUserWhoLogsOn}] -ProgramName <String> [-ProgramRunType {OnlyWhenUserIsLoggedOn | WhetherOrNotUserIsLoggedOn | OnlyWhenNoUserIsLoggedOn}] [-Reconnect <Boolean>] [-RemoveSupportedOperatingSystemPlatform <IResultObject[]>] [-Requirement <String>] [-RunMode {RunWithUserRights | RunWithAdministrativeRights}] [-RunOnAnyPlatform] [-RunType {Normal | Minimized | Maximized | Hidden}] -StandardProgram [-SuppressProgramNotification <Boolean>] [-UserInteraction <Boolean>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMProgram [-AddSupportedOperatingSystemPlatform <IResultObject[]>] [-AfterRunningType {NoActionRequired | ConfigurationManagerRestartsComputer | ProgramControlsRestart | ConfigurationManagerLogsUserOff}] [-Category <String>] [-CommandLine <String>] [-Comment <String>] [-DisableMomAlertOnRun <Boolean>] [-DisableProgram <Boolean>] [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DriveLetter <String>] [-DriveMode {RunWithUnc | RequiresDriveLetter | RequiresSpecificDriveLetter}] [-Duration <Int32>] [-EnableTaskSequence <Boolean>] [-ForceWildcardHandling] [-GenerateMomAlertOnFail <Boolean>] -PackageId <String> [-PassThru] [-ProgramAssignedType {RunOnceForTheComputer | RunOnceForEveryUserWhoLogsOn}] -ProgramName <String> [-ProgramRunType {OnlyWhenUserIsLoggedOn | WhetherOrNotUserIsLoggedOn | OnlyWhenNoUserIsLoggedOn}] [-Reconnect <Boolean>] [-RemoveSupportedOperatingSystemPlatform <IResultObject[]>] [-Requirement <String>] [-RunMode {RunWithUserRights | RunWithAdministrativeRights}] [-RunOnAnyPlatform] [-RunType {Normal | Minimized | Maximized | Hidden}] -StandardProgram [-SuppressProgramNotification <Boolean>] [-UserInteraction <Boolean>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMProgram [-AddSupportedOperatingSystemPlatform <IResultObject[]>] [-AfterRunningType {NoActionRequired | ConfigurationManagerRestartsComputer | ProgramControlsRestart | ConfigurationManagerLogsUserOff}] [-Category <String>] [-CommandLine <String>] [-Comment <String>] [-DisableMomAlertOnRun <Boolean>] [-DisableProgram <Boolean>] [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DriveLetter <String>] [-DriveMode {RunWithUnc | RequiresDriveLetter | RequiresSpecificDriveLetter}] [-Duration <Int32>] [-EnableTaskSequence <Boolean>] [-ForceWildcardHandling] [-GenerateMomAlertOnFail <Boolean>] -InputObject <IResultObject> [-PassThru] [-ProgramAssignedType {RunOnceForTheComputer | RunOnceForEveryUserWhoLogsOn}] -ProgramName <String> [-ProgramRunType {OnlyWhenUserIsLoggedOn | WhetherOrNotUserIsLoggedOn | OnlyWhenNoUserIsLoggedOn}] [-Reconnect <Boolean>] [-RemoveSupportedOperatingSystemPlatform <IResultObject[]>] [-Requirement <String>] [-RunMode {RunWithUserRights | RunWithAdministrativeRights}] [-RunOnAnyPlatform] [-RunType {Normal | Minimized | Maximized | Hidden}] -StandardProgram [-SuppressProgramNotification <Boolean>] [-UserInteraction <Boolean>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMProgram [-CommandLine <String>] [-CommandLineFolder <String>] [-Comment <String>] -DeviceProgram [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DownloadProgramType {AsSoonAsPossible | OnlyOverFastNetwork | OnlyWhenTheDeviceIsDocked}] [-ForceWildcardHandling] -PackageName <String> [-PassThru] -ProgramName <String> [-Requirement <String>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMProgram [-CommandLine <String>] [-CommandLineFolder <String>] [-Comment <String>] -DeviceProgram [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DownloadProgramType {AsSoonAsPossible | OnlyOverFastNetwork | OnlyWhenTheDeviceIsDocked}] [-ForceWildcardHandling] -PackageId <String> [-PassThru] -ProgramName <String> [-Requirement <String>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMProgram [-CommandLine <String>] [-CommandLineFolder <String>] [-Comment <String>] -DeviceProgram [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DownloadProgramType {AsSoonAsPossible | OnlyOverFastNetwork | OnlyWhenTheDeviceIsDocked}] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] -ProgramName <String> [-Requirement <String>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMProgram [-CommandLine <String>] [-CommandLineFolder <String>] [-Comment <String>] -DeviceProgram [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DownloadProgramType {AsSoonAsPossible | OnlyOverFastNetwork | OnlyWhenTheDeviceIsDocked}] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Requirement <String>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
