Copy-CMConfigurationPolicy
--------------------------




### Synopsis
Copies a configuration policy.



---


### Description

The Copy-CMConfigurationPolicy copies a configuration policy. A configuration policy can be a client authentication  certificate profile configuration item, a wireless profile configuration item, or others. See the Alias section for additional policy items that you can use this cmdlet to copy.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMConfigurationPolicy](Get-CMConfigurationPolicy)



* [Remove-CMConfigurationPolicy](Remove-CMConfigurationPolicy)





---


### Examples
#### Example 1: Copy a configuration policy by using the pipeline
```PowerShell
PS XYZ:\> Get-CMConfigurationPolicy -Name "TrustedCACert01" -Fast | Copy-CMConfigurationPolicy -NewName "TrustedCACert01_copy"
```
This command gets the configuration policy object named TrustedCACert01 and uses the pipeline operator to pass the object to Copy-CMConfiguratinPolicy , which creates a copy of the policy and names it TrustedCACert01_copy.
#### Example 2: Copy a configuration policy by ID
```PowerShell
PS XYZ:\> Copy-CMConfigurationPolicy -Id 16777454 -NewName "EmailProfile1_copy"
```
This command makes a copy of the configuration policy with the ID of 16777454 and names it EmailProfile1_copy.


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



#### **Id**

Specifies the CI_ID of a configuration policy.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|true    |0       |False        |CIId<br/>CI_ID|



#### **InputObject**

Gets a configuration policy object. To obtain a configuration policy object, use the Get-CMConfigurationPolicy cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|ConfigurationPolicy|



#### **Name**

Specifies the name of a configuration policy.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |0       |False        |LocalizedDisplayName|



#### **NewName**

Specifies a name for the copy of the configuration policy.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Copy-CMConfigurationPolicy [-Id] <Int32> [-NewName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMConfigurationPolicy [-InputObject] <IResultObject> [-NewName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMConfigurationPolicy [-Name] <String> [-NewName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
