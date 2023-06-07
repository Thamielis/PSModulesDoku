Deny-CMApprovalRequest
----------------------




### Synopsis
Denies a request to allow the installation of an application.



---


### Description

The Deny-CMApprovalRequest cmdlet denies a request from a user to install an application. You can specify an approval request by application name, application ID, or by user. You can use the Get-CMApprovalRequest (Get-CMApprovalRequest.md)cmdlet to view approval requests.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMApprovalRequest](Approve-CMApprovalRequest)



* [Get-CMApprovalRequest](Get-CMApprovalRequest)





---


### Examples
#### Example 1: Deny a request by application ID
```PowerShell
PS XYZ:\>Deny-CMApprovalRequest -Id "ScopeId_2A11048C-917A-4C11-9E77-7DCC402F30EC/Application_426dfca1-0cc0-4aa3-85f8-3cd1b184d494/1" -Comment "All requests for this application are denied."
```
This command denies a request for an application that has the specified ID. The command includes a comment.
#### Example 2: Deny a request from a specific user
```PowerShell
PS XYZ:\>Deny-CMApprovalRequest -Application "Test" -User "tsqa\davidchew"
```
This command denies a request for an application named Test for the specified user.
#### Example 3: Deny a request by using a variable
```PowerShell
PS XYZ:\> $Approval = Get-CMApprovalRequest -Id "ScopeId_2A11048C-917A-4C11-9E77-7DCC402F30EC/Application_426dfca1-0cc0-4aa3-85f8-3cd1b184d494/1"
PS XYZ:\> Deny-CMApprovalRequest -InputObject $Approval -Comment "Request denied."
```
The first command gets an approval request for a specified application ID and stores it in the $Approval variable.


The second command denies the request stored in $Approval. The command includes a comment.


---


### Parameters
#### **ApplicationName**

Specifies an array of names of applications.






|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[String[]]`|true    |named   |False        |Application<br/>Name|



#### **Comment**

Specifies a comment about the denial of the request.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



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

Specifies an approval request object. To obtain an approval request object, use the Get-CMApprovalRequest (Get-CMApprovalRequest.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **RequestGuid**

Specifies the request ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **User**

Specifies an array of user names of persons who submitted the approval request. Use the format domain\user.






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





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Deny-CMApprovalRequest -ApplicationName <String[]> [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -User <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Deny-CMApprovalRequest [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Deny-CMApprovalRequest [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Deny-CMApprovalRequest [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -RequestGuid <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
