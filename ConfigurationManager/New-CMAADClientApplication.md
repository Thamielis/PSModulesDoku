New-CMAADClientApplication
--------------------------




### Synopsis

New-CMAADClientApplication -AppName <string> -InputObject <IResultObject#SMS_AAD_Application_Ex> [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]




---


### Description


---


### Parameters
#### **AppName**




|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[string]`|true    |Named   |false        |ApplicationName|



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



#### **InputObject**




|Type                                    |Required|Position|PipelineInput|Aliases          |
|----------------------------------------|--------|--------|-------------|-----------------|
|`[IResultObject#SMS_AAD_Application_Ex]`|true    |Named   |false        |ServerApplication|



#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
None




---


### Outputs
* IResultObject#SMS_AAD_Application_Ex







---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=New-CMAADClientApplication; CommonParameters=True; parameter=System.Object[]}}
```
