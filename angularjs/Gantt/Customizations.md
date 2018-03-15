---
layout: post
title: Customization
description: Customization
platform: AngularJS
control: Gantt
documentation: ug
---
# Customizations 

The Gantt provides support for the following UI customizations:

* Taskbar template
* Task label template
* Tooltip template

## Taskbar template

You can design your own taskbars to view the tasks in Gantt by using the [e-taskbartemplate](https://help.syncfusion.com/api/js/ejgantt#members:taskbartemplate "taskbarTemplate") property. You can map the JsRender script or script element’s ID to this property, and you can also customize the parent taskbars and milestones with custom templates by using the [e-parenttaskbartemplate](https://help.syncfusion.com/api/js/ejgantt#members:parenttaskbartemplate "parentTaskbarTemplate") and [e-milestonetemplate](https://help.syncfusion.com/api/js/ejgantt#members:milestonetemplate "milestoneTemplate") properties.

The following code example shows how to define template for taskbars in the Gantt:


{% highlight javascript %}
<script type="text/x-jsrender" id="taskbarTemplate">

    <div class="e-gantt-template-taskbar bg-color">

        <div>

            //…

        </div>

        <div class="e-gantt-template-progressbar">

        </div>

    </div>

</script>

<script type="text/x-jsrender" id="parentTaskbarTemplate">

    <div class="e-gantt-template-taskbar">

        //…

        <div class="e-gantt-template-progressbar">

        </div>

    </div>

</script>

<script type="text/x-jsrender" id="milestoneTemplate">

    <div class="e-gantt-template-milestone" style="background-color:transparent;">

        <div class="e-gantt-milestone milestone-top"></div>

        <div class="e-gantt-milestone milestone-bottom"></div>

    </div>

</script>

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-taskbartemplate= "taskbarTemplate"
      e-parenttaskbartemplate= "parentTaskbarTemplate"
      e-milestonetemplate= "milestoneTemplate"
      >
   </div>

<script>
     angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.taskbarTemplate="#taskbarTemplate";
               $scope.parentTaskbarTemplate="#parentTaskbarTemplate";
               $scope.milestoneTemplate="#milestoneTemplate";
          });    
</script>

{% endhighlight %}

The DOM structure and class names mentioned in the above code snippet is mandatory for providing the editing support in custom templates.

The following screenshot shows the template for taskbars in the Gantt:

![](Customization_images/Customization_img1.png)

## Task label template

By default, the task name will be displayed to the left and resource names will be displayed to the right of the taskbars as task labels. But these task labels are customizable.

### Mapping data source fields as task labels

You can set any data source fields as task labels by using [e-righttasklabelmapping](https://help.syncfusion.com/api/js/ejgantt#members:righttasklabelmapping "rightTaskLabelMapping") and [e-lefttasklabelmapping](https://help.syncfusion.com/api/js/ejgantt#members:lefttasklabelmapping "leftTaskLabelMapping") properties.

The following code example explains how to set task name field as right label and task ID field as left label:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-righttasklabelmapping= "taskName"
      e-lefttasklabelmapping= "taskID"
      >
   </div>
</body>

{% endhighlight %}

The following screenshot shows Gantt with task labels mapped with different data source fields:

![](Customization_images/Customization_img4.png)

### Task label templates

You can customize the task labels with templates by using [e-righttasklabeltemplate](https://help.syncfusion.com/api/js/ejgantt#members:righttasklabeltemplate "rightTaskLabelTemplate") and [e-lefttasklabeltemplate](https://help.syncfusion.com/api/js/ejgantt#members:lefttasklabeltemplate "leftTaskLabelTemplate") properties.

The following code example explains how to map custom templates to task labels:


{% highlight javascript %}
<script id="rightlabelTemplate" type="text/x-jsrender">

    {{"{{"}}if #data['resourceNames']{{}}}}

    <div>

        {{"{{"}}for resourceInfo{{}}}}

        <img src="14.2.0.26/themes/web/content/images/gantt/{{"{{"}}:resourceName{{}}}}.png" height="30px" />

        <span style="margin-left:5px;">{{"{{"}}:resourceName{{}}}}</span> {{"{{"}}:~_getSeparator(#get("array").data.length,#index){{}}}} {{"{{"}}/for{{}}}}

    </div>

    {{/if}}

</script>

<script id="leftlabelTemplate" type="text/x-jsrender">

    <div style="padding-top:5px;">

        <span>{{"{{"}}:#data['taskName']{{}}}}  [{{"{{"}}:status{{}}}}%]</span>

    </div>

</script>

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
       e-righttasklabeltemplate= "rightTaskLabelTemplate"
       e-lefttasklabeltemplate= "leftTaskLabelTemplate"
      >
   </div>

<script>
     angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.rightTaskLabelTemplate="#rightTaskLabelTemplate";
               $scope.leftTaskLabelTemplate="#leftTaskLabelTemplate";
          });    
</script>

{% endhighlight %}

The following screenshot shows Gantt with task label templates:

![](Customization_images/Customization_img2.png)

## Tooltip template

The default tooltip in the Gantt can be customized by using the [e-taskbartooltiptemplateid](https://help.syncfusion.com/api/js/ejgantt#members:taskbartooltiptemplate "taskbarTooltipTemplateId") property. You should map the JsRender script element’s ID value to this property.

The following code example shows how to customize the tooltip:


{% highlight javascript %}
<script type="text/x-jsrender" id="tooltipTemplate">

    <table>

       {{"{{"}}if #data['resourceNames']{{}}}}

        <tr>

            <td rowspan="3" style="padding:3px"><img src="14.2.0.26/themes/web/content/images/gantt/{{"{{"}}:#data['resourceNames']{{}}}}.png" height="40px" /></td>

            <td style="padding:3px"><b>Task done By:</b></td>

            <td style="padding:3px">{{"{{"}}:#data['resourceNames']{{}}}}</td>

        </tr>

        {{/if{{}}}}

        <tr>

            <td style="padding:3px"><b>Starts On:</b></td>

            <td style="padding:3px">{{"{{"}}:~_ganttDateFormatter("startDate"){{}}}}</td>

        </tr>

        <tr>

            <td style="padding:3px"><b>Ends On:</b></td>

            <td style="padding:3px">{{"{{"}}:~_ganttDateFormatter("endDate"){{}}}}</td>

        </tr>

    </table>

</script>
<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
       e-taskbartooltiptemplateid= "taskbarTooltipTemplateId"
      >
   </div>

<script>
     angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.taskbarTooltipTemplateId="#tooltipTemplate";
          });    
</script>
</body>

{% endhighlight %}

The following screenshot shows the Gantt with task tooltip customization:

![](Customization_images/Customization_img3.png)

### Cell tooltip 

The tooltip of the tree grid part can also be customized by using the[e-celltooltiptemplate](https://help.syncfusion.com/api/js/ejgantt#members:celltooltiptemplate) property. You should map the script element or element id to this property. The following code explains how to customize the cell tooltip in Gantt:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
       e-showgridcelltooltip= "true",
       e-celltooltiptemplate= "CustomToolTip",
      >
   </div>

<script>
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.CustomToolTip = "#CustomToolTip";
        });
    $.views.helpers({
        _TaskID: getTaskID,
        _TaskName: getTaskName
    });
    function getTaskID() {
        return this.data.record["taskId"];
    }
    function getTaskName() {
        return this.data.record["taskName"];
    }
</script>

<script id="CustomToolTip" type="text/x-jsrender">
    <table>
        <tr>
            <td>Id:</td>
            <td>{{:~_TaskID()}}</td>
        </tr>
        <tr>
            <td>Name:</td>
            <td>{{:~_TaskName()}}</td>
        </tr>
    </table>
</script>
</body>
{% endhighlight %}
![](Customization_images/Customization_img5.png)

