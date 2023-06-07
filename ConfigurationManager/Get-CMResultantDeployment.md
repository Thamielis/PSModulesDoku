Get-CMResultantDeployment
-------------------------




### Synopsis
{{ Fill in the Synopsis }}



---


### Description

{{ Fill in the Description }}



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> {{ Add example code here }}
```
{{ Add example description here }}


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



#### **InputObject**

{{ Fill InputObject Description }}






|Type             |Required|Position|PipelineInput |Aliases                     |
|-----------------|--------|--------|--------------|----------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Resource<br/>Device<br/>User|



#### **ResourceId**

{{ Fill ResourceId Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|true    |0       |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_DeploymentSummary


* IResultObject#SMS_DeploymentSummary






---


### Notes




---


### Syntax
```PowerShell
Get-CMResultantDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMResultantDeployment [-ResourceId] <UInt32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
