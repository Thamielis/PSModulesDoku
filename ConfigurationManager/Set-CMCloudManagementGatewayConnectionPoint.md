Set-CMCloudManagementGatewayConnectionPoint
-------------------------------------------




### Synopsis
Configure a cloud management gateway connection point.



---


### Description

Use this cmdlet to configure a cloud management gateway (CMG) connection point role on a site system server.



For more information on CMG, see CMG Overview (/mem/configmgr/core/clients/manage/cmg/overview).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMCloudManagementGatewayConnectionPoint](Add-CMCloudManagementGatewayConnectionPoint)



* [Get-CMCloudManagementGatewayConnectionPoint](Get-CMCloudManagementGatewayConnectionPoint)



* [Remove-CMCloudManagementGatewayConnectionPoint](Remove-CMCloudManagementGatewayConnectionPoint)





---


### Examples
#### Example 1
```PowerShell
Set-CMCloudManagementGatewayConnectionPoint -CloudManagementGatewayName "GraniteFalls-new.cloudapp.net" -SiteSystemServerName "cmgcp.contoso.com"
```



---


### Parameters
#### **CloudManagementGatewayName**

Specify the service name of the CMG in Azure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specify a CMG connection point object to configure. To get the object, use the Get-CMCloudManagementGatewayConnectionPoint (Get-CMCloudManagementGatewayConnectionPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases               |
|-----------------|--------|--------|--------------|----------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|GatewayConnectionPoint|



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteCode**

Specify the site code for this site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the FQDN of the server as the target for this role.






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
Set-CMCloudManagementGatewayConnectionPoint -CloudManagementGatewayName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCloudManagementGatewayConnectionPoint [-SiteSystemServerName] <String> -CloudManagementGatewayName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
