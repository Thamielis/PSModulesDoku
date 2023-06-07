New-CMTSStepConnectNetworkFolder
--------------------------------




### Synopsis
Create a Connect To Network Folder step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Connect To Network Folder step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Connect To Network Folder](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ConnectToNetworkFolder).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepConnectNetworkFolder](Get-CMTSStepConnectNetworkFolder)



* [Remove-CMTSStepConnectNetworkFolder](Remove-CMTSStepConnectNetworkFolder)



* [Set-CMTSStepConnectNetworkFolder](Set-CMTSStepConnectNetworkFolder)



* [About task sequence steps: Connect To Network Folder](About task sequence steps: Connect To Network Folder)





---


### Examples
#### Example 1
```PowerShell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force

$step = New-CMTSStepConnectNetworkFolder -Name "Connect To Network Folder" -Drive "Z:" -Path "\\server\share$" -UserName "contoso\_osdnetfolder" -UserPassword $Secure_String_Pwd

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



#### **Drive**

Specify the local drive letter to assign for this connection.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |DriveLetter|



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



#### **Path**

Specify the network folder path. Use the format `\server\share`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserName**

Specify the user account with permissions to connect to this network folder. Also use the UserPassword parameter.


For more information on this account, see the task sequence network folder connection account (/mem/configmgr/core/plan-design/hierarchy/accounts#task-sequence-network-folder-connection-account).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **UserPassword**

Specify the password for the UserName .






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_ConnectNetworkFolderAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_ConnectNetworkFolderAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_connectnetworkfolderaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepConnectNetworkFolder [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-Drive <String>] [-ForceWildcardHandling] -Name <String> -Path <String> -UserName <String> [-UserPassword <SecureString>] [-Confirm] [-WhatIf] [<CommonParameters>]
```