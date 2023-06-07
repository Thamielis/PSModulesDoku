New-CMTSStepRunCommandLine
--------------------------




### Synopsis
Create a Run Command Line step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Run Command Line step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Run Command Line](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RunCommandLine).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepRunCommandLine](Get-CMTSStepRunCommandLine)



* [Remove-CMTSStepRunCommandLine](Remove-CMTSStepRunCommandLine)



* [Set-CMTSStepRunCommandLine](Set-CMTSStepRunCommandLine)



* [About task sequence steps: Run Command Line](About task sequence steps: Run Command Line)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepRunCommandLine -Name "Run Command Line" -CommandLine "cmd.exe /c copy Jan98.dat c:\sales\Jan98.dat" -PackageId "XYZ00821"

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **CommandLine**

Specify the command line that the task sequence runs. Include file name extensions, for example, `.exe`. Include all required settings files and command-line options.


For example: `cmd.exe /c copy Jan98.dat c:\sales\Jan98.dat`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Condition**

Specify a condition object to use with this step. To get this object, use one of the task sequence condition cmdlets. For example, Get-CMTSStepConditionVariable (Get-CMTSStepConditionVariable.md).






|Type               |Required|Position|PipelineInput|Aliases   |
|-------------------|--------|--------|-------------|----------|
|`[IResultObject[]]`|false   |named   |False        |Conditions|



#### **ContinueOnError**

Add this parameter to enable the step option Continue on error . When you enable this option, if the step fails, the task sequence continues.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Description**

Specify an optional description for this task sequence step.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Disable**

Add this parameter to disable this task sequence step.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[Switch]`|false   |named   |False        |DisableThisStep|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DisableWow64Redirection**

By default, 64-bit operating systems use the WOW64 file system redirector to run command lines. This behavior is to properly find 32-bit versions of OS executables and libraries. Add this parameter to disable the use of the WOW64 file system redirector. Windows runs the command using native 64-bit versions of OS executables and libraries. This option has no effect when running on a 32-bit OS.






|Type      |Required|Position|PipelineInput|Aliases                             |
|----------|--------|--------|-------------|------------------------------------|
|`[Switch]`|false   |named   |False        |DisableRedirectionFor64BitFileSystem|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **OutputVariableName**

Specify the name of a custom task sequence variable. When you use this parameter, the step saves the last 1000 characters of the command output to the variable.






|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|false   |named   |False        |Output<br/>OutputVariable|



#### **PackageId**

When you specify files or programs on the command line that don't already exist on the destination computer, use this parameter to specify the package ID for a package that has the necessary files. The package doesn't require a program. If the specified files exist on the destination computer, this option isn't required.


This value is a standard package ID, for example `XYZ00821`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RunAsUser**

Add this parameter to run the command line as a Windows user account and not the local system account. Then use the UserName and UserPassword parameters.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SuccessCode**

Specify an array of integer values as exit codes from the command that the step should evaluate as success.






|Type       |Required|Position|PipelineInput|Aliases     |
|-----------|--------|--------|-------------|------------|
|`[Int32[]]`|false   |named   |False        |SuccessCodes|



#### **Timeout**

Specify an integer value that represents how long Configuration Manager allows the command line to run. This value can be from `1` minute to `999` minutes. The default value is `15` minutes.


If you enter a value that doesn't allow enough time for the specified command to complete successfully, this step fails. The entire task sequence could fail depending on step or group conditions. If the timeout expires, Configuration Manager terminates the command-line process.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|false   |named   |False        |TimeoutInMinutes|



#### **UserName**

When you use the RunAsUser parameter, use this parameter to specify the name of the Windows user account. To specify the account password, use the UserPassword parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserPassword**

When you use the RunAsUser parameter, use this parameter to specify the password of the account that you specify with UserName .






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **WorkingDirectory**

Specify the folder in which the command starts. This path can be up to 127 characters.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |StartIn|



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
* IResultObject#SMS_TaskSequence_RunCommandLineAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_RunCommandLineAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_runcommandlineaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepRunCommandLine -CommandLine <String> [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DisableWow64Redirection] [-ForceWildcardHandling] -Name <String> [-PackageId <String>] [-RunAsUser] [-SuccessCode <Int32[]>] [-Timeout <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSStepRunCommandLine -CommandLine <String> [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DisableWow64Redirection] [-ForceWildcardHandling] [-OutputVariableName <String>] [-PackageId <String>] [-RunAsUser] [-SuccessCode <Int32[]>] [-Timeout <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSStepRunCommandLine -CommandLine <String> [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DisableWow64Redirection] [-ForceWildcardHandling] [-OutputVariableName <String>] [-PackageId <String>] [-RunAsUser] [-SuccessCode <Int32[]>] [-Timeout <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
