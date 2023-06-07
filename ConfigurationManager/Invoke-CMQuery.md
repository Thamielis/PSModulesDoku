Invoke-CMQuery
--------------




### Synopsis
Run a Configuration Manager query.



---


### Description

Use this cmdlet to run a query in the Configuration Manager site. Configuration Manager queries define a WMI Query Language (WQL) expression to get information from the site database based on the criteria you provide. WQL is similar to SQL, but still goes through the SMS Provider instead of directly to the database. So WQL still abides by your role-based access configuration.



When you run a query, the site processes the WQL expression, and returns the results in PowerShell. Depending upon the structure of the WQL statement, the format of the results may vary.



Queries can return most types of Configuration Manager objects, which include computers, sites, collections, applications, and inventory data. For more information, see Introduction to queries in Configuration Manager (/mem/configmgr/core/servers/manage/introduction-to-queries).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMQuery](Export-CMQuery)



* [Get-CMQuery](Get-CMQuery)



* [Import-CMQuery](Import-CMQuery)



* [New-CMQuery](New-CMQuery)



* [Remove-CMQuery](Remove-CMQuery)



* [Set-CMQuery](Set-CMQuery)



* [Introduction to queries in Configuration Manager](Introduction to queries in Configuration Manager)





---


### Examples
#### Example 1: View and run a default query
```PowerShell
PS XYZ:\> Get-CMQuery -Id "SMS012"

SmsProviderObjectPath          : SMS_Query.QueryID="SMS012"
Comments                       : This site and all its subsites in the ConfigMgr hierarchy
Expression                     : SELECT SiteCode, SiteName, Version, ServerName FROM sms_siteandsubsites
LimitToCollectionID            :
LocalizedCategoryInstanceNames : {}
Name                           : This Site and its Subsites
QueryID                        : SMS012
ResultAliasNames               : {sms_siteandsubsites, sms_siteandsubsites, sms_siteandsubsites, sms_siteandsubsites}
ResultColumnsNames             : {sms_siteandsubsites.SiteCode, sms_siteandsubsites.SiteName,
                                 sms_siteandsubsites.Version, sms_siteandsubsites.ServerName}
TargetClassName                : sms_siteandsubsites

PS XYZ:\> Invoke-CMQuery -Id "SMS012"

SmsProviderObjectPath : SMS_SiteAndSubsites.SiteCode="XYZ"
ServerName            : cmserver.contoso.com
SiteCode              : XYZ
SiteName              : Production primary site
Version               : 5.00.9043.1000
```
Notice in the output of the Get-CMQuery cmdlet that the WQL Expression is simple. It selects four attributes from a single class.


Then notice how the output of the Invoke-CMQuery cmdlet is a simple table.
#### Example 2: View and run a complex query
```PowerShell
PS XYZ:\> Get-CMQuery -Id "XYZ00002"

SmsProviderObjectPath          : SMS_Query.QueryID="XYZ00002"
Comments                       :
Expression                     : select SMS_R_System.Name, SMS_R_System.LastLogonUserName,
                                 SMS_G_System_OPERATING_SYSTEM.Caption from SMS_R_System inner join
                                 SMS_G_System_OPERATING_SYSTEM on SMS_G_System_OPERATING_SYSTEM.ResourceID =
                                 SMS_R_System.ResourceId where SMS_G_System_OPERATING_SYSTEM.Caption like "Microsoft Windows Server 2012%"
LimitToCollectionID            : XYZ0025F
LocalizedCategoryInstanceNames : {}
Name                           : Server 2016
QueryID                        : XYZ00002
ResultAliasNames               : {SMS_R_System, SMS_R_System, SMS_G_System_OPERATING_SYSTEM}
ResultColumnsNames             : {SMS_R_System.Name, SMS_R_System.LastLogonUserName,
                                 SMS_G_System_OPERATING_SYSTEM.Caption}
TargetClassName                : SMS_R_System

PS XYZ:\> Invoke-CMQuery -Id "XYZ00002"


SmsProviderObjectPath         : __GENERIC
SMS_G_System_OPERATING_SYSTEM :
                                instance of SMS_G_System_OPERATING_SYSTEM
                                {
                                        Caption = "Microsoft Windows Server 2012 R2 Datacenter";
                                };

SMS_R_System                  :
                                instance of SMS_R_System
                                {
                                        LastLogonUserName = "jqpublic";
                                        Name = "millcreek01";
                                };
```
This query has a more complex Expression that joins two classes. The result of the query is then more complex.


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

Specify the ID of the query to run. For example, `"XYZ00006"`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |QueryId|



#### **InputObject**

Specify a query object to run. To get this object, use the Get-CMQuery (Get-CMQuery.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **LimitToCollectionId**

If the query is configured to prompt for the limiting collection, use this parameter to specify a collection ID. If the query's LimitToCollectionID property is `<Prompt>`, and you don't include this parameter when you run the query, the cmdlet fails.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Name**

Specify the name of the query to run.






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
Invoke-CMQuery [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-LimitToCollectionId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMQuery [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-LimitToCollectionId <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMQuery [-DisableWildcardHandling] [-ForceWildcardHandling] [-LimitToCollectionId <String>] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
