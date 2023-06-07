Invoke-CMReport
---------------




### Synopsis
Invokes a report about data and operations in Configuration Manager.



---


### Description

The Invoke-CMReport cmdlet invokes a Microsoft SQL Server Reporting Services report that displays information about data and operations in Configuration Manager. The reporting services point is a site system role that you install on a server that runs Microsoft SQL Server Reporting Services.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Invoke a report
```PowerShell
PS XYZ:\>Invoke-CMReport -ReportPath "/Reports/Data" -SiteCode "CM4"
```
This command invokes a report by using a report path and a site code.


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



#### **OutputFormat**

Specifies an output format in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ReportParameter**

Specifies report parameters as key-value pairs.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



#### **ReportPath**

Specifies the path to a folder where reports are stored.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specifies a site code in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SrsServerName**

Specifies a name of a Microsoft SQL Server Reporting Services server.






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
None





---


### Outputs
* [Diagnostics.Process](https://learn.microsoft.com/en-us/dotnet/api/System.Diagnostics.Process)






---


### Notes




---


### Syntax
```PowerShell
Invoke-CMReport [-DisableWildcardHandling] [-ForceWildcardHandling] [-OutputFormat <String>] [-PassThru] [-ReportParameter <Hashtable>] -ReportPath <String> [-SiteCode <String>] [-SrsServerName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
