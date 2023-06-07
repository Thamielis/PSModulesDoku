Add-CMPassiveSite
-----------------




### Synopsis
Use this cmdlet to add a site server in passive mode.



---


### Description

Use this cmdlet to add a site server in passive mode.



---


### Related Links
* [Site server high availability](Site server high availability)





---


### Examples
#### Example 1
```PowerShell
Add-CMPassiveSite -InputObject $SiteSystem -InstallDirectory $InstallPath -SourceFilePathOption CopySourceFileFromActiveSite
```

#### Example 2
```PowerShell
Add-CMPassiveSite -SiteCode $SiteCode -SiteSystemServerName $SiteSystemServerName -InstallDirectory $InstallPath -SourceFilePathOption UseLocalSourceDirectory -LocalSourceDirectory $LocalSourcePath
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



#### **InputObject**

{{ Fill InputObject Description }}






|Type             |Required|Position|PipelineInput |Aliases         |
|-----------------|--------|--------|--------------|----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteSystemServer|



#### **InstallDirectory**

{{ Fill InstallDirectory Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **LocalSourceDirectory**

{{ Fill LocalSourceDirectory Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NetworkSourceDirectory**

{{ Fill NetworkSourceDirectory Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

{{ Fill SiteCode Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteSystemServerName**

{{ Fill SiteSystemServerName Description }}






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |named   |False        |Name<br/>ServerName|



#### **SourceFilePathOption**

{{ Fill SourceFilePathOption Description }}



Valid Values:

* CopySourceFileFromActiveSite
* UseLocalSourceDirectory
* UseNetworkSourceDirectory






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[PassiveSiteSourceFileType]`|true    |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Add-CMPassiveSite [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -InstallDirectory <String> [-LocalSourceDirectory <String>] [-NetworkSourceDirectory <String>] -SourceFilePathOption {CopySourceFileFromActiveSite | UseLocalSourceDirectory | UseNetworkSourceDirectory} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMPassiveSite [-DisableWildcardHandling] [-ForceWildcardHandling] -InstallDirectory <String> [-LocalSourceDirectory <String>] [-NetworkSourceDirectory <String>] -SiteCode <String> -SiteSystemServerName <String> -SourceFilePathOption {CopySourceFileFromActiveSite | UseLocalSourceDirectory | UseNetworkSourceDirectory} [-Confirm] [-WhatIf] [<CommonParameters>]
```
