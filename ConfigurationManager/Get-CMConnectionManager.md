Get-CMConnectionManager
-----------------------




### Synopsis
Gets the Connection Manager instance associated with the currently-connected site server.



---


### Description

The Get-CMConnectionManager cmdlet gets the Connection Manager instance associated with the currently-connected site server. The Connection Manager instance can be used for directly communicating with the SMS Provider.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get a Connection Manager instance
```PowerShell
PS ABC:\> Get-CMConnectionManager
```
This command gets the connection manager instance associated with the currently-connected site server.


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





---


### Inputs
None





---


### Outputs
* Microsoft.ConfigurationManagement.ManagementProvider.ConnectionManagerBase






---


### Notes




---


### Syntax
```PowerShell
Get-CMConnectionManager [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
