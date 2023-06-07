Get-CMCertificateProfilePfx
---------------------------




### Synopsis
Gets a PFX certificate profile.



---


### Description

The Get-CMCertificateProfilePfx function gets a PFX certificate profile.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMCertificateProfilePfx](New-CMCertificateProfilePfx)



* [Set-CMCertificateProfilePfx](Set-CMCertificateProfilePfx)





---


### Examples
#### Example 1: Get a PFX certificate profile by name
```PowerShell
PS XYZ:\> Get-CMCertificateProfilePfx -Name "Test1"
```
This command gets the PFX certificate profile object named Test1.
#### Example 2: Get a PFX certificate profile by ID
```PowerShell
PS XYZ:\> Get-CMcertificateprofilePfx -Id 16777499
```
This command gets the PFX certificate profile object with the ID of 16777499.


---


### Parameters
#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not used, this parameter should be specified.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the ID of a PFX certificate profile.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specifies the name of a PFX certificate profile.






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
Get-CMCertificateProfilePfx [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMCertificateProfilePfx [-Name] <String> [-Fast] [<CommonParameters>]
```
