Get-CMOrchestrationGroup
------------------------




### Synopsis
Get an orchestration group object.



---


### Description

Use this cmdlet to get an orchestration group object by name or ID. You can use this object to start, remove, or configure the orchestration group. For these other actions, use the following cmdlets:



- Invoke-CMOrchestrationGroup (invoke-cmorchestrationgroup.md)- Remove-CMOrchestrationGroup (remove-cmorchestrationgroup.md)- Set-CMOrchestrationGroup (set-cmorchestrationgroup.md)Use orchestration groups to better control the deployment of software updates to devices. You may need to carefully manage updates for specific workloads, or automate behaviors in between. For more information, see About orchestration groups in Configuration Manager (/mem/configmgr/sum/deploy-use/orchestration-groups).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Invoke-CMOrchestrationGroup](Invoke-CMOrchestrationGroup)



* [New-CMOrchestrationGroup](New-CMOrchestrationGroup)



* [Remove-CMOrchestrationGroup](Remove-CMOrchestrationGroup)



* [Set-CMOrchestrationGroup](Set-CMOrchestrationGroup)



* [About orchestration groups in Configuration Manager](About orchestration groups in Configuration Manager)





---


### Examples
#### Example 1: View details about members of an orchestration group
```PowerShell
$og = Get-CMOrchestrationGroup -Name "IT servers"

foreach ( $member in $og.MOGMembers ) {
  Get-CMDevice -Id $member -Fast | Select-Object Name, Build
}
```

#### Example 2: Get orchestration groups with unapproved scripts
```PowerShell
Get-CMOrchestrationGroup | Where-Object ( $_.PostScriptApprovalState -eq $false -or $_.PreScriptApprovalState -eq $false ) | Select-Object Name
```



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



#### **Id**

Specify the ID of orchestration group to get. This value is the MOGID property, which is an integer. For example, `16777217`.






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|true    |0       |False        |MOGID  |



#### **Name**

Specify the name of the orchestration group to get.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|false   |0       |False        |OrchestrationGroupName|





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_MachineOrchestrationGroup






---


### Notes
This cmdlet returns an object for the SMS_MachineOrchestrationGroup WMI class.



---


### Syntax
```PowerShell
Get-CMOrchestrationGroup [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMOrchestrationGroup [[-Name] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
