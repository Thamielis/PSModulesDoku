New-CMTSRule
------------




### Synopsis
Create a rule to add to a Set Dynamic Variables task sequence step.



---


### Description

Use this cmdlet to create a rule object that you add to a Set Dynamic Variables task sequence step. To add rules, use the New-CMTSStepSetDynamicVariable (New-CMTSStepSetDynamicVariable.md) or [Set-CMTSStepSetDynamicVariable](Set-CMTSStepSetDynamicVariable.md)cmdlets. When the task sequence runs this step, it evaluates the dynamic rules and variables in order. When it evaluates the rules on the specific device, it can then set task sequence variables based on those rules.



There are four types of rules:



- Computer : Evaluate values for hardware asset tag, UUID, serial number, or MAC address. - Location : Evaluate values for the default network gateway. - Make and Model : Evaluate values for the make and model of a computer. - Task sequence variable : Add a task sequence variable, condition, and value to evaluate.



For more information, see Dynamic rules and variables (/mem/configmgr/osd/understand/task-sequence-steps#dynamic-rules-and-variables).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMTSStepSetDynamicVariable](Set-CMTSStepSetDynamicVariable)



* [New-CMTSStepSetDynamicVariable](New-CMTSStepSetDynamicVariable)



* [About task sequence steps - Set Dynamic Variables](About task sequence steps - Set Dynamic Variables)



* [How to use task sequence variables in Configuration Manager](How to use task sequence variables in Configuration Manager)





---


### Examples
#### Example 1: Set the download destination if in Windows PE
```PowerShell
$tsrule = New-CMTSRule -Variable @{'OSDDownloadDestinationLocationType' = 'TSCache'} -ReferencedVariableName "_SMSTSInWinPE" -ReferencedVariableOperator equals -ReferencedVariableValue TRUE

$tsname = "Default IPU"
$tsstep = "Set Dynamic Variables"

Set-CMTSStepSetDynamicVariable -TaskSequenceName $tsname -StepName $tsstep -AddRule $tsrule
```



---


### Parameters
#### **AssetTag**

Specify an Asset tag for the Computer rule type. The maximum value is 255 characters.


For example, if you set this value to `123456`, it adds the following rule: `IF Asset tag equals "123456" THEN`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DefaultGateway**

Specify the Default gateway for the Location rule type.


For example, if you set this value to `192.168.10.1`, it adds the following rule: `IF Default gateway equals "192.168.10.1" THEN`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **MacAddress**

Specify the MAC address for the Computer rule type.


For example, if you set this value to `00:11:22:33:44:55`, it adds the following rule: `IF MAC address equals "00:11:22:33:44:55" THEN`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Make**

Specify the Make for the Make and Model rule type. To set the other value, use the Model parameter. The rule evaluates true when both values are true.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character




For example, if you set this value to `Surface` and the Model to ` `, it adds the following rule: `IF Make equals "Surface" AND Model equals " " THEN`







|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Model**

Specify the Model for the Make and Model rule type. To set the other value, use the Make parameter. The rule evaluates true when both values are true.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character




For example, if you set this value to ` ` and the Make to `Surface`, it adds the following rule: `IF Make equals "Surface" AND Model equals " " THEN`







|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ReferencedVariableName**

Specify the Variable for the Task Sequence Variable rule type. It requires that you also set the ReferencedVariableOperator and ReferencedVariableValue parameters.


This variable name can be a built-in task sequence variable or a custom one that you created. For more information, see How to use task sequence variables in Configuration Manager (/mem/configmgr/osd/understand/using-task-sequence-variables).


For example, if you set the following values:


* ReferencedVariableName : `OSDRegisteredOrgName` - ReferencedVariableOperator : `Equals` - ReferencedVariableValue : `Contoso`


Then it adds the following rule: `IF OSDRegisteredOrgName equals "Contoso" THEN`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ReferencedVariableOperator**

Specify the Condition for the Task Sequence Variable rule type. It requires that you also set the ReferencedVariableName and ReferencedVariableValue parameters. For the available operators, see the list of accepted values for this parameter.


For example, if you set the following values:


* ReferencedVariableName : `OSDRegisteredOrgName` - ReferencedVariableOperator : `Equals` - ReferencedVariableValue : `Contoso`


Then it adds the following rule: `IF OSDRegisteredOrgName equals "Contoso" THEN`



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
|`[VariableOperatorType]`|false   |named   |False        |



#### **ReferencedVariableValue**

Specify the Value for the Task Sequence Variable rule type. It requires that you also set the ReferencedVariableName and ReferencedVariableOperator parameters.


For example, if you set the following values:


* ReferencedVariableName : `OSDRegisteredOrgName` - ReferencedVariableOperator : `Equals` - ReferencedVariableValue : `Contoso`


Then it adds the following rule: `IF OSDRegisteredOrgName equals "Contoso" THEN`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SerialNumber**

Specify a Serial number for the Computer rule type.


For example, if you set this value to `123456`, it adds the following rule: `IF Asset tag equals "123456" THEN`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Uuid**

Specify a UUID for the Computer rule type.


For example, if you set this value to `de5ba380-f692-45e0-bbd3-0e40543b549e`, it adds the following rule: `IF UUID equals "de5ba380-f692-45e0-bbd3-0e40543b549e" THEN`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Variable**

Specify the existing or custom task sequence variables and associated values that the step should set when the rule evaluates to true.


For example, if you set this value to  `@{'OSDDownloadDestinationLocationType' = 'TSCache'}`, it adds the following variable after the `THEN` of the rule: `SET OSDDownloadDestinationLocationType = "TSCache"`


To specify more than one variable in the same hashtable, use a semi-colon (`;`) delimiter. For example: `@{'OSDRegisteredUserName' = 'Contoso';'OSDRegisteredOrgName' = 'Contoso'}`






|Type         |Required|Position|PipelineInput|Aliases  |
|-------------|--------|--------|-------------|---------|
|`[Hashtable]`|true    |named   |False        |Variables|



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
* IResultObject#SMS_TaskSequence_Rule






---


### Notes




---


### Syntax
```PowerShell
New-CMTSRule [-AssetTag <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MacAddress <String>] [-SerialNumber <String>] [-Uuid <String>] -Variable <Hashtable> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSRule [-DefaultGateway <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Variable <Hashtable> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSRule [-DisableWildcardHandling] [-ForceWildcardHandling] [-Make <String>] [-Model <String>] -Variable <Hashtable> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMTSRule [-DisableWildcardHandling] [-ForceWildcardHandling] [-ReferencedVariableName <String>] [-ReferencedVariableOperator {Exists | NotExists | Equals | NotEquals | Greater | GreaterEqual | Less | LessEqual | Like | NotLike}] [-ReferencedVariableValue <String>] -Variable <Hashtable> [-Confirm] [-WhatIf] [<CommonParameters>]
```
