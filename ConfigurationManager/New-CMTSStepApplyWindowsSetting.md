New-CMTSStepApplyWindowsSetting
-------------------------------




### Synopsis
Create an Apply Windows Settings step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Apply Windows Settings step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Apply Windows Settings](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyWindowsSettings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepApplyWindowsSetting](Get-CMTSStepApplyWindowsSetting)



* [Remove-CMTSStepApplyWindowsSetting](Remove-CMTSStepApplyWindowsSetting)



* [Set-CMTSStepApplyWindowsSetting](Set-CMTSStepApplyWindowsSetting)



* [About task sequence steps: Apply Windows Settings](About task sequence steps: Apply Windows Settings)





---


### Examples
#### Example 1
```PowerShell
$tz = Get-TimeZone -Id "Russian Standard Time"

$step = New-CMTSStepApplyWindowsSetting -Name "Apply Windows Settings for Moscow office" -UserName "Natalia Ivanovna" -OrganizationName "Contoso" -TimeZone $tz -InputLocale "ru-ru" -SystemLocale "ru-ru" -UILanguage "ru-ru" UserLocale "ru-ru"

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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputLocale**

Use this parameter to set the locale setting for the default keyboard layout. For example, to set it to Russian (Russia), specify the string ru-ru : `-InputLocale "ru-ru"`


For more information on these Windows setup answer file values, see Microsoft-Windows-International-Core (/windows-hardware/customize/desktop/unattend/microsoft-windows-international-core).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **OrganizationName**

Specify the registered organization name to associate with the destination computer.






|Type      |Required|Position|PipelineInput|Aliases                   |
|----------|--------|--------|-------------|--------------------------|
|`[String]`|true    |named   |False        |RegisteredOrganizationName|



#### **Password**

To enable the local Administrator account, use this parameter to specify its password. If you don't include this parameter, the local account is disabled by default with a randomly generated password.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **ProductKey**

Specify the product key to use for the Windows installation on the destination computer.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SystemLocale**

Use this parameter to set the language for non-Unicode programs. For example, to set it to Russian (Russia), specify the string ru-ru : `-SystemLocale "ru-ru"`


For more information on these Windows setup answer file values, see Microsoft-Windows-International-Core (/windows-hardware/customize/desktop/unattend/microsoft-windows-international-core).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TimeZone**

Specify the time zone to configure on the destination computer. To get this object, use the Get-TimeZone (/powershell/module/microsoft.powershell.management/get-timezone)built-in cmdlet.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeZoneInfo]`|false   |named   |False        |



#### **UILanguage**

Use this parameter to set the system default user interface (UI) language. For example, to set it to Russian (Russia), specify the string ru-ru : `-UILanguage "ru-ru"`


For more information on these Windows setup answer file values, see Microsoft-Windows-International-Core (/windows-hardware/customize/desktop/unattend/microsoft-windows-international-core).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UILanguageFallback**

Use this parameter to set the fallback language if the system default UI language is only partially localized. For example, to set it to Russian (Russia), specify the string ru-ru : `-UILanguageFallback "ru-ru"`


For more information on these Windows setup answer file values, see Microsoft-Windows-International-Core (/windows-hardware/customize/desktop/unattend/microsoft-windows-international-core).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserLocale**

Use this parameter to set the per-user settings used for formatting dates, times, currency, and numbers. For example, to set it to Russian (Russia), specify the string ru-ru : `-UserLocale "ru-ru"`


For more information on these Windows setup answer file values, see Microsoft-Windows-International-Core (/windows-hardware/customize/desktop/unattend/microsoft-windows-international-core).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**

Specify the registered user name to associate with the destination computer.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |RegisteredUserName|



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
* IResultObject#SMS_TaskSequence_ApplyWindowsSettingsAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_ApplyWindowsSettingsAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_applywindowssettingsaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepApplyWindowsSetting [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputLocale <String>] -Name <String> -OrganizationName <String> [-Password <SecureString>] [-ProductKey <String>] [-SystemLocale <String>] [-TimeZone <TimeZoneInfo>] [-UILanguage <String>] [-UILanguageFallback <String>] [-UserLocale <String>] -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
