Set-CMClientSettingClientCache
------------------------------




### Synopsis
Sets a client setting client cache.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **BroadcastPort**








|Type     |Required|Position|PipelineInput|Aliases                       |
|---------|--------|--------|-------------|------------------------------|
|`[Int32]`|false   |named   |False        |PortForInitialNetworkBroadcast|



#### **ConfigureBranchCache**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ConfigureCacheSize**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DownloadPort**








|Type     |Required|Position|PipelineInput|Aliases                       |
|---------|--------|--------|-------------|------------------------------|
|`[Int32]`|false   |named   |False        |PortForContentDownloadFromPeer|



#### **EnableBranchCache**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableHttps**








|Type       |Required|Position|PipelineInput|Aliases                              |
|-----------|--------|--------|-------------|-------------------------------------|
|`[Boolean]`|false   |named   |False        |EnableHttpsForClientPeerCommunication|



#### **EnableSuperPeer**








|Type       |Required|Position|PipelineInput|Aliases                           |
|-----------|--------|--------|-------------|----------------------------------|
|`[Boolean]`|false   |named   |False        |EnableClientInFullOsToShareContent|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **MaxBranchCacheSizePercent**








|Type     |Required|Position|PipelineInput|Aliases                      |
|---------|--------|--------|-------------|-----------------------------|
|`[Int32]`|false   |named   |False        |MaximumBranchCacheSizePercent|



#### **MaxCacheSize**








|Type     |Required|Position|PipelineInput|Aliases           |
|---------|--------|--------|-------------|------------------|
|`[Int32]`|false   |named   |False        |MaximumCacheSizeMb|



#### **MaxCacheSizePercent**








|Type     |Required|Position|PipelineInput|Aliases                |
|---------|--------|--------|-------------|-----------------------|
|`[Int32]`|false   |named   |False        |MaximumCacheSizePercent|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMClientSettingClientCache [-BroadcastPort <Int32>] [-ConfigureBranchCache <Boolean>] [-ConfigureCacheSize <Boolean>] -DefaultSetting [-DisableWildcardHandling] [-DownloadPort <Int32>] [-EnableBranchCache <Boolean>] [-EnableHttps <Boolean>] [-EnableSuperPeer <Boolean>] [-ForceWildcardHandling] [-MaxBranchCacheSizePercent <Int32>] [-MaxCacheSize <Int32>] [-MaxCacheSizePercent <Int32>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingClientCache [-BroadcastPort <Int32>] [-ConfigureBranchCache <Boolean>] [-ConfigureCacheSize <Boolean>] [-DisableWildcardHandling] [-DownloadPort <Int32>] [-EnableBranchCache <Boolean>] [-EnableHttps <Boolean>] [-EnableSuperPeer <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-MaxBranchCacheSizePercent <Int32>] [-MaxCacheSize <Int32>] [-MaxCacheSizePercent <Int32>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingClientCache [-BroadcastPort <Int32>] [-ConfigureBranchCache <Boolean>] [-ConfigureCacheSize <Boolean>] [-DisableWildcardHandling] [-DownloadPort <Int32>] [-EnableBranchCache <Boolean>] [-EnableHttps <Boolean>] [-EnableSuperPeer <Boolean>] [-ForceWildcardHandling] [-MaxBranchCacheSizePercent <Int32>] [-MaxCacheSize <Int32>] [-MaxCacheSizePercent <Int32>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
