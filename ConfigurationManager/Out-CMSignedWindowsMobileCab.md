Out-CMSignedWindowsMobileCab
----------------------------




### Synopsis
Signs a Windows Mobile CAB file.



---


### Description

The Out-CMSignedWindowsMobileCab cmdlet signs a Windows Mobile cabinet file and places the signed file in the specified location.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1: Sign a Windows Mobile CAB file
```PowerShell
PS XYZ:\>Out-CMSignedWindowsMobileCab -ContentLocation "\\Server1\Applications\Cab\Test.CAB" -PfxFilePath "\\Server1\Applications\sign\sign3.pfx" -PfxPassword $SecureString -OutputPath "\\Server1\Applications\Cab\TestSigned.CAB"
```
This command signs the Windows Mobile CAB file named Test.CAB using the provided certificate and password. The signed CAB file is placed in the specified output path.


---


### Parameters
#### **ContentLocation**

Specifies the path of the content. The site system server requires permissions to read the content files.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



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



#### **OutputPath**

Specifies the output file path for the signed Windows Mobile CAB file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PfxFilePath**

Specifies the path of a PFX file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PfxPassword**

Specifies the PFX password as a secured string.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|true    |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


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
Out-CMSignedWindowsMobileCab [-ContentLocation] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -OutputPath <String> -PfxFilePath <String> -PfxPassword <SecureString> [-Confirm] [-WhatIf] [<CommonParameters>]
```
