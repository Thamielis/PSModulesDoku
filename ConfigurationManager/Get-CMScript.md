Get-CMScript
------------




### Synopsis
Get a PowerShell script in Configuration Manager.



---


### Description

Use this cmdlet to get a Configuration Manager PowerShell script. These scripts are integrated and managed in Configuration Manager. For more information, see Create and run PowerShell scripts from the Configuration Manager console (/mem/configmgr/apps/deploy-use/create-deploy-scripts).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMScript](Approve-CMScript)



* [Deny-CMScript](Deny-CMScript)



* [Invoke-CMScript](Invoke-CMScript)



* [New-CMScript](New-CMScript)



* [Remove-CMScript](Remove-CMScript)



* [Set-CMScript](Set-CMScript)



* [Create and run PowerShell scripts from the Configuration Manager console](Create and run PowerShell scripts from the Configuration Manager console)





---


### Examples
#### Example 1: Get all unapproved scripts
```PowerShell
Get-CMScript -Fast | Where-Object { -not $_.ApprovalState }
```

#### Example 2: Get scripts by using name
```PowerShell
Get-CMScript -ScriptName "D*"
```

#### Example 3: Get scripts from a specific author
```PowerShell
Get-CMScript -Fast -Author "*jqpublic" | Select-Object ScriptName, ApprovalState, LastUpdateTime
```



---


### Parameters
#### **Author**

Specify the author of the script to get. For example, `contoso\jqpublic`.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **ScriptGuid**

Applies to version 2010 and later. Specify the GUID of a script to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ScriptName**

Specify a script name to get.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Scripts


* IResultObject#SMS_Scripts






---


### Notes
This cmdlet returns an object for the SMS_Scripts WMI class.



---


### Syntax
```PowerShell
Get-CMScript [-Author <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -ScriptGuid <String> [<CommonParameters>]
```
```PowerShell
Get-CMScript [-Author <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-ScriptName <String>] [<CommonParameters>]
```
