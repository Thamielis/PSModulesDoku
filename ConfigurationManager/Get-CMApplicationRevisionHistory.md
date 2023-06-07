Get-CMApplicationRevisionHistory
--------------------------------




### Synopsis
Gets a Configuration Manager object that represents the revision history for an application.



---


### Description

The Get-CMApplicationRevisionHistory cmdlet gets a Configuration Manager object that represents the revision history for an application. When you revise an application or a deployment type contained in an application, Configuration Manager creates a new revision of the application. You can use the revision history to display each revision made to an application, view the properties of a revision, restore a previous revision, or delete an old revision.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMApplicationRevisionHistory](Remove-CMApplicationRevisionHistory)



* [Restore-CMApplicationRevisionHistory](Restore-CMApplicationRevisionHistory)





---


### Examples
#### Example 1: Get the revision history for an application
```PowerShell
PS XYZ:\> Get-CMApplicationRevisionHistory -Name "MSXML 6.0 Parser"
```
This command gets the application revision history named MSXML 6.0 Parser.


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

Specifies an array of IDs of application revision histories.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies an application object. To obtain an application object, use the Get-CMApplication (Get-CMApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases    |
|-----------------|--------|--------|--------------|-----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Application|



#### **Name**

Specifies an array of names of application revision histories.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **Revision**

Specifies the version number of an application revision.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[UInt32]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_Application


* IResultObject#SMS_Application






---


### Notes




---


### Syntax
```PowerShell
Get-CMApplicationRevisionHistory [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-Revision <UInt32>] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationRevisionHistory [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Revision <UInt32>] [<CommonParameters>]
```
```PowerShell
Get-CMApplicationRevisionHistory [-Name] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Revision <UInt32>] [<CommonParameters>]
```
