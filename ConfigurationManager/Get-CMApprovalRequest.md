Get-CMApprovalRequest
---------------------




### Synopsis
Gets an approval request to allow the installation of a Configuration Manager application.



---


### Description

The Get-CMApprovalRequest cmdlet gets a request from a user to install a Configuration Manager application. You can specify an approval request by application name, application ID, or by user name.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMApprovalRequest](Approve-CMApprovalRequest)



* [Deny-CMApprovalRequest](Deny-CMApprovalRequest)





---


### Examples
#### Example 1: Get all approval requests
```PowerShell
PS XYZ:\> Get-CMApprovalRequest
```
This command gets all pending Configuration Manager approval requests.
#### Example 2: Get an approval request by using an application ID
```PowerShell
PS XYZ:\> Get-CMApprovalRequest -Id "1635223"
```
This command gets an approval request for an application with the specified ID.
#### Example 3: Get an approval request for a specific user
```PowerShell
PS XYZ:\> Get-CMApprovalRequest -Application "HelloWorld" -User "tsqa\davidchew"
```
This command gets an approval request for the application HelloWorld for a specified user.


---


### Parameters
#### **ApplicationName**

Specifies an array of names of applications.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|false   |named   |False        |Application|



#### **CurrentState**





Valid Values:

* Unknown
* Requested
* Canceled
* Denied
* Approved






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[RequestState]`|false   |named   |False        |



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

Specifies an array of IDs of applications.






|Type        |Required|Position|PipelineInput|Aliases   |
|------------|--------|--------|-------------|----------|
|`[String[]]`|true    |named   |False        |CIUniqueId|



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **ModelName**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RequestGuid**

Sepcifies the request ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **User**

Specifies an array of user names of persons who submitted the approval request. Use the format domain\user.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_UserApplicationRequest


* IResultObject#SMS_UserApplicationRequest






---


### Notes




---


### Syntax
```PowerShell
Get-CMApprovalRequest [-ApplicationName <String[]>] [-CurrentState {Unknown | Requested | Canceled | Denied | Approved}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-User <String>] [<CommonParameters>]
```
```PowerShell
Get-CMApprovalRequest [-CurrentState {Unknown | Requested | Canceled | Denied | Approved}] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [-User <String>] [<CommonParameters>]
```
```PowerShell
Get-CMApprovalRequest [-CurrentState {Unknown | Requested | Canceled | Denied | Approved}] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-User <String>] [<CommonParameters>]
```
```PowerShell
Get-CMApprovalRequest [-CurrentState {Unknown | Requested | Canceled | Denied | Approved}] [-DisableWildcardHandling] [-ForceWildcardHandling] -ModelName <String> [-User <String>] [<CommonParameters>]
```
```PowerShell
Get-CMApprovalRequest [-CurrentState {Unknown | Requested | Canceled | Denied | Approved}] [-DisableWildcardHandling] [-ForceWildcardHandling] -RequestGuid <String> [-User <String>] [<CommonParameters>]
```
