Invoke-CMWmiMethod
------------------




### Synopsis
Calls a WMI method.



---


### Description

The Invoke-CMWmiMethod cmdlet calls Windows Management Instrumentation (WMI) methods provided in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [Invoke-CMWmiQuery](Invoke-CMWmiQuery)





---


### Examples
#### Example 1: Call a WMI method by using the pipeline
```PowerShell
PS XYZ:\> Get-CMBoundaryGroup -Name "Boundary1" | Invoke-CMWmiMethod -MethodName "AddBoundary" -Parameter @{BoundaryId = 16777217,16777218}
```
This command uses a WMI method to add an array of boundaries to a boundary group.


The command gets the boundary group object named Boundary1 and uses the pipeline operator to pass the object to Invoke-CMWmiMethod . Invoke-CMWmiMethod calls the WMI method AddBoundary which adds the boundaries specified by their IDs to boundary group Boundary1.


---


### Parameters
#### **ClassName**

Specifies the name of the WMI class that contains the static method you want to call.






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



#### **InputObject**

Specifies a management object or a Configuration Management object.






|Type             |Required|Position|PipelineInput |Aliases |
|-----------------|--------|--------|--------------|--------|
|`[IResultObject]`|true    |0       |True (ByValue)|Instance|



#### **MethodName**

Specifies the name of the method to invoke. This parameter is mandatory and cannot be null or empty.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Parameter**

Specifies the name of the property and the value for the method. The name and value must be in a name/value pair. The name/value pair is passed on the command line as a hash table.






|Type         |Required|Position|PipelineInput|Aliases   |
|-------------|--------|--------|-------------|----------|
|`[Hashtable]`|false   |named   |False        |Parameters|



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
Invoke-CMWmiMethod [-ClassName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -MethodName <String> [-Parameter <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMWmiMethod [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] -MethodName <String> [-Parameter <Hashtable>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
