Set-CMRemoteConnectionProfileConfigurationItem
----------------------------------------------




### Synopsis
Modifies a remote connection profile.



---


### Description

The Set-CMRemoteConnectionProfileConfigurationItem cmdlet modifies a remote connection profile. Client computers use remote connection profiles to remotely connect to computers from outside the domain or over the Internet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRemoteConnectionProfileConfigurationItem](New-CMRemoteConnectionProfileConfigurationItem)





---


### Examples
#### Example 1: Modify a remote connection profile configuration item
```PowerShell
PS XYZ:\> Set-CMRemoteConnectionProfileConfigurationItem -ID "AAA0004D" -EnablePrimaryUsers $False -EnableTSConnection $False -EnableTSFirewallRule $False
```
This command modifies the remote connection profile configuration item with the ID AAA0004D. In this case, the EnablePrimaryUsers , EnableTSConnection , and EnableTSFirewallRule properties are all set to $False.


---


### Parameters
#### **Description**

Specifies a description for a remote connection profile.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |named   |False        |LocalizedDescription|



#### **Digest**








|Type                 |Required|Position|PipelineInput |
|---------------------|--------|--------|--------------|
|`[ConfigurationItem]`|false   |named   |True (ByValue)|



#### **DigestPath**








|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[String]`|false   |named   |False        |DesiredConfigurationDigestPath|



#### **DigestXml**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type       |Required|Position|PipelineInput|Aliases                 |
|-----------|--------|--------|-------------|------------------------|
|`[Boolean]`|false   |named   |False        |EnableConnectionSettings|



#### **EnableNla**

Indicates whether to allow connections only from computers that run Remote Desktop by using Network Level Authentication.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePrimaryUser**








|Type       |Required|Position|PipelineInput|Aliases           |
|-----------|--------|--------|-------------|------------------|
|`[Boolean]`|false   |named   |False        |EnablePrimaryUsers|



#### **EnableTSConnection**

Indicates whether to allow remote connections to client computers. If you specify a value for this parameter, you must specify values for the EnablePrimaryUsers and EnableTSFirewallRule parameters.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableTSFirewallRule**

Indicates whether to allow Windows Firewall exceptions for connections in Windows domains and on private networks. If you specify a value for this parameter, you must specify values for the EnablePrimaryUsers and EnableTSConnections parameters.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs for remote connection profiles.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a remote connection profile object. To obtain a remote connection profile, use the Get-CMRemoteConnectionProfileConfigurationItem cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **Name**

Specifies an array of names of remote connection profiles.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **NewName**

Specifies the new name for the remote connection profile.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RDGatewayServer**

Specifies the host name and port of the Remote Desktop gateway server, for example, Boston.gateway.Contoso.com:8080.






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



Microsoft.ConfigurationManagement.DesiredConfigurationManagement.ConfigurationItem





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMRemoteConnectionProfileConfigurationItem [-Id] <Int32> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableNla <Boolean>] [-EnablePrimaryUser <Boolean>] [-EnableTSConnection <Boolean>] [-EnableTSFirewallRule <Boolean>] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RDGatewayServer <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMRemoteConnectionProfileConfigurationItem [-InputObject] <IResultObject> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableNla <Boolean>] [-EnablePrimaryUser <Boolean>] [-EnableTSConnection <Boolean>] [-EnableTSFirewallRule <Boolean>] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RDGatewayServer <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMRemoteConnectionProfileConfigurationItem [-Name] <String> [-Description <String>] [-Digest <ConfigurationItem>] [-DigestPath <String>] [-DigestXml <String>] [-DisableWildcardHandling] [-Enable <Boolean>] [-EnableNla <Boolean>] [-EnablePrimaryUser <Boolean>] [-EnableTSConnection <Boolean>] [-EnableTSFirewallRule <Boolean>] [-ForceWildcardHandling] [-NewName <String>] [-PassThru] [-RDGatewayServer <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
