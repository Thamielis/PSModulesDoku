Approve-CMApprovalRequest
-------------------------




### Synopsis
Approves a request to allow the installation of an application.



---


### Description

The Approve-CMApprovalRequest cmdlet approves a request from a user to install an application. You can specify an approval request by application name, application ID, or by user. You can also use the Get-CMApprovalRequest (Get-CMApprovalRequest.md)cmdlet to view approval requests.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Deny-CMApprovalRequest](Deny-CMApprovalRequest)



* [Get-CMApprovalRequest](Get-CMApprovalRequest)





---


### Examples
#### Example 1: Approve a request for a specific application
```PowerShell
PS XYZ:\>Approve-CMApprovalRequest -Id "ScopeId_2A11048C-917A-4C11-9E77-7DCC402F30EC/Application_426dfca1-0cc0-4aa3-85f8-3cd1b184d494/1"
```
This command approves a request from a user to install an application specified by its ID.
#### Example 2: Approve a request for a specific user
```PowerShell
PS XYZ:\>Approve-CMApprovalRequest -Application "Test" -User "tsqa\davidchew" -Comment "Request approved."
```
This command approves a request for an application named Test for the specified user. The command includes a comment.
#### Example 3: Approve a request by using a variable
```PowerShell
PS XYZ:\> $Approval = Get-CMApprovalRequest -Id "ScopeId_2A11048C-917A-4C11-9E77-7DCC402F30EC/Application_d047e945-d6af-46f4-910f-ed36c880ae06/1"
PS XYZ:\> Approve-CMApprovalRequest -InputObject $Approval -Comment "Request approved."
```
The first command gets an approval request for a specified application ID and stores it in the variable `$Approval`.


The second command accepts the request stored in `$Approval`. The command includes a comment.


---


### Parameters
#### **ApplicationName**

Specifies an array of names of applications.






|Type        |Required|Position|PipelineInput|Aliases             |
|------------|--------|--------|-------------|--------------------|
|`[String[]]`|true    |named   |False        |Application<br/>Name|



#### **Comment**

Specifies a comment about the approval of the request.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |Comments|



#### **DisableWildcardHandling**

DisableWildcardHandling treats wildcard characters as literal character values. Don't combine with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

ForceWildcardHandling processes wildcard characters and may lead to unexpected behavior (not recommended). Don't combine with DisableWildcardHandling .






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



#### **InstallActionBehavior**

Specifies when to install the application, either right away or during non-business hours.



Valid Values:

* InstallNow
* InstallNonBusinessHours






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[ActionBehavior]`|false   |named   |False        |



#### **RequestGuid**

Specifies the request ID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **User**

Specifies the name of a user who submitted the approval request. Use the format domain\user .






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
Approve-CMApprovalRequest -ApplicationName <String[]> [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InstallActionBehavior {InstallNow | InstallNonBusinessHours}] -User <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Approve-CMApprovalRequest [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String[]> [-InstallActionBehavior {InstallNow | InstallNonBusinessHours}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Approve-CMApprovalRequest [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallActionBehavior {InstallNow | InstallNonBusinessHours}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Approve-CMApprovalRequest [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InstallActionBehavior {InstallNow | InstallNonBusinessHours}] -RequestGuid <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
