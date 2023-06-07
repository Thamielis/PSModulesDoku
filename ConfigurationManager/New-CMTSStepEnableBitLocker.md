New-CMTSStepEnableBitLocker
---------------------------




### Synopsis
Create an Enable BitLocker step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Enable BitLocker step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Enable BitLocker](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_EnableBitLocker).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepEnableBitLocker](Get-CMTSStepEnableBitLocker)



* [Remove-CMTSStepEnableBitLocker](Remove-CMTSStepEnableBitLocker)



* [Set-CMTSStepEnableBitLocker](Set-CMTSStepEnableBitLocker)



* [About task sequence steps: Enable BitLocker](About task sequence steps: Enable BitLocker)





---


### Examples
#### Example 1
```PowerShell
$step = New-CMTSStepEnableBitLocker -Name "Enable BitLocker" -TpmOnly -CreateKeyOption ActiveDirectoryDomainServices -EncryptionMethod AES_256 -EnableSkipWhenNoValidTpm $false -EncryptFullDisk $false -WaitForBitLockerComplete $false

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



#### **CreateKeyOption**

Use one of the following values to specify where to create the recovery key:


* `ActiveDirectoryDomainServices`: Create the recovery password and escrow it in Active Directory (recommended)


* `DoNotCreateRecoveryKey`: Encrypt the drive, but don't create a recovery password.



Valid Values:

* ActiveDirectoryDomainServices
* DoNotCreateRecoveryKey






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[CreateKeyType]`|false   |named   |False        |



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



#### **Drive**

Specify the drive to encrypt. If you don't specify this parameter, the step encrypts the current OS drive.






|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[String]`|false   |named   |False        |SpecificDrive|



#### **EnableSkipWhenNoValidTpm**

Applies to version 2006 and later. Set this parameter to `true` to skip this step for computers that don't have a TPM or when the TPM isn't enabled.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EncryptFullDisk**

Add this parameter to use full disk encryption. By default, the Enable BitLocker step only encrypts used space on the drive.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EncryptionMethod**

Applies to version 2006 and later. Use this parameter to specify the disk encryption mode. By default or if not specified, the step continues to use the default encryption method for the OS version.



Valid Values:

* DoNotSpecify
* AES_128
* AES_256
* XTS_AES128
* XTS_AES256
* TotalCount






|Type                    |Required|Position|PipelineInput|Aliases             |
|------------------------|--------|--------|-------------|--------------------|
|`[DiskEncryptionMethod]`|false   |named   |False        |DiskEncryptionMethod|



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



#### **Pin**

If you use the parameter TpmAndPin , use this parameter to specify the PIN value. Specify 4-20 integers as a secure string.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **TpmAndPin**

Add this parameter to configure key management for the OS drive to use a TPM and a personal identification number (PIN). When you specify this option, BitLocker locks the normal boot process until the user provides the PIN. If you use this parameter, use Pin to specify the PIN value. You can't combine this parameter with TpmAndUsb , TpmOnly , or UsbOnly .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **TpmAndUsb**

Add this parameter to configure key management for the OS drive to use a TPM and a startup key stored on a USB flash drive. When you select this option, BitLocker locks the normal boot process until a USB device that contains a BitLocker startup key is attached to the computer. You can't combine this parameter with TpmAndPin , TpmOnly , or UsbOnly .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **TpmOnly**

Add this parameter to configure key management for the OS drive to only use a TPM. You can't combine this parameter with TpmAndPin , TpmAndUsb , or UsbOnly .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UsbOnly**

Add this parameter to configure key management for the OS drive to only use a startup key stored on a USB flash drive. When you select this option, BitLocker locks the normal boot process until a USB device that contains a BitLocker startup key is attached to the computer. You can't combine this parameter with TpmAndPin , TpmAndUsb , or TpmOnly .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **WaitForBitLockerComplete**

Add this parameter to configure the step to wait for BitLocker to complete the drive encryption process on all drives before continuing task sequence execution.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_EnableBitLockerAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_EnableBitLockerAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_enablebitlockeraction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepEnableBitLocker [-Condition <IResultObject[]>] [-ContinueOnError] [-CreateKeyOption {ActiveDirectoryDomainServices | DoNotCreateRecoveryKey}] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-Drive <String>] [-EnableSkipWhenNoValidTpm <Boolean>] [-EncryptFullDisk] [-EncryptionMethod {DoNotSpecify | AES_128 | AES_256 | XTS_AES128 | XTS_AES256 | TotalCount}] [-ForceWildcardHandling] -Name <String> [-Pin <SecureString>] [-TpmAndPin] [-TpmAndUsb] [-TpmOnly] [-UsbOnly] [-WaitForBitLockerComplete] [-Confirm] [-WhatIf] [<CommonParameters>]
```
