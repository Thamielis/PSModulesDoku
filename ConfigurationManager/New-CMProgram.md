New-CMProgram
-------------




### Synopsis
Create a new program for a package.



---


### Description

Use this cmdlet to create a program for a package. Programs are commands that are associated with a Configuration Manager package. They identify the actions that occur when the client receives the client package. You can associate multiple programs with the same package. For more information, see Packages and programs in Configuration Manager (/mem/configmgr/apps/deploy-use/packages-and-programs).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMProgram](Disable-CMProgram)



* [Enable-CMProgram](Enable-CMProgram)



* [Get-CMProgram](Get-CMProgram)



* [Remove-CMProgram](Remove-CMProgram)



* [Set-CMProgram](Set-CMProgram)



* [Packages and programs in Configuration Manager](Packages and programs in Configuration Manager)





---


### Examples
#### Example 1: Create a program
```PowerShell
$parameters = @{
  PackageName = "User State Migration Tool for Windows"
  StandardProgramName = "Scan x64"
  CommandLine = "amd64\scanstate.exe \\gold\sources$\userdata /i:miguser.xml /i:migapp.xml /o"
  RunType = "Normal"
  ProgramRunType = "OnlyWhenNoUserIsLoggedOn"
  DiskSpaceRequirement = 200
  DiskSpaceUnit = "MB"
  Duration = 100
  DriveMode = "RunWithUnc"
}
New-CMProgram @parameters
```



---


### Parameters
#### **AddSupportedOperatingSystemPlatform**

Specify one or more supported OS platforms to add for the program. To get this object, use the Get-CMSupportedPlatform (Get-CMSupportedPlatform.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases                             |
|-------------------|--------|--------|-------------|------------------------------------|
|`[IResultObject[]]`|false   |named   |False        |AddSupportedOperatingSystemPlatforms|



#### **CommandLine**

Specify the command line for the program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **DeviceProgramName**

Specifies a device program name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DiskSpaceRequirement**

Specify the amount of disk space that the software program requires to run on the computer. The value must be greater than or equal to zero. If you specify a value, use the DiskSpaceUnit parameter to specify units for the value.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |DiskSpaceReq|



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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PackageId**

Specify the ID of the package for this program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PackageName**

Specify a package name for this program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ProgramRunType**

Specifies the logon conditions that are necessary for the program to run.


The default setting is `OnlyWhenUserIsLoggedOn`.



Valid Values:

* OnlyWhenUserIsLoggedOn
* WhetherOrNotUserIsLoggedOn
* OnlyWhenNoUserIsLoggedOn






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ProgramRunType]`|false   |named   |False        |



#### **Reconnect**

Indicates whether the client computer reconnects to the distribution point when the user signs in to Windows.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Requirement**

Specifies additional requirements for standard or device programs.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |Requirements|



#### **RunMode**

Specify the credentials that the program requires to run on the client computer.



Valid Values:

* RunWithUserRights
* RunWithAdministrativeRights






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[RunModeType]`|false   |named   |False        |



#### **RunType**

Specify the mode in which the program runs on the client computer.


The default value is `Normal`.



Valid Values:

* Normal
* Minimized
* Maximized
* Hidden






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[RunType]`|false   |named   |False        |



#### **StandardProgramName**

Specify the standard program name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
None





---


### Outputs
* IResultObject#SMS_Program






---


### Notes
For more information on this return object and its properties, see SMS_Program server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_program-server-wmi-class).



---


### Syntax
```PowerShell
New-CMProgram [-AddSupportedOperatingSystemPlatform <IResultObject[]>] -CommandLine <String> [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DriveLetter <String>] [-DriveMode {RunWithUnc | RequiresDriveLetter | RequiresSpecificDriveLetter}] [-Duration <Int32>] [-ForceWildcardHandling] -PackageName <String> [-ProgramRunType {OnlyWhenUserIsLoggedOn | WhetherOrNotUserIsLoggedOn | OnlyWhenNoUserIsLoggedOn}] [-Reconnect <Boolean>] [-RunMode {RunWithUserRights | RunWithAdministrativeRights}] [-RunType {Normal | Minimized | Maximized | Hidden}] -StandardProgramName <String> [-UserInteraction <Boolean>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMProgram [-AddSupportedOperatingSystemPlatform <IResultObject[]>] -CommandLine <String> [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DriveLetter <String>] [-DriveMode {RunWithUnc | RequiresDriveLetter | RequiresSpecificDriveLetter}] [-Duration <Int32>] [-ForceWildcardHandling] -PackageId <String> [-ProgramRunType {OnlyWhenUserIsLoggedOn | WhetherOrNotUserIsLoggedOn | OnlyWhenNoUserIsLoggedOn}] [-Reconnect <Boolean>] [-RunMode {RunWithUserRights | RunWithAdministrativeRights}] [-RunType {Normal | Minimized | Maximized | Hidden}] -StandardProgramName <String> [-UserInteraction <Boolean>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMProgram -CommandLine <String> [-CommandLineFolder <String>] [-Comment <String>] -DeviceProgramName <String> [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DownloadProgramType {AsSoonAsPossible | OnlyOverFastNetwork | OnlyWhenTheDeviceIsDocked}] [-ForceWildcardHandling] -PackageName <String> [-Requirement <String>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMProgram -CommandLine <String> [-CommandLineFolder <String>] [-Comment <String>] -DeviceProgramName <String> [-DisableWildcardHandling] [-DiskSpaceRequirement <String>] [-DiskSpaceUnit {KB | MB | GB}] [-DownloadProgramType {AsSoonAsPossible | OnlyOverFastNetwork | OnlyWhenTheDeviceIsDocked}] [-ForceWildcardHandling] -PackageId <String> [-Requirement <String>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
