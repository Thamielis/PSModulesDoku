New-CMRequirementRuleFileAttributeValue
---------------------------------------




### Synopsis
Create a requirement rule to verify file attributes.



---


### Description

Use this cmdlet to create a requirement rule on an application deployment type that verifies file attributes. For example, Hidden or Read only . It requires a custom global condition of data type File .



> [!TIP] > For comparison, if you manually create this requirement rule in the Configuration Manager console, select the following options: > > - Category: Custom > - Condition: Select a custom global condition of data type File > - Rule type: Value > - Property: Attributes After you use this cmdlet, then use one of the Add- or Set- cmdlets for deployment types. Pass this requirement rule object to either the AddRequirement or RemoveRequirement parameters.



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
#### Example 1
```PowerShell
$myGC = Get-CMGlobalCondition -Name "pagefile.sys"
$myRule = New-CMRequirementRuleFileAttributeValue -GlobalCondition $myGC -FileArchive On -FileHidden On -FileSystem On

Set-CMScriptDeploymentType -ApplicationName "Central app" -DeploymentTypeName "Install" -AddRequirement $myRule
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FileArchive**

Set this parameter to `On` to verify the Archive bit on the file. By default, the condition doesn't verify the attribute.



Valid Values:

* On
* Off
* DoNotVerify






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[AttributeVerificationOption]`|false   |named   |False        |



#### **FileCompressed**

Set this parameter to `On` to verify the Compressed bit on the file. By default, the condition doesn't verify the attribute.



Valid Values:

* On
* Off
* DoNotVerify






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[AttributeVerificationOption]`|false   |named   |False        |



#### **FileEncrypted**

Set this parameter to `On` to verify the Encrypted bit on the file. By default, the condition doesn't verify the attribute.



Valid Values:

* On
* Off
* DoNotVerify






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[AttributeVerificationOption]`|false   |named   |False        |



#### **FileHidden**

Set this parameter to `On` to verify the Hidden bit on the file. By default, the condition doesn't verify the attribute.



Valid Values:

* On
* Off
* DoNotVerify






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[AttributeVerificationOption]`|false   |named   |False        |



#### **FileReadOnly**

Set this parameter to `On` to verify the Read only bit on the file. By default, the condition doesn't verify the attribute.



Valid Values:

* On
* Off
* DoNotVerify






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[AttributeVerificationOption]`|false   |named   |False        |



#### **FileSystem**

Set this parameter to `On` to verify the System bit on the file. By default, the condition doesn't verify the attribute.



Valid Values:

* On
* Off
* DoNotVerify






|Type                           |Required|Position|PipelineInput|
|-------------------------------|--------|--------|-------------|
|`[AttributeVerificationOption]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a custom global condition object to use as the basis for this requirement rule. To get this object, use the Get-CMGlobalCondition (Get-CMGlobalCondition.md)cmdlet.


To see the list of available File global conditions at the site, use the following PowerShell command:


`Get-CMGlobalCondition | Where-Object DataType -eq "File" | Select-Object LocalizedDisplayName`






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
New-CMRequirementRuleFileAttributeValue [-InputObject] <IResultObject> [-DisableWildcardHandling] [-FileArchive {On | Off | DoNotVerify}] [-FileCompressed {On | Off | DoNotVerify}] [-FileEncrypted {On | Off | DoNotVerify}] [-FileHidden {On | Off | DoNotVerify}] [-FileReadOnly {On | Off | DoNotVerify}] [-FileSystem {On | Off | DoNotVerify}] [-ForceWildcardHandling] [<CommonParameters>]
```
