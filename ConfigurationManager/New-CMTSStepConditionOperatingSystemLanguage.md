New-CMTSStepConditionOperatingSystemLanguage
--------------------------------------------




### Synopsis
Create an OS language condition for a task sequence step.



---


### Description

Use this cmdlet to create an OS language condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionQueryWmi](Get-CMTSStepConditionQueryWmi)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1
```PowerShell
$langIdIrish = 2108
$condition = New-CMTSStepConditionOperatingSystemLanguage -OSLanguageId $langIdIrish

$tsNameOsd = "AAron"
$tsStepNameDynVar = "Set Dynamic Variables"

Set-CMTSStepSetDynamicVariable -TaskSequenceName $tsNameOsd -StepName $tsStepNameDynVar -AddCondition $condition
```
This sample script creates the following condition on the step:


`WMI Query  SELECT OsLanguage FROM Win32_OperatingSystem WHERE OsLanguage='2108'`


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



#### **OSLanguageId**

Use this parameter to configure the specific OS language. This check compares the language ID to the OSLanguage property of the Win32_OperatingSystem WMI class on the client. For example, `1033` for English (United States) .


This value is the decimal equivalent of the Windows language ID . For example, `1033` is `0x0409` for English (United States) , and `2070` is `0x0816` for Portuguese (Portugal) . For more information, see [MS-LCID]: Windows Language Code Identifier (LCID) Reference (/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c).






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



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
* IResultObject#SMS_TaskSequence_WMIConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_WMIConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_wmiconditionexpression-server-wmi-class).

You can only set a single language ID per condition. To add a condition for multiple language IDs, first create multiple OS language conditions. Then nest them in an if statement condition with the New-CMTSStepConditionIfStatement (New-CMTSStepConditionIfStatement.md)cmdlet.

To get an OS language condition, use the Get-CMTSStepConditionQueryWmi (Get-CMTSStepConditionQueryWmi.md)cmdlet. The task sequence editor option to add an OS Language condition is a shortcut for a specific WMI query.



---


### Syntax
```PowerShell
New-CMTSStepConditionOperatingSystemLanguage [-DisableWildcardHandling] [-ForceWildcardHandling] -OSLanguageId <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
