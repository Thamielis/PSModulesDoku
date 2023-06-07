Install-CMClient
----------------




### Synopsis
Installs a Configuration Manager client.



---


### Description

The Install-CMClient cmdlet installs a client for Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Set-CMClientStatusSetting](Set-CMClientStatusSetting)



* [Update-CMClientStatus](Update-CMClientStatus)



* [Get-CMDevice](Get-CMDevice)



* [Get-CMBaseline](Get-CMBaseline)





---


### Examples
#### Example 1: Install a client
```PowerShell
PS XYZ:\>Install-CMClient -Name "RemoteClient05" -SiteCode "CM1" -AlwaysInstallClient $True -IncludeDomainController $True
```
This command installs the client named RemoteClient05 on the Configuration Manager site that has the site code CM1.


---


### Parameters
#### **AlwaysInstallClient**

Indicates whether Configuration Manager always installs the client.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CollectionId**

Specifies the ID of the collection to which the client belongs.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeviceId**

Specifies the ID for the device to which Configuration Manager installs the client.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeviceName**

Specifies the name of the device to which Configuration Manager installs the client.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceReinstall**

Indicates whether the cmdlet reinstalls the client.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IncludeDomainController**

Indicates whether Configuration Manager authenticates and authorizes the client by using the clients domain controller.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specifies a Configuration Manager client object. You can get a Configuration Manager client object by using the Get-CMBaseline (Get-CMBaseline.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases              |
|-----------------|--------|--------|--------------|---------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection<br/>Device|



#### **Name**

Specifies the name of a Configuration Manager client.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specifies the site code for the Configuration Manager site that hosts this site system role.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Install-CMClient [-AlwaysInstallClient <Boolean>] -CollectionId <String> [-DisableWildcardHandling] [-ForceReinstall <Boolean>] [-ForceWildcardHandling] [-IncludeDomainController <Boolean>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Install-CMClient [-AlwaysInstallClient <Boolean>] -DeviceId <String> [-DisableWildcardHandling] [-ForceReinstall <Boolean>] [-ForceWildcardHandling] [-IncludeDomainController <Boolean>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Install-CMClient [-AlwaysInstallClient <Boolean>] -DeviceName <String> [-DisableWildcardHandling] [-ForceReinstall <Boolean>] [-ForceWildcardHandling] [-IncludeDomainController <Boolean>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Install-CMClient [-AlwaysInstallClient <Boolean>] [-DisableWildcardHandling] [-ForceReinstall <Boolean>] [-ForceWildcardHandling] [-IncludeDomainController <Boolean>] -InputObject <IResultObject> [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Install-CMClient [-AlwaysInstallClient <Boolean>] [-DisableWildcardHandling] [-ForceReinstall <Boolean>] [-ForceWildcardHandling] [-IncludeDomainController <Boolean>] -Name <String> [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
