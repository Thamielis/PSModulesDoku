Get-CMBaseline
--------------




### Synopsis
Get a configuration baseline.



---


### Description

Use this cmdlet to get one or more configuration baselines. Use configuration baselines to evaluate compliance of a device. For more information, see Get started with compliance settings in Configuration Manager (/mem/configmgr/compliance/get-started/get-started-with-compliance-settings).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Disable-CMBaseline](Disable-CMBaseline)



* [Enable-CMBaseline](Enable-CMBaseline)



* [Export-CMBaseline](Export-CMBaseline)



* [Import-CMBaseline](Import-CMBaseline)



* [New-CMBaseline](New-CMBaseline)



* [Remove-CMBaseline](Remove-CMBaseline)



* [Set-CMBaseline](Set-CMBaseline)



* [Get-CMBaselineSummarizationSchedule](Get-CMBaselineSummarizationSchedule)



* [Get started with compliance settings in Configuration Manager](Get started with compliance settings in Configuration Manager)





---


### Examples
#### Example 1: Get configuration baselines by using a parent baseline name
```PowerShell
Get-CMBaseline -ParentBaselineName "ParentBaselineContoso01"
```

#### Example 2: Get configuration baselines by using a parent baseline ID
```PowerShell
Get-CMBaseline -ParentBaselineId "16777357"
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of a configuration baseline. This value is the same as the CI_ID attribute. For example, `33554545`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specify the name of a configuration baseline. This value is the same as the LocalizedDisplayName attribute.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|false   |0       |False        |LocalizedDisplayName|



#### **ParentBaseline**

Specify a configuration baseline object that's a parent baseline.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |0       |True (ByValue)|



#### **ParentBaselineId**

Specify the ID of a parent configuration baseline.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|true    |named   |False        |



#### **ParentBaselineName**

Specify the name of a parent configuration baseline.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ConfigurationBaselineInfo


* IResultObject#SMS_ConfigurationBaselineInfo


* IResultObject[]#SMS_ConfigurationItem


* IResultObject#SMS_ConfigurationItem


* IResultObject[]#SMS_SoftwareUpdate


* IResultObject#SMS_SoftwareUpdate






---


### Notes
For more information on these return objects and their properties, see the following articles:

- SMS_ConfigurationBaselineInfo server WMI class (/mem/configmgr/develop/reference/compliance/sms_configurationbaselineinfo-server-wmi-class)- SMS_ConfigurationItem server WMI class (/mem/configmgr/develop/reference/compliance/sms_configurationitem-server-wmi-class)- SMS_SoftwareUpdate server WMI class (/mem/configmgr/develop/reference/sum/sms_softwareupdate-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMBaseline [-Id] <Int32> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBaseline [[-Name] <String>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBaseline [-ParentBaseline] <IResultObject> [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMBaseline [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -ParentBaselineId <Int32> [<CommonParameters>]
```
```PowerShell
Get-CMBaseline [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] -ParentBaselineName <String> [<CommonParameters>]
```
