Invoke-CMWmiQuery
-----------------




### Synopsis
Run a WMI query.



---


### Description

The Invoke-CMWmiQuery cmdlet runs a Windows Management Instrumentation (WMI) query. Unlike other query cmdlets or tools, with this cmdlet the connection and namespace is already set up for you.



You can also use this cmdlet to create a query with WMI Query Language (WQL). Configuration Manager uses WQL for queries in collections. WQL is similar to SQL, but still uses the SMS Provider, thus abides by role-based access controls.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Invoke-CMWmiMethod](Invoke-CMWmiMethod)





---


### Examples
#### Example 1: Run a WQL query
```PowerShell
$WQL = @"
SELECT app.* FROM SMS_ApplicationLatest AS app
INNER JOIN SMS_CIContentPackage AS con ON app.CI_ID=con.CI_ID
INNER JOIN SMS_DistributionPoint AS srv ON con.PackageID=srv.PackageID
WHERE app.IsHidden = 0
"@

Invoke-CMWmiQuery -Query $WQL -Option Lazy
```

#### Example 2: Run a WMI query for device collections
```PowerShell
$Search = [Microsoft.ConfigurationManagement.PowerShell.Provider.SmsProviderSearch]::new()
$Search.AddOrder("CollectionID", [Microsoft.ConfigurationManagement.PowerShell.Provider.SearchParameterOrderBy]::Asc)
$Search.Add("Name","DeviceCol*", $True)

Invoke-CMWmiQuery -Search $Search -ClassName "SMS_Collection" -Option Lazy
```

#### Example 3: Run a WMI query for sites by status
```PowerShell
$Search.Clear()
$Search.Add("Status", $True)

Invoke-CMWmiQuery -ClassName "SMS_Site" -Search $Search
```

#### Example 4: Run a WMI query for sites by name
```PowerShell
$Search.Clear()
$Search.Add("SiteName", $null, [Microsoft.ConfigurationManagement.PowerShell.Provider.SearchParameterOperator]::NotEquals)

Invoke-CMWmiQuery -ClassName "SMS_Site" -Search $Search
```

#### Example 5: Run a WMI query for applications
```PowerShell
$Search.Clear()
$Search.AddAdhoc("CI_ID > 0")

Invoke-CMWmiQuery -ClassName "SMS_Application" -Search $Search -Option Lazy
```



---


### Parameters
#### **ClassName**

Specifies the Configuration Manager WMI class that you want to query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Context**

Specify the WMI context as a hash table. It's a list of name/value pairs that are passed to a WMI provider that supports context information for a customized operation.






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|false   |named   |False        |



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



#### **Option**

The most common option is `Fast`.


Specify a query option:


* `None`: Default


* `Lazy`: By default, the cmdlet loads lazy properties.


* `Fast`: Use this option to not load lazy properties. This option can return results more quickly for some classes.


* `ExpectResults` & `ExpectResultsThrowException`: If the query returns no results, throw an exception. This exception typically ends a script.


* `FastExpectResults` & `LazyExpectResults`: These options combine `Fast` and `Lazy` with `ExpectResults`.


* `ExpectResultsSoftFail`: If the query returns no results, output an error, but don't end the script.




For more information about lazy properties, see Configuration Manager lazy properties (/mem/configmgr/develop/core/understand/configuration-manager-lazy-properties).


The following values are for internal use only:


* Clone


* NoMask


* NoRefresh

* IgnoreNoResults




Valid Values:

* None
* Fast
* Fast
* Fast
* ExpectResults
* LazyExpectResults
* LazyExpectResults
* Clone
* ExpectResultsSoftFail
* ExpectResultsThrowException
* NoMask
* IgnoreNoResults






|Type            |Required|Position|PipelineInput|Aliases|
|----------------|--------|--------|-------------|-------|
|`[QueryOptions]`|false   |named   |False        |Options|



#### **Query**

Specifies a WMI Query Language (WQL) statement.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **Search**

Specifies an SMSProviderSearch object.






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[SmsProviderSearch]`|true    |named   |False        |



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
* IResultObject[]


* IResultObject






---


### Notes




---


### Syntax
```PowerShell
Invoke-CMWmiQuery -ClassName <String> [-Context <Hashtable>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Option {None | NoRefresh | Lazy | Fast | ExpectResults | FastExpectResults | LazyExpectResults | Clone | ExpectResultsSoftFail | ExpectResultsThrowException | NoMask | IgnoreNoResults}] -Search <SmsProviderSearch> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMWmiQuery [-Query] <String> [-Context <Hashtable>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Option {None | NoRefresh | Lazy | Fast | ExpectResults | FastExpectResults | LazyExpectResults | Clone | ExpectResultsSoftFail | ExpectResultsThrowException | NoMask | IgnoreNoResults}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
