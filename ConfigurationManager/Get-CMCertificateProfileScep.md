Get-CMCertificateProfileScep
----------------------------




### Synopsis
Gets a SCEP certificate profile.



---


### Description

The Get-CMCertificateProfileScep function gets a SCEP certificate profile.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMCertificateProfileScep](New-CMCertificateProfileScep)



* [Set-CMCertificateProfileScep](Set-CMCertificateProfileScep)





---


### Examples
#### Example 1: Get a SCEP certificate profile by ID
```PowerShell
PS XYZ:\> Get-CMcertificateProfileScep -Id 16777476
```
This command gets the SCEP certificate profile with the ID of 16777476.
#### Example 2: Get a SCEP certificate profile by name
```PowerShell
PS XYZ:\> Get-CMCertificateProfileScep -Name "TestSCEPProfile"
```
This command gets the SCEP certificate profile with the name TestSCEPProfile.


---


### Parameters
#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not used, this parameter should be specified.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the CI_ID of a SCEP certificate profile.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specifies the name of a SCEP certificate profile.






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
Get-CMCertificateProfileScep [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMCertificateProfileScep [-Name] <String> [-Fast] [<CommonParameters>]
```
