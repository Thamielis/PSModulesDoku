Get-CMAutoDeploymentRuleDeployment
----------------------------------




### Synopsis
Gets the deployments associated with an automatic deployment rule.



---


### Description

The Get-CMAutoDeploymentRuleDeployment cmdlet gets the deployments associated with an automatic deployment rule.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAutoDeploymentRuleDeployment](New-CMAutoDeploymentRuleDeployment)



* [Remove-CMAutoDeploymentRuleDeployment](Remove-CMAutoDeploymentRuleDeployment)



* [Set-CMAutoDeploymentRuleDeployment](Set-CMAutoDeploymentRuleDeployment)



* [Get-CMSoftwareUpdateAutoDeploymentRule](Get-CMSoftwareUpdateAutoDeploymentRule)





---


### Examples
#### Example 1: Get a deployment object for an automatic deployment rule
```PowerShell
PS XYZ:\>Get-CMAutoDeploymentRuleDeployment -Name "AutoDeploymentRule01"
```
This command gets the deployment object for the automatic deployment rule named AutoDeploymentRule01.
#### Example 2: Get a deployment object for an automatic deployment rule using the pipeline
```PowerShell
PS XYZ:\>Get-CMSoftwareUpdateAutoDeploymentRule -Name "TestRule01" | Get-CMAutoDeploymentRuleDeployment
```
This command gets the automatic deployment rule object named TestRule01 and uses the pipeline operator to pass the object to Get-CMAutoDeploymentRuleDeployment , which gets the deployments associated with the automatic deployment rule named TestRule01.


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

Specifies the ID of the automatic deployment rule associated with the deployment.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|true    |0       |False        |AutoDeploymentID|



#### **InputObject**

Specifies the auto deployment rule object associated with the deployment. To obtain an auto deployment rule object, use the Get-CMSoftwareUpdateAutoDeploymentRule (Get-CMSoftwareUpdateAutoDeploymentRule.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases           |
|-----------------|--------|--------|--------------|------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|AutoDeploymentRule|



#### **Name**

Specifies the name of the automatic deployment rule associated with the deployment.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|false   |0       |False        |AutoDeploymentName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_AdrDeploymentSettings






---


### Notes




---


### Syntax
```PowerShell
Get-CMAutoDeploymentRuleDeployment [-Id] <Int32> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMAutoDeploymentRuleDeployment [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMAutoDeploymentRuleDeployment [[-Name] <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
