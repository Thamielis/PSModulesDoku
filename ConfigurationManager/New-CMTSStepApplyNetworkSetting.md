New-CMTSStepApplyNetworkSetting
-------------------------------




### Synopsis
Create an Apply Network Settings step, which you can add to a task sequence.



---


### Description

This cmdlet creates a new Apply Network Settings step object. Then use the Add-CMTaskSequenceStep (Add-CMTaskSequenceStep.md) cmdlet to add the step to a task sequence. For more information on this step, see [About task sequence steps: Apply Network Settings](/mem/configmgr/osd/understand/task-sequence-steps#BKMK_ApplyNetworkSettings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMTSStepApplyNetworkSetting](Get-CMTSStepApplyNetworkSetting)



* [Remove-CMTSStepApplyNetworkSetting](Remove-CMTSStepApplyNetworkSetting)



* [Set-CMTSStepApplyNetworkSetting](Set-CMTSStepApplyNetworkSetting)



* [New-CMTSNetworkAdapterSetting](New-CMTSNetworkAdapterSetting)



* [About task sequence steps: Apply Network Settings](About task sequence steps: Apply Network Settings)





---


### Examples
#### Example 1
```PowerShell
$Secure_String_Pwd = ConvertTo-SecureString "P@ssW0rD!" -AsPlainText -Force

$step = New-CMTSStepApplyNetworkSetting -Name "Apply network settings" -DnsSuffix "corp.contoso.com" -DomainName "na.corp.contoso.com" -DomainOU "LDAP://OU=Ops,OU=ITS,DC=na,DC=corp,DC=contoso,DC=com" -UserName "contoso\_cmosdjoin" -UserPassword $Secure_String_Pwd

$tsNameOsd = "Default OS deployment"
$tsOsd = Get-CMTaskSequence -Name $tsNameOsd -Fast

$tsOsd | Add-CMTaskSequenceStep -Step $step -InsertStepStartIndex 11
```



---


### Parameters
#### **AddAdapterSetting**

Specify a network adapter settings object to add to this step. To get this object, use the New-CMTSNetworkAdapterSetting (New-CMTSNetworkAdapterSetting.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases           |
|-------------------|--------|--------|-------------|------------------|
|`[IResultObject[]]`|false   |named   |False        |AddAdapterSettings|



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



#### **DnsSuffix**

Specify the DNS suffix. For example, `corp.contoso.com`. This setting is applied to all connections with TCP/IP enabled.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DomainName**

To configure this step to have the computer join a domain, use this parameter to specify the name of a domain to join. Then use the following other parameters:


* DomainOU : Optionally specify an organizational unit in which to create the new computer account - UserName : Specify the user account with permissions to join a computer to the domain - UserPassword : Specify the password for the user account.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DomainOU**

When you use the DomainName parameter, you can also specify the path to an organizational unit (OU). When the computer joins the domain, if it creates a new computer account, that account will be in this OU.


For example, `LDAP://OU=MyOu,DC=MyDom,DC=MyCompany,DC=com`






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **EnableTcpIpFiltering**

Add this parameter to enable TCP/IP filtering for the connection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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



#### **UserName**

When you use the DomainName parameter, use this parameter to specify the domain user account that's used to add the destination computer to the domain. Use the UserPassword parameter to specify the account password.


For more information, see the task sequence domain joining account (/mem/configmgr/core/plan-design/hierarchy/accounts#task-sequence-domain-join-account).






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |DomainUserName|



#### **UserPassword**

Specify the password as a secure string for the UserName parameter.






|Type            |Required|Position|PipelineInput|Aliases           |
|----------------|--------|--------|-------------|------------------|
|`[SecureString]`|false   |named   |False        |DomainUserPassword|



#### **WorkgroupName**

To configure this step to have the computer join a workgroup, use this parameter to specify the workgroup name.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* IResultObject#SMS_TaskSequence_ApplyNetworkSettingsAction






---


### Notes
For more information on this return object and its properties, see SMS_TaskSequence_ApplyNetworkSettingsAction server WMI class (/mem/configmgr/develop/reference/osd/sms_tasksequence_applynetworksettingsaction-server-wmi-class).



---


### Syntax
```PowerShell
New-CMTSStepApplyNetworkSetting [-AddAdapterSetting <IResultObject[]>] [-Condition <IResultObject[]>] [-ContinueOnError] [-Description <String>] [-Disable] [-DisableWildcardHandling] [-DnsSuffix <String>] [-DomainName <String>] [-DomainOU <String>] [-EnableTcpIpFiltering] [-ForceWildcardHandling] -Name <String> [-UserName <String>] [-UserPassword <SecureString>] [-WorkgroupName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
