---
title: Status and trend work item, query-based charts 
description: Create status, progress, and trend charts from flat-based queries   in VSTS and Team Foundation Server  
ms.prod: vs-devops-alm
ms.technology: vs-devops-reporting
ms.assetid: EFAD32DB-8B19-4ACC-8F72-87CC5A513798  
ms.manager: douge
ms.author: kaelli
ms.date: 05/22/2017
---


# Track progress by creating status and trend query-based charts 


[!INCLUDE [temp](_shared/vsts-tfs-header-17-15.md)]


You can quickly view the status of work in progress by charting the results of a [flat-list query](../work/track/using-queries.md). You can create several types of charts&mdash;such as pie, column, or trend&mdash;for the same query.  Charts support viewing a count of work items or a sum of values for select numeric fields, such as Remaining Work or Original Estimate. 

>[!NOTE]  
>For examples of queries based on numeric fields, see [Query by numeric fields](../work/track/query-numeric.md). For information on creating charts that track test progress and results, see [Track test status](../manual-test/getting-started/track-test-status.md).  

For example, the following image illustrates four different charts created from the same flat-list query. The pie chart groups the 146 active bugs by priority, and the bar chart groups the bugs by team and their triage status. The last two chart show two different views of the active bugs as they trend over the last two weeks.  

![A view of 4 charts for a flat-list query](_img/charts-active-bugs.png)

## Add and configure a query-based chart  

1.	From the Queries page, open the chart editor for a flat list query. You must belong to the Contributors group to create charts. Stakeholders can view charts but not create them. 

	<img src="_img/charts-new-chart.png" alt="Web portal, Queries page, Chart tab, New chart link" style="border: 2px solid #C3C3C3;" />  

2.	Select the chart type and field for grouping values. When you use pie, bar, and column charts, select a single field to view a count of work items.  

	<img src="_img/charts-pie-chart-active-bugs-by-priority.png" alt="Web portal, Queries page, Chart tab, Configure Chart dialog, Configure a Pie chart" style="border: 2px solid #C3C3C3;" /> 

	If you don't see the field you want in the **Group by** drop-down list, add the field as a column to the query and save the query. You can group by any field except date-time and free-form text fields. For example: 
	- To group by iterations, include the Iteration Path in the query or column options    
	- To group by team, include the Area Path or Node Name in the query or column options  
	- To group by a custom field, include it in a query clause or column options (See [Customize your work tracking experience](../work/customize/customize-work.md) to learn about adding a custom field)

	If you receive an error message when you close the chart editor, you need to request [Basic access](../security/change-access-levels.md).

3.	To sort the results, choose value or label as the sort option and then ascending or descending.  
	 
4.	To change a color, simply click a color on the chart and pick a new color from the color picker.  
 
Charts automatically update when you edit the query or refresh the query results.  


### Stacked bar chart  

A stacked bar chart lets you track progress against two field values. Node Name will display the last leaf within the hierarchy of area paths. Use this when you want to show data across teams.  

<img src="_img/charts-add-stacked-bar.png" alt="Web portal, Queries page, Chart tab, Configure Chart dialog, Stacked bar chart" style="border: 2px solid #C3C3C3;" /> 


### Trend chart  
Trend charts let you view progress for the last one, two, or four weeks. 

<img src="_img/charts-active-bugs-area-trend-2-weeks.png" alt="Web portal, Queries page, Chart tab, Configure Chart dialog, Stacked area trend chart" style="border: 2px solid #C3C3C3;" /> 


### Burndown chart  

Choose the Sum operator for Remaining Work to view a burndown chart of tasks. 

<img src="_img/create-burndown-trend-sum-chart.png" alt="Web portal, Queries page, Chart tab, Configure Chart dialog,Trend chart for the past 4 weeks" style="border: 2px solid #C3C3C3;" /> 
 

## Add a chart to a team dashboard 

Select your option from the chart's context menu. 

![Chart context menu, add to a team dashboard](_img/pin-chart-to-a-dashboard.png)

To add a chart to your team's home page, you must be a [team administrator](../work/scale/add-team-administrator.md). You can only add charts defined for shared queries.

To add other types of charts, such as test results and build summary charts, see [Add widgets and chart to a dashboard](add-widget-to-dashboard.md). 

>[!NOTE]  
><b>Feature availability: </b> For on-premises TFS 2015, you can pin charts to the team homepage. From VSTS or TFS 2015.1, you can add charts to [multiple team dashboards](dashboards.md) and get access to the [widget catalog](widget-catalog.md).  


<a id="add-chart-widget"></a> 
## Add chart widget to a dashboard   
>[!NOTE]  
><b>Feature availability: </b> The widget, Chart for Work Items, is available from VSTS or TFS 2015.2 or later version. You add it to a team dashboard from the [widget catalog](widget-catalog.md). 

 
If you've already defined your [flat list query](../work/track/using-queries.md), you can add and configure a chart to a team dashboard using the Chart for work items widget. 

1. From the web portal for VSTS, open the [team dashboard](dashboards.md) you want to add the chart to.   

2. Click ![Edit dashboard icon](_img/edit-dashboard-icon.png) to modify a dashboard, and then click ![add a widget icon](_img/add-widget-icon.png) to access the widget catalog.  

	If you don't see these icons, then you need to be added as a [team administrator](../work/scale/add-team-administrator.md) or a member of the Project Administrators group. 

3. Choose the Chart for work items widget and then click Add. 

	<img src="_img/widget-chart-work-query.png" alt="Web portal, Dashboards page, Widget catalog, Chart for work items widget" style="border: 2px solid #C3C3C3;" /> 

4. Click the widget's ![Configure widget icon](_img/icons/configure-icon.png) or the ![Actions icon](_img/icons/actions-icon.png) configure icon to open the configuration dialog. 

	<img src="_img/charts-chart-wit-widget-configure-dialog.png" alt="Web portal, Dashboards page, Widget catalog, Chart for work items widget, Configuration dialog" style="border: 2px solid #C3C3C3;" /> 

5. Give the chart a title, select the flat list query on which the chart is based, and choose the chart type.   

	Based on your chart type, specify values for the remaining fields. Change a chart color simply by choosing another color from those shown.   

	>[!NOTE]  
	>All rules for configuring charts described previously in this topic apply to configuring the chart for work items widget. 

6. After you save your changes, you'll see the new chart has been added to the dashboard. 

	![Chart of work items widget, configure dialog](_img/charts-chart-wit-widget-configured.png)  

7. Drag the tile anywhere on the dashboard to put it where you want it. 

8. When you're finished with your changes, click ![Exit edit-dashboard-mode icon](_img/exit-edit-dashboard-mode-icon.png) to exit dashboard editing.


## Related notes

Now you know how to create status and trend charts for work items. A few things to keep in mind...

- To create similar charts for tests, see [Track your test results](../manual-test/getting-started/track-test-status.md)    
- Charts you create for queries that are saved under Shared Queries are viewable by all team members and can be added to team dashboards or pinned to a team homepage   
- Charts that you create for queries under your My Queries folder are visible only to you   
- You can copy and email the URL of any chart page to share it with a team member 
- For additional examples of charts created from numeric fields, see [Query by a numeric field](../work/track/query-numeric.md). 


Also, from the web portal, you can view the following charts:  

- [Cumulative flow diagram](./guidance/cumulative-flow.md)  
- [Team velocity](./guidance/team-velocity.md)  
- [Sprint burndown charts](../work/scrum/sprint-burndown.md)  
- [Test progress and test results](../manual-test/getting-started/track-test-status.md)  
- [Add widgets and chart to a dashboard](add-widget-to-dashboard.md)
- [Widget catalog charts](widget-catalog.md)    


[!INCLUDE [temp](_shared/image-differences.md)]


### Requirements to view and create charts  
If you have [Stakeholder access or license](../security/get-started-stakeholder.md), you can only view charts. If you need to create charts, ask your project admin or account owner to grant you elevated access.   

### Fields that show up in the chart editor
For fields to appear in the chart editor, you must add the field to either the query filter criteria or a displayed column. 

You can't select fields for groupings that aren't supported, such as ID, Title, Tags, date-time fields, Description, Repro Steps, and other HTML and long text fields.  

### Charts and the display of areas and iterations
When you select **Area Path** or **Iteration Path**, only the leaf node appears in the chart. The leaf node is the last node of the full path. For example, ```Phone``` is the leaf node of ```FabrikamFiber/Fabrikam Website/Phone```. If your query contains a mixed level of leaf nodes, your chart might not reflect expected results.  

Use ```Node Name```, the area path leaf node, to see if that improves your results. 


Charts display in browsers that support Scalable Vector Graphics (SVG). This includes Internet Explorer 9 and Internet Explorer 10, Chrome, Firefox and Safari on Mac. Charts have not been optimized for mobile or touch displays. 

### Why some charts don't show all the field values in the results 
When a chart contains more than seven items within the data series, values in the eight-plus items are consolidated into a set labeled "other"?   

![Other category groups data beyond 7 set series](_img/tfs-vso-remaining-category-consolidation-chart.png)  


### Additional charts (TFS)
- If your team project has a project portal and SharePoint site configured, you can access several [Excel charts](excel/excel-reports.md). These include charts to monitor code quality, testing, and bug tracking activity.
- If your team project has [SQL Server reports](https://msdn.microsoft.com/library/dd380714.aspx) added, you can access several reports that include status and trend activities. If you need to add reporting, see [Add reports to a team project](./admin/add-reports-to-a-team-project.md).
- If your team project has reporting services added, you can [create an Excel chart from a work item query](./excel/create-status-and-trend-excel-reports.md).

### Query-based charts versus Excel-generated PivotCharts (TFS) 

Query-based charts generate data from the work item tracking data store and therefore displays the most recent data. [Excel PivotCharts](./excel/create-status-and-trend-excel-reports.md) access data published to the Analysis Services cube, which is refreshed every two hours by default. Also, Excel PivotCharts are only available to users of an on-premises TFS.     
 


[add-a-team]: ../Work/scale/multiple-teams.md
[team-assets]: ../Work/scale/manage-team-assets.md
[add-team-members]: ../Work/scale/multiple-teams.md#add-team-members
[add-team-admin]: ../work/scale/add-team-administrator.md
