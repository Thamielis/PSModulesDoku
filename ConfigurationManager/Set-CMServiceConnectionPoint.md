Set-CMServiceConnectionPoint
----------------------------




### Synopsis
Sets a service connection point.



---


### Description

The Set-CMServiceConnectionPoint updates the settings of a connection service point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMServiceConnectionPoint](Add-CMServiceConnectionPoint)



* [Get-CMServiceConnectionPoint](Get-CMServiceConnectionPoint)



* [Remove-CMServiceConnectionPoint](Remove-CMServiceConnectionPoint)





---


### Examples
#### Example 1: Set a service connection point
```PowerShell
PS XYZ:\> Set-CMServiceConnectionPoint -SiteSystemServerName "SiteSystemServer01.Contoso.com" -SiteCode PS1 -Mode Offline
```
This command sets the mode for the site system server named SiteSystemServer01.Contoso.com to offline.
#### Example 2: Set a service connection point by using a variable
```PowerShell
PS XYZ:\> $Server = Get-CMServiceConnectionPoint -SiteCode PS1 -SiteSystemServerName "SiteSystemServer02.Contoso.com"
PS XYZ:\> Set-CMServiceConnectionPoint -InputObject $Server -Mode Offline
```
The first command gets the site system server object named SiteSystemServer02.Contoso.com with the site code PS1 and stores the object in the $Server variable.


The second command sets the mode for the site system server stored in $Server to offline.
#### Example 3: Set a service connection point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMServiceConnectionPoint -SiteCode PS1 -SiteSystemServerName "SiteSystemServer03.Contoso.com" | Set-CMServiceConnectionPoint -Mode Offline
```
This command gets the site system server object named SiteSystemServer03.Contoso.com with the site code PS1 and uses the pipeline operator to pass the object to Set-CMServiceConnectionPoint , which sets the mode for the server object to offline.


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






|Type             |Required|Position|PipelineInput |Aliases               |
|-----------------|--------|--------|--------------|----------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ServiceConnectionPoint|



#### **Mode**

Specifies a mode for the service connection point. Valid values are:


* Online


* Offline



Valid Values:

* Online
* Offline






|Type                          |Required|Position|PipelineInput|
|------------------------------|--------|--------|-------------|
|`[ServiceConnectionPointMode]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a site system server that hosts the service connection point role.






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
Set-CMServiceConnectionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Mode {Online | Offline}] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMServiceConnectionPoint [-SiteSystemServerName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Mode {Online | Offline}] [-PassThru] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
