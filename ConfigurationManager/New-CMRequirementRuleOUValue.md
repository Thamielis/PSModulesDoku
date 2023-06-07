New-CMRequirementRuleOUValue
----------------------------




### Synopsis
Create an Active Directory organizational unit (OU) requirement rule for an application deployment type.



---


### Description

Use this cmdlet to create an Active Directory organizational unit (OU) requirement rule for an application deployment type.



After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



For more information, see Deployment type Requirements (/mem/configmgr/apps/deploy-use/create-applications#bkmk_dt-require) and [Create global conditions](/mem/configmgr/apps/deploy-use/create-global-conditions).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
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



* [New-CMRequirementRuleRegistryKeyPermissionValue](New-CMRequirementRuleRegistryKeyPermissionValue)



* [New-CMRequirementRuleScreenResolutionValue](New-CMRequirementRuleScreenResolutionValue)



* [Get-CMGlobalCondition](Get-CMGlobalCondition)



* [Deployment type Requirements](Deployment type Requirements)



* [Create global conditions](Create global conditions)





---


### Examples
#### Example 1: Add a requirement rule for Active Directory OUs
```PowerShell
$myGC = Get-CMGlobalCondition -Name "Organizational unit (OU)"

$ouName1 = "CN=Computers,DC=Contoso,DC=Com"

$ouName2 = "CN=Servers,DC=Contoso,DC=Com"

$ouA = @{"OU"=$ouName1; "IsIncludeSubOU"=$true}

$ouB = @{"OU"=$ouName2; "IsIncludeSubOU"=$false}

$myRule = $myGC | New-CMRequirementRuleOUValue -RuleOperator NoneOf -OU $ouA,$ouB

Set-CMScriptDeploymentType -ApplicationName "Central App" -DeploymentTypeName "Install" -AddRequirement $myRule
```



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

Specify a global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


In most instances, you'll use the default Organizational unit (OU) global condition, for example: `Get-CMGlobalCondition -Name "Organizational unit (OU)"`.






|Type             |Required|Position|PipelineInput |Aliases        |
|-----------------|--------|--------|--------------|---------------|
|`[IResultObject]`|true    |0       |True (ByValue)|GlobalCondition|



#### **OrganizationalUnit**

Specify a hashtable to specify the name of the OU and whether to include child OUs. For example:


`@{"OU"="CN=Computers,DC=Contoso,DC=Com"; "IsIncludeSubOU"=$true}`






|Type           |Required|Position|PipelineInput|Aliases                                                                                                        |
|---------------|--------|--------|-------------|---------------------------------------------------------------------------------------------------------------|
|`[Hashtable[]]`|true    |named   |False        |OrganizationalUnits<br/>OU<br/>OUs<br/>OrganizationalUnitWithSubOUOption<br/>OrganizationalUnitWithSubOUOptions|



#### **RuleOperator**

Specify the operator to compare the device's setting with the expected value.



Valid Values:

* And
* Or
* Other
* IsEquals
* NotEquals
* GreaterThan
* LessThan
* Between
* NotBetween
* GreaterEquals
* LessEquals
* BeginsWith
* NotBeginsWith
* EndsWith
* NotEndsWith
* Contains
* NotContains
* AllOf
* OneOf
* NoneOf
* SetEquals
* SubsetOf
* ExcludesAll






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[RuleExpressionOperator]`|true    |named   |False        |





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
New-CMRequirementRuleOUValue [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -OrganizationalUnit <Hashtable[]> -RuleOperator {OneOf | NoneOf} [<CommonParameters>]
```