New-CMRequirementRuleRegistryKeyPermissionValue
-----------------------------------------------




### Synopsis
Create a requirement rule to verify registry key permissions.



---


### Description

Use this cmdlet to create a requirement rule on an application deployment type that verifies registry key permissions. It requires a custom global condition of data type Registry key .



> [!TIP] > For comparison, if you manually create this requirement rule in the Configuration Manager console, select the following options: > > - Category: Custom > - Condition: Select a custom global condition of data type Registry key > - Rule type: Value > - Property: Permissions After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRegistryAccessControlEntry](New-CMRegistryAccessControlEntry)



* [New-CMRequirementRuleActiveDirectorySiteValue](New-CMRequirementRuleActiveDirectorySiteValue)



* [New-CMRequirementRuleBooleanValue](New-CMRequirementRuleBooleanValue)



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



* [New-CMRequirementRuleScreenResolutionValue](New-CMRequirementRuleScreenResolutionValue)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Deployment type Requirements](Deployment type Requirements)



* [Create global conditions](Create global conditions)





---


### Examples
#### Example 1: Add a requirement rule for registry key permissions
```PowerShell
$myGC = Get-CMGlobalCondition -Name "LOB app registry key"

$userName = "contoso\jqpublic"
$ce = New-CMRegistryAccessControlEntry -GroupOrUserName $userName -AccessOption Allow -Permission Read,Write

$userName2 = "contoso\jdoe"
$ce2 = New-CMRegistryAccessControlEntry -GroupOrUserName $userName2 -AccessOption Allow -Permission Read

$myRule = $myGC | New-CMRequirementRuleRegistryKeyPermissionValue -Exclusive $false -ControlEntry $ce,$ce2

Set-CMScriptDeploymentType -ApplicationName "Central app" -DeploymentTypeName "Install" -AddRequirement $myRule
```



---


### Parameters
#### **ControlEntry**

Specify an array of access control entry objects. An access control entry defines specific permissions for a specific user or group. To get this object, use the New-CMRegistryAccessControlEntry (New-CMRegistryAccessControlEntry.md)cmdlet.






|Type                            |Required|Position|PipelineInput|Aliases                                                                       |
|--------------------------------|--------|--------|-------------|------------------------------------------------------------------------------|
|`[RegistryAccessControlEntry[]]`|true    |named   |False        |ControlEntries<br/>RegistryAccessControlEntry<br/>RegistryAccessControlEntries|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Exclusive**

If this parameter is `$true`, for the rule to be compliant, it needs to exactly match the specified ACE exactly. Any other permissions on the registry key cause the rule to fail.


If set to `$false`, for the rule to be compliant, the specified ACE must exist, and other permissions can exist as well.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a custom global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


To see the list of available Registry key global conditions at the site, use the following PowerShell command:


`Get-CMGlobalCondition | Where-Object DataType -eq "RegistryKey" | Select-Object LocalizedDisplayName`






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|





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
New-CMRequirementRuleRegistryKeyPermissionValue [-InputObject] <IResultObject> -ControlEntry <RegistryAccessControlEntry[]> [-DisableWildcardHandling] [-Exclusive <Boolean>] [-ForceWildcardHandling] [<CommonParameters>]
```
