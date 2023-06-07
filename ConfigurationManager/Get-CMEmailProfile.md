Get-CMEmailProfile
------------------




### Synopsis
Gets an email profile.



---


### Description

The Get-CMEmailProfile function gets an Exchange ActiveSync email profile.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMEmailProfile](New-CMEmailProfile)



* [Set-CMEmailProfile](Set-CMEmailProfile)





---


### Examples
#### Example 1: Get an email profile by name
```PowerShell
PS XYZ:\> Get-CMEmailProfile -Name "EmailProfile1"
```
This command gets the Exchange ActiveSync email profile with the name EmailProfile1.
#### Example 2: Get an email profile by ID
```PowerShell
PS XYZ:\> Get-CMEmailProfile -ID 16795653
```
This command gets the Exchange ActiveSync email profile with the CI_ID of 16795653.
#### Example 3: Get all email profiles
```PowerShell
PS XYZ:\> Get-CMEmailProfile -Fast
```
This command gets all Exchange ActiveSync email profiles. The command does not return lazy properties.


---


### Parameters
#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not used, this parameter should be specified.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the CI_ID of an email profile.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **Name**

Specifies the name of an email profile.






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
Get-CMEmailProfile [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMEmailProfile [-Name] <String> [-Fast] [<CommonParameters>]
```
