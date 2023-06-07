Set-CMManagementPoint
---------------------




### Synopsis
Changes settings for a management point in Configuration Manager.



---


### Description

The Set-CMManagementPoint cmdlet changes settings for a management point in Configuration Manager. A management point is a Configuration Manager site that provides policy and service information to clients and receives configuration data from clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMManagementPoint](Add-CMManagementPoint)



* [Get-CMManagementPoint](Get-CMManagementPoint)



* [Remove-CMManagementPoint](Remove-CMManagementPoint)





---


### Examples
#### Example 1: Change management point settings for site system and site code
```PowerShell
PS XYZ:\> Set-CMManagementPoint -SiteSystemServerName "CMDEV-TEST02.TSQA.CORP.CONTOSO.COM" -SiteCode "CM2" -EnableSSL $False -UseSiteDatabase $True
```
This command changes settings for a management point in a Configuration Manager installation. The command specifies the following information about the management point:


- The new management point appears on the site system named CMDEV-TEST02.TSQA.CONTOSO.COM.


- The site has code CM2.


- The management point queries a site database for information.


- The command enables SSL for the management point.
#### Example 2: Change management point settings for site system and site code, connection type, and database name
```PowerShell
PS XYZ:\> Set-CMManagementPoint -SiteSystemServerName "CMDEV-TEST02.TSQA.CORP.CONTOSO.COM " -SiteCode "CM2" -ClientConnectionType InternetAndIntranet -AllowDevice $True -EnableSSL $True -GenerateAlert $False -UseSiteDatabase $False -SQLServerFqdnName "CMDEV-TEST02.TSQA.CORP.CONTOSO.COM" -SQLServerInstanceName "MSSQLServer" -DatabaseName "ContosoSQL01"
```
This command changes settings for a management point in a Configuration Manager installation. The command specifies the following information about the management point:


- The new management point appears on the site system named CMDEV-TEST02.TSQA.CONTOSO.COM. This name is also the fully qualified domain name for the SQL Server instance named MSSQLServer. - The site has code CM2.


- The management point accepts connections from Internet and intranet clients and from portable devices.


- The management point has the associated database name ContosoSQL01.


- The command enables SSL for the management point.


---


### Parameters
#### **AllowDevice**

Indicates whether the management point supports device clients.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ClientConnectionType**

Specifies the type of the client connection. The acceptable values for this parameter are:


* Internet


* InternetAndIntranet


* Intranet



Valid Values:

* Intranet
* Internet
* InternetAndIntranet






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[ClientConnectionTypes]`|false   |named   |False        |



#### **DatabaseName**

Specifies the name of the site database or site database replica that the management point uses to query for site database information.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableCloudGateway**








|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSsl**

Indicates whether to enable SSL.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateAlert**

Indicates whether the management point generates health alerts.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specifies the management point for which you change values by using a management point object. To obtain a management point object, use the Get-CMManagementPoint (Get-CMManagementPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ManagementPoint|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code of the Configuration Manager site that hosts the site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of the server that hosts the site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **SqlServerFqdn**








|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|false   |named   |False        |SqlServerFqdnName|



#### **SqlServerInstanceName**

Specifies the name of the SQL Server instance that clients use to communicate with the site system.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UseComputerAccount**

Indicates that the management point uses its own computer account instead of a domain user account to access site database information.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UserName**

Specifies a domain user account that the management point uses to access site information.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UseSiteDatabase**

Indicates whether the management point queries a site database instead of a site database replica for information.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Set-CMManagementPoint [-AllowDevice <Boolean>] [-ClientConnectionType {Internet | Intranet | InternetAndIntranet}] [-DatabaseName <String>] [-DisableWildcardHandling] [-EnableCloudGateway <Boolean>] [-EnableSsl <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] -InputObject <IResultObject> [-PassThru] [-SqlServerFqdn <String>] [-SqlServerInstanceName <String>] [-UseComputerAccount] [-UserName <String>] [-UseSiteDatabase <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMManagementPoint [-SiteSystemServerName] <String> [-AllowDevice <Boolean>] [-ClientConnectionType {Internet | Intranet | InternetAndIntranet}] [-DatabaseName <String>] [-DisableWildcardHandling] [-EnableCloudGateway <Boolean>] [-EnableSsl <Boolean>] [-ForceWildcardHandling] [-GenerateAlert <Boolean>] [-PassThru] [-SiteCode <String>] [-SqlServerFqdn <String>] [-SqlServerInstanceName <String>] [-UseComputerAccount] [-UserName <String>] [-UseSiteDatabase <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
