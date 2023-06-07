Add-CMManagementPoint
---------------------




### Synopsis
Adds a management point to Configuration Manager.



---


### Description

The Add-CMManagementPoint cmdlet adds a management point to Configuration Manager. A management point is a Configuration Manager site system role that provides policy and service information to clients and receives configuration data from clients.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMManagementPoint](Get-CMManagementPoint)



* [Remove-CMManagementPoint](Remove-CMManagementPoint)



* [Set-CMManagementPoint](Set-CMManagementPoint)





---


### Examples
#### Example 1: Add a management point
```PowerShell
PS XYZ:\>Add-CMManagementPoint -SiteSystemServerName "CMDEV-TEST02.TSQA.CONTOSO.COM" -SiteCode "CM2" -ClientConnectionType InternetAndIntranet -AllowDevice $True -GenerateAlert -SQLServerFqdnName "CMDEV-TEST02.TSQA.CONTOSO.COM" -SQLServerInstanceName "MSSQLServer" -DatabaseName "test" -UserName "TSQA\MPAdmin" -Verbose
```
This command adds a management point to a Configuration Manager installation. The command specifies the following information about the management point:


- The new management point appears on the site system named CMDEV-TEST02.TSQA.CONTOSO.COM. This name is also the fully qualified domain name for the SQL Server instance named MSSQLServer. - The site has code CM2.


- The management point accepts connections from internet and intranet clients and from portable devices.


- The management point has the associated database name Test.


- The management point uses the domain user account for the user named TSQA\MPAdmin.


- The cmdlet displays all messages that the addition operation generates.


---


### Parameters
#### **AllowDevice**

Indicates that the management point supports device clients.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClientConnectionType**

Specifies the type of the client connection. Valid values are:


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



#### **CommunicationType**





Valid Values:

* Http
* Https






|Type                         |Required|Position|PipelineInput|Aliases                |
|-----------------------------|--------|--------|-------------|-----------------------|
|`[ComputerCommunicationType]`|false   |named   |False        |ClientCommunicationType|



#### **ConnectionAccountUserName**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|false   |named   |False        |UserName|



#### **DatabaseName**

Specifies the name of the site database or site database replica that the management point uses to query for site database information.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableCloudGateway**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableSsl**

Indicates that the cmdlet enables SSL for the management point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateAlert**

Indicates that Configuration Manager generates an alert when the management point is not healthy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specifies the input to this cmdlet. You can use this parameter, or you can pipe the input to this cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |0       |True (ByValue)|SiteServer|



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
|`[String]`|true    |named   |False        |SqlServerFqdnName|



#### **SqlServerInstanceName**

Specifies the name of the SQL Server instance that clients use to communicate with the site system.






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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Add-CMManagementPoint [-SiteSystemServerName] <String> [-AllowDevice] [-ClientConnectionType {Internet | Intranet | InternetAndIntranet}] [-CommunicationType {Http | Https}] [-ConnectionAccountUserName <String>] -DatabaseName <String> [-DisableWildcardHandling] [-EnableCloudGateway] [-EnableSsl] [-ForceWildcardHandling] [-GenerateAlert] [-SiteCode <String>] -SqlServerFqdn <String> [-SqlServerInstanceName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMManagementPoint [-InputObject] <IResultObject> [-AllowDevice] [-ClientConnectionType {Internet | Intranet | InternetAndIntranet}] [-CommunicationType {Http | Https}] [-ConnectionAccountUserName <String>] -DatabaseName <String> [-DisableWildcardHandling] [-EnableCloudGateway] [-EnableSsl] [-ForceWildcardHandling] [-GenerateAlert] -SqlServerFqdn <String> [-SqlServerInstanceName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMManagementPoint [-InputObject] <IResultObject> [-AllowDevice] [-ClientConnectionType {Internet | Intranet | InternetAndIntranet}] [-CommunicationType {Http | Https}] [-ConnectionAccountUserName <String>] [-DisableWildcardHandling] [-EnableCloudGateway] [-EnableSsl] [-ForceWildcardHandling] [-GenerateAlert] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMManagementPoint [-SiteSystemServerName] <String> [-AllowDevice] [-ClientConnectionType {Internet | Intranet | InternetAndIntranet}] [-CommunicationType {Http | Https}] [-ConnectionAccountUserName <String>] [-DisableWildcardHandling] [-EnableCloudGateway] [-EnableSsl] [-ForceWildcardHandling] [-GenerateAlert] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
