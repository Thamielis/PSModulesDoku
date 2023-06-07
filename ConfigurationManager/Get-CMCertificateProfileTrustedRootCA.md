Get-CMCertificateProfileTrustedRootCA
-------------------------------------




### Synopsis
Gets a trusted CA certificate profile.



---


### Description

The Get-CMCertificateProfileTrustedRootCA function gets a trusted CA certificate profile.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMCertificateProfileTrustedRootCA](New-CMCertificateProfileTrustedRootCA)



* [Set-CMCertificateProfileTrustedRootCA](Set-CMCertificateProfileTrustedRootCA)





---


### Examples
#### Example 1: Get a trusted CA certificate profile by ID
```PowerShell
PS XYZ:\> Get-CMCertificateProfileTrustedRootCA -Id 16777479
```
This command gets the trusted CA certificate profile with the ID 16777479.
#### Example 2: Get a trusted CA certificate profile by name
```PowerShell
PS XYZ:\> Get-CMCertificateProfileTrustedRootCA -Name "Test01" -Fast
```
This command gets the trusted CA certificate profile named Test01, but does not return lazy properties.


---


### Parameters
#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not used, this parameter should be specified.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the ID of a trusted CA certificate profile.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specifies the name of a trusted CA certificate profile.






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
Get-CMCertificateProfileTrustedRootCA [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMCertificateProfileTrustedRootCA [-Name] <String> [-Fast] [<CommonParameters>]
```
