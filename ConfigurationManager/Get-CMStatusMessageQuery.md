Get-CMStatusMessageQuery
------------------------




### Synopsis
Gets Configuration Manager status message queries or displays messages.



---


### Description

The Get-CMStatusMessageQuery cmdlet gets Configuration Manager status message queries. Status message queries return status messages from a Configuration Manager site database. You can use this cmdlet with the ShowMessages parameter to display messages found by this query.



You can use this cmdlet to get queries to use with the Set-CMStatusMessageQuery (Set-CMStatusMessageQuery.md) cmdlet or the [Remove-CMStatusMessageQuery](Remove-CMStatusMessageQuery.md)cmdlet.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMStatusMessageQuery](New-CMStatusMessageQuery)



* [Remove-CMStatusMessageQuery](Remove-CMStatusMessageQuery)



* [Set-CMStatusMessageQuery](Set-CMStatusMessageQuery)





---


### Examples
#### Example 1: Get a query that has a specified name
```PowerShell
PS XYZ:\> Get-CMStatusMessageQuery -Name "Clients That Received a Specific Deployed Program"
```
This command gets a query that has a specified name.
#### Example 2: Show messages for a query
```PowerShell
PS XYZ:\> Get-CMStatusMessageQuery -Id "SMS551" -ShowMessages
```
This command shows messages found by a query that has an ID of SMS551.


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



#### **Id**

Specifies an ID of a status message query.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |QueryId|



#### **Name**

Specifies a name of a status message query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ShowMessage**








|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[Switch]`|false   |named   |False        |ShowMessages|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_Query


* IResultObject#SMS_Query






---


### Notes




---


### Syntax
```PowerShell
Get-CMStatusMessageQuery [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-PassThru] [-ShowMessage] [<CommonParameters>]
```
```PowerShell
Get-CMStatusMessageQuery [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-PassThru] [-ShowMessage] [<CommonParameters>]
```
