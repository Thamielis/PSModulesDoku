Get-CMSiteStatusMessage
-----------------------




### Synopsis
Gets site system status messages.



---


### Description

The Get-CMSiteStatusMessage cmdlet gets status messages for one or more Configuration Manager site system components. A status message is a message that a Configuration Manager component generates that contains information about the success, failure, or operation of site system components. Configuration Manager stores status messages in a Configuration Manager site database. You can view status messages in the Status Message Viewer.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get site status messages
```PowerShell
PS XYZ:\> Get-CMSiteStatusMessage -ViewingPeriod "2012/09/03 02:16:10.000" -ComputerName "cmcen-dist02" -Severity Error -SiteCode "CM2"
```
This command gets the site status messages that Configuration Manager receives on or after September 3, 2012 and that have an error severity. Configuration Manager gets the status messages from the Configuration Manager site that has the site code CM2 on the computer named cmcen-dist02.tsqa.contoso.com.


---


### Parameters
#### **Component**








|Type        |Required|Position|PipelineInput|Aliases                                        |
|------------|--------|--------|-------------|-----------------------------------------------|
|`[String[]]`|false   |named   |False        |ComponentName<br/>Components<br/>ComponentNames|



#### **ComputerName**

Specifies the fully qualified domain name (FQDN) of the server that hosts the site system role.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |ComputerNames|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FilterHashtable**








|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MessageId**








|Type       |Required|Position|PipelineInput|Aliases   |
|-----------|--------|--------|-------------|----------|
|`[Int32[]]`|false   |named   |False        |MessageIds|



#### **Module**








|Type        |Required|Position|PipelineInput|Aliases                               |
|------------|--------|--------|-------------|--------------------------------------|
|`[String[]]`|false   |named   |False        |ModuleName<br/>Modules<br/>ModuleNames|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Severity**

Specifies the severity of a status message. The acceptable values for this parameter are:


* All


* Error


* Information


* Warning



Valid Values:

* All
* Error
* Information
* Warning






|Type          |Required|Position|PipelineInput|Aliases   |
|--------------|--------|--------|-------------|----------|
|`[Severity[]]`|false   |named   |False        |Severities|



#### **SiteCode**

Specifies the site code of the Configuration Manager site that hosts the site system role.






|Type        |Required|Position|PipelineInput|Aliases  |
|------------|--------|--------|-------------|---------|
|`[String[]]`|false   |named   |False        |SiteCodes|



#### **StartDateTime**








|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[DateTime]`|false   |named   |False        |ViewingPeriod|





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_StatusMessage


* IResultObject#SMS_StatusMessage






---


### Notes




---


### Syntax
```PowerShell
Get-CMSiteStatusMessage [-Component <String[]>] [-ComputerName <String[]>] [-DisableWildcardHandling] [-FilterHashtable <Hashtable>] [-ForceWildcardHandling] [-MessageId <Int32[]>] [-Module <String[]>] [-PassThru] [-Severity {All | Error | Information | Warning}] [-SiteCode <String[]>] [-StartDateTime <DateTime>] [<CommonParameters>]
```
