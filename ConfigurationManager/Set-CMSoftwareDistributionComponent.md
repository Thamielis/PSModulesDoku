Set-CMSoftwareDistributionComponent
-----------------------------------




### Synopsis
Sets properties of a software distribution component in Configuration Manager.



---


### Description

The Set-CMSoftwareDistributionComponent cmdlet sets properties of a software distribution component in Configuration Manager. You can configure the properties of an object to meet the demands that clients place on the Configuration Manager site.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareDistributionComponent](Get-CMSoftwareDistributionComponent)





---


### Examples
#### Example 1: Set properties of a software distribution component
```PowerShell
PS XYZ:\> Set-CMSoftwareDistributionComponent -SiteCode "CM2" -MaximumPackageCount 3 -MaximumThreadsPerPackage 6 -RetryCount 99 -DelayBeforeRetryingMinutes 31 -MulticastRetryCount 4 -MulticastDelayBeforeRetryingMinutes 2 -NetworkAccessAccount "Western\ElisaDaugherty"
```
The following command sets all properties for a software distribution component.


---


### Parameters
#### **AddNetworkAccessAccountName**

{{ Fill AddNetworkAccessAccountName Description }}






|Type        |Required|Position|PipelineInput|Aliases                     |
|------------|--------|--------|-------------|----------------------------|
|`[String[]]`|false   |named   |False        |AddNetworkAccessAccountNames|



#### **CleanNetworkAccessAccountName**

{{ Fill CleanNetworkAccessAccountName Description }}






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[Switch]`|false   |named   |False        |CleanNetworkAccessAccountNames|



#### **ClientComputerAccount**

Indicates that the cmdlet uses a client computer account.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DelayBeforeRetryingMins**








|Type     |Required|Position|PipelineInput|Aliases                   |
|---------|--------|--------|-------------|--------------------------|
|`[Int32]`|false   |named   |False        |DelayBeforeRetryingMinutes|



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



#### **MaximumPackageCount**

Specifies a maximum number of packages.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MaximumThreadCountPerPackage**








|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |MaximumThreadsPerPackage|



#### **MulticastDelayBeforeRetryingMins**








|Type     |Required|Position|PipelineInput|Aliases                            |
|---------|--------|--------|-------------|-----------------------------------|
|`[Int32]`|false   |named   |False        |MulticastDelayBeforeRetryingMinutes|



#### **MulticastRetryCount**

Specifies a retry count for multicast software distribution attempts.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **NetworkAccessAccountName**

Specifies an account name for network access.






|Type        |Required|Position|PipelineInput|Aliases                  |
|------------|--------|--------|-------------|-------------------------|
|`[String[]]`|false   |named   |False        |NetworkAccessAccountNames|



#### **RemoveNetworkAccessAccountName**

{{ Fill RemoveNetworkAccessAccountName Description }}






|Type        |Required|Position|PipelineInput|Aliases                        |
|------------|--------|--------|-------------|-------------------------------|
|`[String[]]`|false   |named   |False        |RemoveNetworkAccessAccountNames|



#### **RetryCount**

Specifies a retry count.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SiteCode**

Specifies a site code of a Configuration Manager site.






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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMSoftwareDistributionComponent [-AddNetworkAccessAccountName <String[]>] [-CleanNetworkAccessAccountName] [-DelayBeforeRetryingMins <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaximumPackageCount <Int32>] [-MaximumThreadCountPerPackage <Int32>] [-MulticastDelayBeforeRetryingMins <Int32>] [-MulticastRetryCount <Int32>] [-NetworkAccessAccountName <String[]>] [-RemoveNetworkAccessAccountName <String[]>] [-RetryCount <Int32>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareDistributionComponent [-ClientComputerAccount] [-DelayBeforeRetryingMins <Int32>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaximumPackageCount <Int32>] [-MaximumThreadCountPerPackage <Int32>] [-MulticastDelayBeforeRetryingMins <Int32>] [-MulticastRetryCount <Int32>] [-RetryCount <Int32>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
