New-CMRequirementRuleBooleanValue
---------------------------------




### Synopsis
Create a requirement rule to evaluate a boolean global condition on an application deployment type.



---


### Description

Use this cmdlet to create a requirement rule on an application deployment type that evaluates a boolean global condition. The global condition defines the specific criteria, and this requirement rule evaluates the boolean state of that global condition on the device.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRequirementRuleActiveDirectorySiteValue](New-CMRequirementRuleActiveDirectorySiteValue)



* [New-CMRequirementRuleCMSiteValue](New-CMRequirementRuleCMSiteValue)



* [New-CMRequirementRuleCommonValue](New-CMRequirementRuleCommonValue)



* [New-CMRequirementRuleDeviceOwnershipValue](New-CMRequirementRuleDeviceOwnershipValue)



* [New-CMRequirementRuleExistential](New-CMRequirementRuleExistential)



* [New-CMRequirementRuleExpression](New-CMRequirementRuleExpression)



* [New-CMRequirementRuleFileAttributeValue](New-CMRequirementRuleFileAttributeValue)



* [New-CMRequirementRuleFilePermissionValue](New-CMRequirementRuleFilePermissionValue)



* [New-CMRequirementRuleFreeDiskSpaceValue](New-CMRequirementRuleFreeDiskSpaceValue)



* [New-CMRequirementRuleInputTypeValue](New-CMRequirementRuleInputTypeValue)



* [New-CMRequirementRuleOperatingSystemLanguageValue](New-CMRequirementRuleOperatingSystemLanguageValue)



* [New-CMRequirementRuleOperatingSystemValue](New-CMRequirementRuleOperatingSystemValue)



* [New-CMRequirementRuleOUValue](New-CMRequirementRuleOUValue)



* [New-CMRequirementRuleRegistryKeyPermissionValue](New-CMRequirementRuleRegistryKeyPermissionValue)



* [New-CMRequirementRuleScreenResolutionValue](New-CMRequirementRuleScreenResolutionValue)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Deployment type Requirements](Deployment type Requirements)



* [Create global conditions](Create global conditions)





---


### Examples
#### Example 1: Check for co-managed state
```PowerShell
$myGC = Get-CMGlobalCondition -Name "Co-managed device"
$myRule = New-CMRequirementRuleBooleanValue -GlobalCondition $myGC -Value $true

Set-CMScriptDeploymentType -ApplicationName "Central app" -DeploymentTypeName "Install" -AddRequirement $myRule
```
You can also use this example with the default Primary device global condition, which is the only default User type global condition.


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

Specify a boolean global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


To see the list of available boolean global conditions at the site, use the following PowerShell command:


`Get-CMGlobalCondition | Where-Object DataType -eq "Boolean" | Select-Object LocalizedDisplayName`






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|



#### **Value**

Specify the boolean state that this requirement rule should evaluate the global condition on the device. In other words, if you want to require the global condition to be true on the device, set this parameter to `$true`.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|true    |named   |False        |





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
New-CMRequirementRuleBooleanValue [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -Value <Boolean> [<CommonParameters>]
```
