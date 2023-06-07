New-CMTSStepRunPowerShellScript
-------------------------------




### Synopsis
Create the Run PowerShell Script step in a task sequence.



---


### Description

This cmdlet creates a new Run PowerShell Script step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Run PowerShell Script](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_RunPowerShellScript).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepRunPowerShellScript](Get-CMTSStepRunPowerShellScript)



* [Remove-CMTSStepRunPowerShellScript](Remove-CMTSStepRunPowerShellScript)



* [Set-CMTSStepRunPowerShellScript](Set-CMTSStepRunPowerShellScript)



* [About task sequence steps: Run PowerShell Script](About task sequence steps: Run PowerShell Script)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepRunPowerShellScript -Name "Run PowerShell Script" -PackageId "XYZ00821" -ScriptName "Add-ContosoBranding.ps1" -ExecutionPolicy AllSigned 

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
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



#### **ExecutionPolicy**

Specify the PowerShell execution policy for the scripts you allow to run on the computer. Choose one of the following policies:


* `AllSigned`: Only run scripts signed by a trusted publisher.


* `Undefined`: Don't define any execution policy.


* `Bypass`: Load all configuration files and run all scripts. If you download an unsigned script from the internet, PowerShell doesn't prompt for permission before running the script.



Valid Values:

* AllSigned
* Undefined
* Bypass






|Type                   |Required|Position|PipelineInput|Aliases                  |
|-----------------------|--------|--------|-------------|-------------------------|
|`[ExecutionPolicyType]`|false   |named   |False        |PowerShellExecutionPolicy|



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

Specify the package ID for the package that has the PowerShell script. The package doesn't require a program. One package can contain multiple scripts.


This value is a standard package ID, for example `XYZ00821`.


Then use the ScriptName parameter to specify the name of the script.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Parameter**

Specify the parameters passed to the PowerShell script. These parameters are the same as the PowerShell script parameters on the command line. Provide parameters consumed by the script, not for the PowerShell command line.


The following example contains valid parameters:


`-MyParameter1 MyValue1 -MyParameter2 MyValue2`


The following example contains invalid parameters. The first two items are PowerShell command-line parameters ( NoLogo and ExecutionPolicy ). The script doesn't consume these parameters.


`-NoLogo -ExecutionPolicy Unrestricted -File MyScript.ps1 -MyParameter1 MyValue1 -MyParameter2 MyValue2`


If a parameter value includes a special character or a space, use single quotation marks (`'`) around the value. Using double quotation marks (`"`) may cause the task sequence step to incorrectly process the parameter.


For example: `-Arg1 '%TSVar1%' -Arg2 '%TSVar2%'`


You can also set this parameter to a task sequence variable. For example, if you specify `%MyScriptVariable%`, when the task sequence runs the script, it adds the value of this custom variable to the PowerShell command line.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |Parameters|



#### **ScriptName**

Specify the name of the script to run. This script is in the package specified by the PackageId parameter.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SourceScript**

Instead of using the PackageId and ScriptName parameters, use this parameter to directly specify the script commands. This string value is the PowerShell commands that this step runs.


You can read the contents of an existing script file into a string variable, and then use that variable for this parameter. For example:


`$script = [IO.File]::ReadAllText( "C:\temp\script.ps1" )`






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|true    |named   |False        |SourceCode|



#### **SuccessCode**

Specify an array of integer values as exit codes from the script that the step should evaluate as success.






|Type       |Required|Position|PipelineInput|Aliases     |
|-----------|--------|--------|-------------|------------|
|`[Int32[]]`|false   |named   |False        |SuccessCodes|



#### **TimeoutMins**

Specify an integer value that represents how long Configuration Manager allows the script to run. This value can be from `1` minute to `999` minutes. The default value is `15` minutes.


If you enter a value that doesn't allow enough time for the specified script to complete successfully, this step fails. The entire task sequence could fail depending on step or group conditions. If the timeout expires, Configuration Manager terminates the PowerShell process.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|false   |named   |False        |TimeoutInMinutes|



#### **UserName**

Use this parameter to run the script as a Windows user account and not the local system account. Specify the name of the Windows user account. To specify the account password, use the UserPassword parameter.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |User   |



#### **UserPassword**

Use this parameter to specify the password of the account that you specify with UserName .






|Type            |Required|Position|PipelineInput|Aliases |
|----------------|--------|--------|-------------|--------|
|`[SecureString]`|false   |named   |False        |Password|



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
* IResultObject#SMS_TaskSequence_RunPowerShellScriptAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_RunPowerShellScriptAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_runpowershellscriptaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepRunPowerShellScript [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ExecutionPolicy {AllSigned | Undefined | Bypass}] [-ForceWildcardHandling] -Name <String> [-OutputVariableName <String>] [-Parameter <String>] -SourceScript <String> [-SuccessCode <Int32[]>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSStepRunPowerShellScript [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ExecutionPolicy {AllSigned | Undefined | Bypass}] [-ForceWildcardHandling] -Name <String> [-OutputVariableName <String>] -PackageId <String> [-Parameter <String>] -ScriptName <String> [-SuccessCode <Int32[]>] [-TimeoutMins <Int32>] [-UserName <String>] [-UserPassword <SecureString>] [-WorkingDirectory <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
