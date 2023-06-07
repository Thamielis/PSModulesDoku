Get-CMAccessLicense
-------------------




### Synopsis
Gets license usage information.



---


### Description

The Get-CMAccessLicense cmdlet gets license usage information for the servers and clients in the scope of Configuration Manager. This cmdlet returns a list of features able to be licensed and a list of unique users and devices per licensable feature.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Get all licensable features for all servers and clients
```PowerShell
PS XYZ:\> Get-CMAccessLicense -License
```
This command gets all licensable features for all servers and clients within the scope of Configuration Manager.
#### Example 2: Get the unique users, devices, and license-specific unique ID for a specified license
```PowerShell
PS XYZ:\> Get-CMAccessLicense -LicenseName ConfigMgr_2012_EndPointClient
```
This command gets the unique users, devices, and license-specific IDs for the license named ConfigMgr_2012_EndPointClient.


---


### Parameters
#### **Count**

Indicates that the cmdlet returns a count of unique users and devices for the specified licensable feature.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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



#### **License**

Indicates that the cmdlet gets all licensable features for all of the servers and clients within the scope of Configuration Manager. You can specify the name of the license that is returned for the LicenseName parameter to obtain the unique users and devices for that specific license.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **LicenseName**

Specifies the name of a licensable feature. If specified, the cmdlet gets only the unique users and devices for the specified license name. The acceptable values for this parameter are:


* ConfigMgr_2012_CoreServer


* ConfigMgr_2012_CoreClient


* ConfigMgr_2012_EndpointClient



Valid Values:

* ConfigMgr_2012_CoreServer
* ConfigMgr_2012_CoreClient
* ConfigMgr_2012_EndpointClient






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMAccessLicense -Count [-DisableWildcardHandling] [-ForceWildcardHandling] -LicenseName {ConfigMgr_2012_CoreServer | ConfigMgr_2012_CoreClient | ConfigMgr_2012_EndpointClient} [<CommonParameters>]
```
```PowerShell
Get-CMAccessLicense [-DisableWildcardHandling] [-ForceWildcardHandling] [-License] [<CommonParameters>]
```
```PowerShell
Get-CMAccessLicense [-DisableWildcardHandling] [-ForceWildcardHandling] -LicenseName {ConfigMgr_2012_CoreServer | ConfigMgr_2012_CoreClient | ConfigMgr_2012_EndpointClient} [<CommonParameters>]
```
