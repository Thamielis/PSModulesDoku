Get-CMConfigurationPolicy
-------------------------




### Synopsis
Gets a configuration policy.



---


### Description

The Get-CMConfigurationPolicy cmdlet gets a configuration policy.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMConfigurationPolicy](Copy-CMConfigurationPolicy)



* [Remove-CMConfigurationPolicy](Remove-CMConfigurationPolicy)





---


### Examples
#### Example 1: Get a configuration policy by name
```PowerShell
PS XYZ:\> Get-CMConfigurationPolicy -Name "TrustedCACert01" -AsXml
```
This command gets the configuration policy named TrustedCACert01 and displays the output in XML format.
#### Example 2: Get a configuration policy by ID
```PowerShell
PS XYZ:\> Get-CMConfigurationPolicy -Id 16777454 -Fast
```
This command gets the configuration policy with the ID of 16777454 and does not display lazy properties.


---


### Parameters
#### **AsXml**

Specifies that the configuration policy is returned in XML format.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **CategoryInstanceType**

Specifies an array of category instance types.






|Type        |Required|Position|PipelineInput|Aliases              |
|------------|--------|--------|-------------|---------------------|
|`[String[]]`|false   |named   |False        |CategoryInstanceTypes|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not used, this parameter should be specified.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the CI__ID of a configuration policy.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Specifies a configuration policy object.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|false   |0       |True (ByValue)|



#### **Name**

Specifies the name of a configuration policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ConfigurationPolicy


* IResultObject#SMS_ConfigurationPolicy






---


### Notes




---


### Syntax
```PowerShell
Get-CMConfigurationPolicy [-Id] <Int32> [-AsXml] [-CategoryInstanceType <String[]>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationPolicy [[-InputObject] <IResultObject>] [-AsXml] [-CategoryInstanceType <String[]>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMConfigurationPolicy [[-Name] <String>] [-AsXml] [-CategoryInstanceType <String[]>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
