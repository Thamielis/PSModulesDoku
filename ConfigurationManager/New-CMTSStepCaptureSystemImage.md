New-CMTSStepCaptureSystemImage
------------------------------




### Synopsis
Create a Capture OS Image step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Capture OS Image step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Capture OS Image](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_CaptureOperatingSystemImage).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepCaptureSystemImage](Get-CMTSStepCaptureSystemImage)



* [Remove-CMTSStepCaptureSystemImage](Remove-CMTSStepCaptureSystemImage)



* [Set-CMTSStepCaptureSystemImage](Set-CMTSStepCaptureSystemImage)



* [About task sequence steps: Capture OS Image](About task sequence steps: Capture OS Image)





---


### Examples
#### Example 1
```PowerShell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force

$step = New-CMTSStepCaptureSystemImage -Name "Capture OS Image" -Path "\\server\share$\images\image.wim" -UserName "contoso\_osdcapture" -Password $Secure_String_Pwd -ImageCreator "Meaghan C" -ImageDescription "The Virginia moon image" -ImageVersion "1.3b"

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



#### **ImageCreator**

Specify the name of the user that created the OS image. This string is stored in the image file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ImageDescription**

Specify a description of the captured OS image. This string is stored in the image file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ImageVersion**

Specify a version number to assign to the captured OS image. This value can be any combination of letters and numbers. It's stored in the image file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify a name for this step to identify it in the task sequence.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |StepName|



#### **Password**

Specify the password for the UserName that has permissions to the network share.






|Type            |Required|Position|PipelineInput|Aliases        |
|----------------|--------|--------|-------------|---------------|
|`[SecureString]`|false   |named   |False        |CapturePassword|



#### **Path**

Specify the network path to the location that Configuration Manager uses when storing the captured OS image.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |CaptureDestination|



#### **UserName**

Specify the username of the account that has permissions to write to the Path location. Also use the Password parameter.


For more information on this account, see Capture OS image account (/mem/configmgr/core/plan-design/hierarchy/accounts#capture-os-image-account).






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |CaptureUserName|



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
* IResultObject#SMS_TaskSequence_CaptureSystemImageAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_CaptureSystemImageAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_capturesystemimageaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepCaptureSystemImage [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ImageCreator <String>] [-ImageDescription <String>] [-ImageVersion <String>] -Name <String> [-Password <SecureString>] -Path <String> -UserName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
