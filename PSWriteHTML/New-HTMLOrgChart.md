New-HTMLOrgChart
----------------




### Synopsis
Short description



---


### Description

Long description



---


### Examples
#### EXAMPLE 1
```PowerShell
New-HTML {
    New-HTMLOrgChart {
        New-OrgChartNode -Name 'Test' -Title 'Test2' {
            New-OrgChartNode -Name 'Test' -Title 'Test2'
            New-OrgChartNode -Name 'Test' -Title 'Test2'
            New-OrgChartNode -Name 'Test' -Title 'Test2' {
                New-OrgChartNode -Name 'Test' -Title 'Test2'
            }
        }
    } -AllowExport -ExportExtension pdf -Draggable
} -FilePath $PSScriptRoot\Example-OrgChart01.html -ShowHTML -Online
```



---


### Parameters
#### **ChartNodes**

Define nodes to be shown on the chart






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[ScriptBlock]`|false   |1       |false        |



#### **Direction**

The available values are "top to bottom" (default value), "bottom to top", "left to right" and "right to left"



Valid Values:

* TopToBottom
* BottomToTop
* LeftToRight
* RightToLeft






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |2       |false        |



#### **VisileLevel**

It indicates the level that at the very beginning orgchart is expanded to.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |3       |false        |



#### **VerticalLevel**

Users can make use of this option to align the nodes vertically from the specified level.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |4       |false        |



#### **NodeTitle**

It sets one property of datasource as text content of title section of orgchart node. In fact, users can create a simple orghcart with only nodeTitle option.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |5       |false        |



#### **ToggleSiblings**

Once enable this option, users can show/hide left/right sibling nodes respectively by clicking left/right arrow.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Pan**

Users could pan the orgchart by mouse drag&drop if they enable this option.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Zoom**

Users could zoomin/zoomout the orgchart by mouse wheel if they enable this option.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **ZoomInLimit**

Users are allowed to set a zoom-in limit.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Double]`|false   |6       |false        |



#### **ZoomOutLimit**

Users are allowed to set a zoom-out limit.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Double]`|false   |7       |false        |



#### **Draggable**

Users can drag & drop the nodes of orgchart if they enable this option. **Note**: this feature doesn't work on IE due to its poor support for HTML5 drag & drop API.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **AllowExport**

It enable the export button for orgchart.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **ExportFileName**

It's filename when you export current orgchart as a picture.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |8       |false        |



#### **ExportExtension**

Available values are png and pdf.



Valid Values:

* png
* pdf






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |9       |false        |



#### **ChartID**

Forces ChartID to be set to known value rather than having it autogenerated






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |10      |false        |





---


### Notes
General notes



---


### Syntax
```PowerShell
New-HTMLOrgChart [[-ChartNodes] <ScriptBlock>] [[-Direction] <String>] [[-VisileLevel] <Int32>] [[-VerticalLevel] <Int32>] [[-NodeTitle] <String>] [-ToggleSiblings] [-Pan] [-Zoom] [[-ZoomInLimit] <Double>] [[-ZoomOutLimit] <Double>] [-Draggable] [-AllowExport] [[-ExportFileName] <String>] [[-ExportExtension] <Object>] [[-ChartID] <String>] [<CommonParameters>]
```