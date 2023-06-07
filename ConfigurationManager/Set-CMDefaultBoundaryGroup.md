Set-CMDefaultBoundaryGroup
--------------------------




### Synopsis

Set-CMDefaultBoundaryGroup [-PassThru] [-IncludeCloudBasedSources <bool>] [-PreferCloudBasedSources <bool>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]

Set-CMDefaultBoundaryGroup -GroupId <int> [-PassThru] [-IncludeCloudBasedSources <bool>] [-PreferCloudBasedSources <bool>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]

Set-CMDefaultBoundaryGroup -Name <string> [-PassThru] [-IncludeCloudBasedSources <bool>] [-PreferCloudBasedSources <bool>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]

Set-CMDefaultBoundaryGroup [-SiteCode <string>] [-PassThru] [-IncludeCloudBasedSources <bool>] [-PreferCloudBasedSources <bool>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **DisableWildcardHandling**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **ForceWildcardHandling**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **GroupId**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|true    |Named   |false        |



#### **IncludeCloudBasedSources**




|Type    |Required|Position|PipelineInput|
|--------|--------|--------|-------------|
|`[bool]`|false   |Named   |false        |



#### **Name**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |Named   |false        |



#### **PassThru**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **PreferCloudBasedSources**




|Type    |Required|Position|PipelineInput|
|--------|--------|--------|-------------|
|`[bool]`|false   |Named   |false        |



#### **SiteCode**




|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[string]`|false   |Named   |false        |DefaultSiteCode|



#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None




---


### Outputs
* IResultObject#SMS_DefaultBoundaryGroup







---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=Set-CMDefaultBoundaryGroup; CommonParameters=True; parameter=System.Object[]}, @{name=Set-CMDefaultBoundaryGroup; CommonParameters=True; parameter=System.Object[]}, @{name=Set-CMDefaultBoundary…
```
