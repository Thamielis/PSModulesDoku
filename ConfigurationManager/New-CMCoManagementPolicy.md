New-CMCoManagementPolicy
------------------------




### Synopsis
Create a co-management policy for a site.



---


### Description

Use this cmdlet to create a co-management policy for a site. You can also switch workloads at the same time. For more information, see How to enable co-management in Configuration Manager (/mem/configmgr/comanage/how-to-enable).



After you create this policy, use the New-CMConfigurationPolicyDeployment (New-CMConfigurationPolicyDeployment.md)cmdlet to deploy it to a collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMConfigurationPolicyDeployment](New-CMConfigurationPolicyDeployment)



* [Get-CMConfigurationPolicy](Get-CMConfigurationPolicy)



* [Remove-CMConfigurationPolicy](Remove-CMConfigurationPolicy)



* [How to enable co-management in Configuration Manager](How to enable co-management in Configuration Manager)



* [Co-management workloads](Co-management workloads)





---


### Examples
#### Example 1
```PowerShell
$CoMgmtPolicyName = "CoMgmtSettingsProd"

New-CMCoManagementPolicy -CoManagementPolicyName $CoMgmtPolicyName -AutoEnroll $true -CAWorkloadEnabled $false -RAWorkloadEnabled $false -WufbWorkloadEnabled $false -EPWorkloadEnabled $false -DCWorkloadEnabled $false -O365WorkloadEnabled $false -ClientAppsWorkloadEnabled $false

New-CMConfigurationPolicyDeployment -CoManagementPolicyName $CoMgmtPolicyName -CollectionId "XYZ00042"
```



---


### Parameters
#### **AutoEnroll**

Set this parameter to $true to enable automatic client enrollment in Intune for existing Configuration Manager clients.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|true    |named   |False        |



#### **CAWorkloadEnabled**

Set this parameter to $true to switch the Compliance policies workload to Intune. For more information, see Co-management workloads (/mem/configmgr/comanage/workloads).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientAppsWorkloadEnabled**

Set this parameter to $true to switch the Client apps workload to Intune. For more information, see Co-management workloads (/mem/configmgr/comanage/workloads).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CoManagementPolicyName**

Specify the name for the policy to create.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DCWorkloadEnabled**

Set this parameter to $true to switch the Device configuration workload to Intune. For more information, see Co-management workloads (/mem/configmgr/comanage/workloads).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EPWorkloadEnabled**

Set this parameter to $true to switch the Endpoint protection workload to Intune. For more information, see Co-management workloads (/mem/configmgr/comanage/workloads).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **O365WorkloadEnabled**

Set this parameter to $true to switch the Office Click-to-Run apps workload to Intune. For more information, see Co-management workloads (/mem/configmgr/comanage/workloads).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RAWorkloadEnabled**

Set this parameter to $true to switch the Resource access policies workload to Intune. For more information, see Co-management workloads (/mem/configmgr/comanage/workloads).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **WufbWorkloadEnabled**

Set this parameter to $true to switch the Windows Update policies workload to Intune. For more information, see Co-management workloads (/mem/configmgr/comanage/workloads).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_ConfigurationPolicy






---


### Notes
For more information on this return object and its properties, see SMS_ConfigurationPolicy server WMI class (/mem/configmgr/develop/reference/compliance/sms_configurationpolicy-server-wmi-class).



---


### Syntax
```PowerShell
New-CMCoManagementPolicy -AutoEnroll <Boolean> [-CAWorkloadEnabled <Boolean>] [-ClientAppsWorkloadEnabled <Boolean>] [-CoManagementPolicyName <String>] [-DCWorkloadEnabled <Boolean>] [-DisableWildcardHandling] [-EPWorkloadEnabled <Boolean>] [-ForceWildcardHandling] [-O365WorkloadEnabled <Boolean>] [-RAWorkloadEnabled <Boolean>] [-WufbWorkloadEnabled <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
