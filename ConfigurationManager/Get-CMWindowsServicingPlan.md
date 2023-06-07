Get-CMWindowsServicingPlan
--------------------------




### Synopsis
Gets a Windows 10 servicing plan.



---


### Description

The Get-CMWindowsServicingPlan cmdlet gets a Windows 10 servicing plan.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMWindowsServicingPlan](New-CMWindowsServicingPlan)





---


### Examples
#### Example 1: Get all servicing plans
```PowerShell
PS XYZ:\> Get-CMWindowsServicingPlan -Fast
```
This command gets all Windows 10 servicing plans. The command does not return lazy properties.
#### Example 2: Get a servicing plan by name
```PowerShell
PS XYZ:\> Get-CMWindowsServicingPlan -Name "SvcPlan01"
```
This command returns the Windows 10 servicing plan named SvcPlan01.


---


### Parameters
#### **Fast**

Indicates that the cmdlet does not automatically refresh lazy properties.


Lazy properties contain values that are relatively inefficient to retrieve which can cause additional network traffic and decrease cmdlet performance. If lazy properties are not used, this parameter should be specified.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies the AutoDeploymentID of a servicing plan.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|true    |0       |False        |AutoDeploymentId|



#### **Name**

Specifies the name of a servicing plan.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |0       |False        |





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
Get-CMWindowsServicingPlan [-Id] <Int32> [-Fast] [<CommonParameters>]
```
```PowerShell
Get-CMWindowsServicingPlan [[-Name] <String>] [-Fast] [<CommonParameters>]
```
