New-CMTSStepConditionSoftware
-----------------------------




### Synopsis
Create an installed software condition for a task sequence step.



---


### Description

Use this cmdlet to create an installed software condition object for a task sequence step. Then use one of the New-CMTSStep\ or Set-CMTSStep\ cmdlets with the Condition or AddCondition** parameters. For example, Set-CMTSStepApplyDataImage (Set-CMTSStepApplyDataImage.md).



For more information, see Use the task sequence editor: Conditions (/mem/configmgr/osd/understand/task-sequence-editor#bkmk_conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConditionSoftware](Get-CMTSStepConditionSoftware)



* [Use the task sequence editor: Conditions](Use the task sequence editor: Conditions)





---


### Examples
#### Example 1
```PowerShell
$msi = "\\cm01.contoso.com\SMS_XYZ\bin\i386\adminconsole.msi"

$condition = New-CMTSStepConditionSoftware -MsiFilePath $msi -IsAnyVersion $true

$tsNameOsd = "Default OS deployment"
$tsStepNameRunPwsh = "Run PowerShell Script"

Set-CMTSStepRunPowerShellScript -TaskSequenceName $tsNameOsd -StepName $tsStepNameRunPwsh -AddCondition $condition
```
This sample script creates the following condition on the step:


`Software  An version of "Microsoft Endpoint Configuration Manager Console" installed`


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



#### **IsAnyVersion**

Use this parameter to determine how the condition matches the MSI codes:


* `$true`: Match any version of this product, MSI upgrade code only - `$false`: Match this specific product, MSI product code and upgrade code If you don't specify this parameter, by default it matches the specific product.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MsiFilePath**

Specify the path to the MSI file to evaluate. The cmdlet reads the product details from this MSI. The path to the MSI isn't saved, just the product details.


For example, it saves the following details for the Configuration Manager version 2107 AdminConsole.msi :


* `ProductCode`: {B3842C82-95EB-472C-940A-D82C4A10857D} - `ProductName`: Microsoft Endpoint Configuration Manager Console - `UpgradeCode`: {B038D5E8-6C93-4A05-9E21-240324CFDF0E} - `Version`: 5.2107.1059.1000






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
* IResultObject#SMS_TaskSequence_SoftwareConditionExpression






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_SoftwareConditionExpression server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_softwareconditionexpression-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConditionSoftware [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsAnyVersion <Boolean>] -MsiFilePath <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
