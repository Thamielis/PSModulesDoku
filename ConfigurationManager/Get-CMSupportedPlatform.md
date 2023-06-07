Get-CMSupportedPlatform
-----------------------




### Synopsis
Get a supported platform.



---


### Description

Get a supported platform. Configuration Manager maintains a list of supported platforms, which applies to various objects such as compliance policies, package programs, and task sequences. These objects only apply to devices with the specified platforms.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMComplianceSupportedPlatform](Set-CMComplianceSupportedPlatform)





---


### Examples
#### Example 1: Get all Windows 10 platforms by name
```PowerShell
Get-CMSupportedPlatform -Name "*Windows*10*" -Fast
```

#### Example 2: Get all Windows 8 platforms by version
```PowerShell
Get-CMSupportedPlatform -Fast -MinVersion "6.2*"
```

#### Example 3: Get all platforms
```PowerShell
Get-CMSupportedPlatform -Fast | Select-Object DisplayText
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MaxVersion**

Filter the list of supported platforms by a specific maximum OS version. For example, `"10.00.99999.9999"`.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |OSMaxVersion|



#### **MinVersion**

Filter the list of supported platforms by a specific maximum OS version. For example, `"10.00.0000.0"`.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |OSMinVersion|



#### **Name**

Filter the list of supported platforms by name. You can specify a specific platform name, for example, `"All Windows 10 (64-bit)"`. You can also use wildcard characters:


* `*`: Multiple characters


* `?`: Single character




For example, `" Windows 10*"` for all Windows 10 platforms.







|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |DisplayText|



#### **Platform**

Filter the list of supported platforms by OS platform. For example, `"I386"` or `"x64"`.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |OSPlatform|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_SupportedPlatforms


* IResultObject#SMS_SupportedPlatforms






---


### Notes




---


### Syntax
```PowerShell
Get-CMSupportedPlatform [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-MaxVersion <String>] [-MinVersion <String>] [-Name <String>] [-Platform <String>] [<CommonParameters>]
```
