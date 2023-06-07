Set-CMComplianceRuleFileFolderPermission
----------------------------------------




### Synopsis
Sets a compliance rule file folder permission.



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
#### **AddExpectedPermission**





Valid Values:

* None
* ListFolderContentsOrReadData
* CreateFilesOrWriteData
* CreateFoldersOrAppendData
* ReadExtendedAttributes
* WriteExtendedAttributes
* TraverseFolderOrExecuteFile
* DeleteSubfoldersAndFiles
* ReadAttributes
* WriteAttributes
* Write
* Delete
* ReadPermissions
* Read
* Execute
* ChangePermissions
* TakeOwnership
* FullControl






|Type                       |Required|Position|PipelineInput|Aliases            |
|---------------------------|--------|--------|-------------|-------------------|
|`[FileSystemPermissions[]]`|false   |named   |False        |ExpectedPermissions|



#### **AddExpectedUserAccess**








|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



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








|Type             |Required|Position|PipelineInput |Aliases          |
|-----------------|--------|--------|--------------|-----------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ConfigurationItem|



#### **IsExclusive**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **NewRuleName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **NoncomplianceSeverity**





Valid Values:

* None
* Informational
* Warning
* Critical
* CriticalWithEvent






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[NoncomplianceSeverity]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Remediate**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **RemoveExpectedUserAccess**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **ReportNoncompliance**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Rule**








|Type    |Required|Position|PipelineInput |
|--------|--------|--------|--------------|
|`[Rule]`|true    |named   |True (ByValue)|



#### **RuleDescription**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RuleName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



Microsoft.SystemsManagementServer.DesiredConfigurationManagement.Rules.Rule





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMComplianceRuleFileFolderPermission [-AddExpectedPermission {None | ListFolderContentsOrReadData | CreateFilesOrWriteData | CreateFoldersOrAppendData | ReadExtendedAttributes | WriteExtendedAttributes | TraverseFolderOrExecuteFile | DeleteSubfoldersAndFiles | ReadAttributes | WriteAttributes | Write | Delete | ReadPermissions | Read | Execute | ChangePermissions | TakeOwnership | FullControl}] [-AddExpectedUserAccess <Hashtable>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsExclusive <Boolean>] [-NewRuleName <String>] [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-PassThru] [-Remediate <Boolean>] [-RemoveExpectedUserAccess <String[]>] [-ReportNoncompliance <Boolean>] [-RuleDescription <String>] -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMComplianceRuleFileFolderPermission [-AddExpectedPermission {None | ListFolderContentsOrReadData | CreateFilesOrWriteData | CreateFoldersOrAppendData | ReadExtendedAttributes | WriteExtendedAttributes | TraverseFolderOrExecuteFile | DeleteSubfoldersAndFiles | ReadAttributes | WriteAttributes | Write | Delete | ReadPermissions | Read | Execute | ChangePermissions | TakeOwnership | FullControl}] [-AddExpectedUserAccess <Hashtable>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsExclusive <Boolean>] [-NewRuleName <String>] [-NoncomplianceSeverity {None | Informational | Warning | Critical | CriticalWithEvent}] [-PassThru] [-Remediate <Boolean>] [-RemoveExpectedUserAccess <String[]>] [-ReportNoncompliance <Boolean>] -Rule <Rule> [-RuleDescription <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```