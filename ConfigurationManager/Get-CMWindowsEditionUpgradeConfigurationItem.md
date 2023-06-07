Get-CMWindowsEditionUpgradeConfigurationItem
--------------------------------------------




### Synopsis
Get a Windows 10 edition upgrade policy.



---


### Description

Get a Windows 10 edition upgrade policy.



---


### Related Links
* [New-CMWindows10EditionUpgrade](New-CMWindows10EditionUpgrade)



* [Remove-CMWindows10EditionUpgrade](Remove-CMWindows10EditionUpgrade)



* [Set-CMWindows10EditionUpgrade](Set-CMWindows10EditionUpgrade)



* [Upgrade Windows devices to a new edition with Configuration Manager](Upgrade Windows devices to a new edition with Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMWindowsEditionUpgradeConfigurationItem -Name "Enterprise"
```



---


### Parameters
#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the Windows 10 edition upgrade policy. This ID is the CI ID of the policy, for example: `552481`.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specify the name of the Windows 10 edition upgrade policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMWindowsEditionUpgradeConfigurationItem [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMWindowsEditionUpgradeConfigurationItem [-Name] <String> [-Fast] [<CommonParameters>]
```
