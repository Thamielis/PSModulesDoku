Set-CMClientSettingRemoteTool
-----------------------------




### Synopsis
Sets a client setting remote tool.



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
#### **AccessLevel**





Valid Values:

* NoAccess
* ViewOnly
* FullControl






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[AccessLevelType]`|false   |named   |False        |



#### **AllowClientChange**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowPermittedViewer**








|Type       |Required|Position|PipelineInput|Aliases                             |
|-----------|--------|--------|-------------|------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowPermittedViewersToRemoteDesktop|



#### **AllowUnattendedComputer**








|Type       |Required|Position|PipelineInput|Aliases                               |
|-----------|--------|--------|-------------|--------------------------------------|
|`[Boolean]`|false   |named   |False        |AllowRemoteControlOfUnattendedComputer|



#### **AudibleSignal**





Valid Values:

* PlayNoSound
* PlaySoundAtBeginAndEnd
* PlaySoundRepeatedly






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[AudibleSignalType]`|false   |named   |False        |



#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FirewallExceptionProfile**





Valid Values:

* Disabled
* Public
* Private
* Domain






|Type                              |Required|Position|PipelineInput|
|----------------------------------|--------|--------|-------------|
|`[FirewallExceptionProfileType[]]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GrantPermissionToLocalAdministrator**








|Type       |Required|Position|PipelineInput|Aliases                                         |
|-----------|--------|--------|-------------|------------------------------------------------|
|`[Boolean]`|false   |named   |False        |GrantRemoteControlPermissionToLocalAdministrator|



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ManageRemoteDesktopSetting**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ManageSolicitedRemoteAssistance**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ManageUnsolicitedRemoteAssistance**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PermittedViewer**








|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|false   |named   |False        |PermittedViewers|



#### **PromptUserForClipboardPermission**








|Type       |Required|Position|PipelineInput|Aliases                               |
|-----------|--------|--------|-------------|--------------------------------------|
|`[Boolean]`|false   |named   |False        |PromptUserForClipboardAccessPermission|



#### **PromptUserForPermission**








|Type       |Required|Position|PipelineInput|Aliases                             |
|-----------|--------|--------|-------------|------------------------------------|
|`[Boolean]`|false   |named   |False        |PromptUserForRemoteControlPermission|



#### **RemoteAssistanceAccessLevel**





Valid Values:

* None
* RemoteViewing
* FullControl






|Type                               |Required|Position|PipelineInput|
|-----------------------------------|--------|--------|-------------|
|`[RemoteAssistanceAccessLevelType]`|false   |named   |False        |



#### **RequireAuthentication**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ShowNotificationIconOnTaskbar**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ShowSessionConnectionBar**








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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMClientSettingRemoteTool [-AccessLevel {NoAccess | ViewOnly | FullControl}] [-AllowClientChange <Boolean>] [-AllowPermittedViewer <Boolean>] [-AllowUnattendedComputer <Boolean>] [-AudibleSignal {PlayNoSound | PlaySoundAtBeginAndEnd | PlaySoundRepeatedly}] -DefaultSetting [-DisableWildcardHandling] [-FirewallExceptionProfile {Disabled | Public | Private | Domain}] [-ForceWildcardHandling] [-GrantPermissionToLocalAdministrator <Boolean>] [-ManageRemoteDesktopSetting <Boolean>] [-ManageSolicitedRemoteAssistance <Boolean>] [-ManageUnsolicitedRemoteAssistance <Boolean>] [-PassThru] [-PermittedViewer <String[]>] [-PromptUserForClipboardPermission <Boolean>] [-PromptUserForPermission <Boolean>] [-RemoteAssistanceAccessLevel {None | RemoteViewing | FullControl}] [-RequireAuthentication <Boolean>] [-ShowNotificationIconOnTaskbar <Boolean>] [-ShowSessionConnectionBar <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingRemoteTool [-AccessLevel {NoAccess | ViewOnly | FullControl}] [-AllowClientChange <Boolean>] [-AllowPermittedViewer <Boolean>] [-AllowUnattendedComputer <Boolean>] [-AudibleSignal {PlayNoSound | PlaySoundAtBeginAndEnd | PlaySoundRepeatedly}] [-DisableWildcardHandling] [-FirewallExceptionProfile {Disabled | Public | Private | Domain}] [-ForceWildcardHandling] [-GrantPermissionToLocalAdministrator <Boolean>] -InputObject <IResultObject> [-ManageRemoteDesktopSetting <Boolean>] [-ManageSolicitedRemoteAssistance <Boolean>] [-ManageUnsolicitedRemoteAssistance <Boolean>] [-PassThru] [-PermittedViewer <String[]>] [-PromptUserForClipboardPermission <Boolean>] [-PromptUserForPermission <Boolean>] [-RemoteAssistanceAccessLevel {None | RemoteViewing | FullControl}] [-RequireAuthentication <Boolean>] [-ShowNotificationIconOnTaskbar <Boolean>] [-ShowSessionConnectionBar <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingRemoteTool [-AccessLevel {NoAccess | ViewOnly | FullControl}] [-AllowClientChange <Boolean>] [-AllowPermittedViewer <Boolean>] [-AllowUnattendedComputer <Boolean>] [-AudibleSignal {PlayNoSound | PlaySoundAtBeginAndEnd | PlaySoundRepeatedly}] [-DisableWildcardHandling] [-FirewallExceptionProfile {Disabled | Public | Private | Domain}] [-ForceWildcardHandling] [-GrantPermissionToLocalAdministrator <Boolean>] [-ManageRemoteDesktopSetting <Boolean>] [-ManageSolicitedRemoteAssistance <Boolean>] [-ManageUnsolicitedRemoteAssistance <Boolean>] -Name <String> [-PassThru] [-PermittedViewer <String[]>] [-PromptUserForClipboardPermission <Boolean>] [-PromptUserForPermission <Boolean>] [-RemoteAssistanceAccessLevel {None | RemoteViewing | FullControl}] [-RequireAuthentication <Boolean>] [-ShowNotificationIconOnTaskbar <Boolean>] [-ShowSessionConnectionBar <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
