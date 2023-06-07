New-CMTSStepConditionRegistry
-----------------------------




### Synopsis
Create a registry setting condition for a task sequence step.



---


### Description

Use this cmdlet to create a registry setting condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionRegistry](Get-CMTSStepConditionRegistry)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1
```PowerShell
$root = "HKeyLocalMachine"
$key = "SOFTWARE\Microsoft\CCM\Logging\@Global"
$name = "LogLevel"
$type = "RegistryDWord"
$value = 1

$condition = New-CMTSStepConditionRegistry -RootKey $root -RegistryKey $key -RegistryOperator Equals -RegistryValueName $name -ValueType $type -RegistryValueData $value

$tsNameOsd = "Default OS deployment"
$tsStepNameDynVar = "Set Dynamic Variables"

Set-CMTSStepSetDynamicVariable -TaskSequenceName $tsNameOsd -StepName $tsStepNameDynVar -AddCondition $condition
```
This sample script creates the following condition on the step:


`Registry  "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\CCM\Logging\@Global\LogLevel" (REG_DWORD) equals "1"`


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RegistryKey**

Specify the registry key path to check. For example, with the `HKeyLocalMachine` RootKey , you can specify the registry key `SOFTWARE\Microsoft\CCM`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RegistryOperator**

Use this parameter to specify the operator for the task sequence to evaluate the registry value. If you use the `Exists` or `NotExists` values, then you don't need to use the RegistryValueData parameter.



Valid Values:

* Exists
* NotExists
* Equals
* NotEquals
* Greater
* GreaterEqual
* Less
* LessEqual
* Like
* NotLike






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[VariableOperatorType]`|true    |named   |False        |



#### **RegistryValueData**

If you use a comparative RegistryOperator like `Equals`, use this parameter to specify the value data to evaluate. Use ValueType to specify the registry type.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RegistryValueName**

Specify the name of the registry value to check. If you don't specify this parameter, the condition checks the (Default) value of the specified RegistryKey .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RootKey**

Specify the registry root key to check.



Valid Values:

* HKeyCurrentUser
* HKeyLocalMachine
* HKeyUsers
* HKeyCurrentConfig






|Type                   |Required|Position|PipelineInput|
|-----------------------|--------|--------|-------------|
|`[RegistryRootKeyType]`|true    |named   |False        |



#### **ValueType**

Specify the type of registry value to check. Use this parameter with the RegistryValueData to specify the value data.



Valid Values:

* RegistrySZ
* RegistryExpandSZ
* RegistryDWord






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[RegistryValueType]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_RegistryConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_RegistryConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_registryconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConditionRegistry [-DisableWildcardHandling] [-ForceWildcardHandling] -RegistryKey <String> -RegistryOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual} [-RegistryValueData <String>] [-RegistryValueName <String>] -RootKey {HKeyCurrentUser | HKeyLocalMachine | HKeyUsers | HKeyCurrentConfig} [-ValueType {RegistrySZ | RegistryExpandSZ | RegistryDWord}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
