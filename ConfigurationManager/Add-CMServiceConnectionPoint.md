Add-CMServiceConnectionPoint
----------------------------




### Synopsis
Adds a service connection point to a site system server.



---


### Description

The Add-CMServiceconnectionPoint cmdlet adds a service connection point role to a site system server. This connects Configuration Manager to Microsoft cloud services and enables you to add a Microsoft Intune subscription and to update your Configuration Manager installation.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMServiceConnectionPoint](Get-CMServiceConnectionPoint)



* [Remove-CMServiceConnectionPoint](Remove-CMServiceConnectionPoint)



* [Set-CMServiceConnectionPoint](Set-CMServiceConnectionPoint)





---


### Examples
#### Example 1: Add a service connection point
```PowerShell
PS XYZ:\> Add-CMServiceConnectionPoint -SiteSystemServerName "TestServer01.Contoso.com" -SiteCode PS1 -Mode Online
```
This command adds the service connection point site system role to the site system server named TestServer01.Contoso.com and the site code PS1. The command sets the mode to online.
#### Example 2: Add a service connection point by using a variable
```PowerShell
PS XYZ:\> $Server = Get-CMSiteSystemServer -SiteCode PS1 -SiteSystemServerName "TestServer02.Contoso.com"
PS XYZ:\> Add-CMServiceConnectionPoint -InputObject $Server -Mode Online
```
The first command gets the site system server object named TestServer02.Contoso.com with the site code PS1 and stores the object in the $Server variable.


The second command adds the service connection point site system role to the site system server stored in $server and sets the mode to online.
#### Example 3: Add a service connection point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMSiteSystemServer -SiteCode PS1 -SiteSystemServerName "TestServer03.Contoso.com" | Add-CMServiceConnectionPoint -Mode Online
```
This command gets the site system server object named TestServer03.Contoso.com with the site code PS1 and uses the pipeline operator to pass the object to Add-CMServiceConnectionPoint , which adds the service connection point site system role to the site system server object and sets the mode to online.


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



#### **InputObject**

Specifies a service connection point object. To obtain a service connection point object, use the Get-CMServiceConnectionPoint cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **Mode**

Specifies a mode for the service connection point. Valid values are:


* Online


* Offline



Valid Values:

* Online
* Offline






|Type                          |Required|Position|PipelineInput|
|------------------------------|--------|--------|-------------|
|`[ServiceConnectionPointMode]`|true    |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a site system server to host the service connection point role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



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
Add-CMServiceConnectionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -Mode {Online | Offline} [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMServiceConnectionPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -Mode {Online | Offline} [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
