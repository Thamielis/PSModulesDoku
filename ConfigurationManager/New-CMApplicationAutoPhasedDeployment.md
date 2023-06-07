New-CMApplicationAutoPhasedDeployment
-------------------------------------




### Synopsis
Use this cmdlet to create a phased deployment for an application by generating two phases with same settings.



---


### Description

Use this cmdlet to create a phased deployment for an application by generating two phases with same settings. This cmdlet's behavior is the same as the Create Phased Deployment wizard on an application, when you select the option to Automatically create a default two phase deployment .



> [!NOTE] > Before you create a phased deployment, make sure to distribute the application's content to a distribution point.



---


### Examples
#### Example 1: Create a deployment by app name
```PowerShell
New-CMApplicationAutoPhasedDeployment -ApplicationName "myApp" -Name "myPDName" -FirstCollectionID "SMSDM001" -SecondCollectionID "SMSDM003" -CriteriaOption Compliance -CriteriaValue 1 -BeginCondition AfterPeriod -DaysAfterPreviousPhaseSuccess 2 -ThrottlingDays 3 -InstallationChoice AfterPeriod -DeadlineUnit Hours -DeadlineValue 4 -Description "MyDescription"
```

#### Example 2: Create a deployment by input app object
```PowerShell
$myApp | New-CMApplicationAutoPhasedDeployment -Name "myPDName" -FirstCollectionID "SMSDM001" -SecondCollectionID "SMSDM003" -CriteriaOption Compliance -CriteriaValue 1 -BeginCondition AfterPeriod -DaysAfterPreviousPhaseSuccess 2 -ThrottlingDays 3 -InstallationChoice AfterPeriod -DeadlineUnit Hours -DeadlineValue 4 -Description "MyDescription"
```



---


### Parameters
#### **Application**

Specify an application object for the phased deployment.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |1       |True (ByValue)|



#### **ApplicationId**

Specify an application ID for the phased deployment.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |1       |False        |CIId<br/>CI_ID|



#### **ApplicationName**

Specify an application name for the phased deployment.






|Type      |Required|Position|PipelineInput|Aliases                        |
|----------|--------|--------|-------------|-------------------------------|
|`[String]`|true    |1       |False        |ApplicationLocalizedDisplayName|



#### **BeginCondition**

Specify an option for beginning the second phase of deployment after success of the first phase:


* `AfterPeriod`: This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Automatically begin this phase after a deferral period (in days) . If you specify this value, use DaysAfterPreviousPhaseSuccess to configure the period of time.


* `Manually`: This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Manually begin the second phase deployment .



Valid Values:

* AfterPeriod
* Manually






|Type                  |Required|Position|PipelineInput|
|----------------------|--------|--------|-------------|
|`[BeginConditionType]`|false   |named   |False        |



#### **CriteriaOption**

Specify an option to choose the criteria for success of the first phase:


* `Compliance`: This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Deployment success percentage . Specify the percentage value with the CriteriaValue parameter.


* `Number`: This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Number of devices successfully deployed . Specify the number of devices with the CriteriaValue parameter.



Valid Values:

* Compliance
* Number






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[CriteriaType]`|false   |named   |False        |



#### **CriteriaValue**

This integer value depends upon the value that you specify for CriteriaOption :


* `Compliance`: Specify the percentage


* `Number`: Specify the number of devices






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DaysAfterPreviousPhaseSuccess**

Specify an integer value for the number of days after success of the first phase to begin the second phase. This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Automatically begin this phase after a deferral period (in days) .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DeadlineUnit**

Specify the type of deadline period. Use this parameter with DeadlineValue .



Valid Values:

* Hours
* Days
* Weeks
* Months






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[TimeUnitType]`|false   |named   |False        |



#### **DeadlineValue**

This parameter is only used if you specify `AfterPeriod` with the InstallationChoice parameter.


Specify an integer value for the period of time for the deadline. Use the DeadlineUnit parameter to specify the type of period: `Hours`, `Days`, `Weeks`, `Months`. This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Installation is required after this period of time .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Description**

Specify a description for the application phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FirstCollection**

Specify a collection object for the first phase.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **FirstCollectionId**

Specify a collection ID for the first phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **FirstCollectionName**

Specify a collection name for the first phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior. It's not recommended. You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InstallationChoice**

Specify an option for the behavior relative to when the software is made available:


* `AsSoonAsPossible`: This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Installation is required as soon as possible .


* `AfterPeriod`: This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Installation is required after this period of time . If you specify this value, use DeadlineUnit and DeadlineValue to configure the period of time.



Valid Values:

* AsSoonAsPossible
* AfterPeriod






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[InstallationChoiceType]`|false   |named   |False        |



#### **Name**

Specify a name for the application phased deployment.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SecondCollection**

Specify a collection object for the second phase.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **SecondCollectionId**

Specify a collection ID for the second phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SecondCollectionName**

Specify a collection name for the second phase.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ThrottlingDays**

Specify an integer value for the number of days to gradually make this software available. This parameter is the same as the following setting on the Settings page of the Create Phased Deployment wizard in the console: Gradually make this software available over this period of time (in days) .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
* IResultObject#SMS_PhasedDeployment






---


### Notes




---


### Syntax
```PowerShell
New-CMApplicationAutoPhasedDeployment [-Application] <IResultObject> [-BeginCondition {AfterPeriod | Manually}] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-Description <String>] [-DisableWildcardHandling] [-FirstCollection <IResultObject>] [-FirstCollectionId <String>] [-FirstCollectionName <String>] [-ForceWildcardHandling] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] -Name <String> [-SecondCollection <IResultObject>] [-SecondCollectionId <String>] [-SecondCollectionName <String>] [-ThrottlingDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMApplicationAutoPhasedDeployment [-ApplicationId] <String> [-BeginCondition {AfterPeriod | Manually}] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-Description <String>] [-DisableWildcardHandling] [-FirstCollection <IResultObject>] [-FirstCollectionId <String>] [-FirstCollectionName <String>] [-ForceWildcardHandling] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] -Name <String> [-SecondCollection <IResultObject>] [-SecondCollectionId <String>] [-SecondCollectionName <String>] [-ThrottlingDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMApplicationAutoPhasedDeployment [-ApplicationName] <String> [-BeginCondition {AfterPeriod | Manually}] [-CriteriaOption {Compliance | Number}] [-CriteriaValue <Int32>] [-DaysAfterPreviousPhaseSuccess <Int32>] [-DeadlineUnit {Hours | Days | Weeks | Months}] [-DeadlineValue <Int32>] [-Description <String>] [-DisableWildcardHandling] [-FirstCollection <IResultObject>] [-FirstCollectionId <String>] [-FirstCollectionName <String>] [-ForceWildcardHandling] [-InstallationChoice {AsSoonAsPossible | AfterPeriod}] -Name <String> [-SecondCollection <IResultObject>] [-SecondCollectionId <String>] [-SecondCollectionName <String>] [-ThrottlingDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
