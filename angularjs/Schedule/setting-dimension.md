---
title: Setting dimension
description: Setting dimension for Schedule control
platform: Angular-1
control: schedule
documentation: ug
keywords: dimension, cell dimension, cell width, cell height 
---
# Setting Dimension

The dimension normally refers to the height and width of the element. With Scheduler, it is possible to set 2 kinds of dimensions.

* Scheduler dimension (Scheduler control height and width)
* Cell dimension (Scheduler cells height and width)

## Scheduler Dimension

The `e-height` and `e-width` properties can be defined to set the outer dimension of the Scheduler control.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="70%" e-height="500px">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {            
        });
    </script>
</body>
</html>

{% endhighlight %}

N> The height and width properties accepts both **pixel** and **percentage** values.

## Scheduler Cell Dimensions

### Cell Height

The `e-cellheight` property allows the Scheduler to set the height of the cells in pixels. The appointment height in vertical mode changes accordingly as per the cell size within which it renders.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-cellheight="40px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //Array of JSON data configure in dataSource
            $scope.appointments = [{
                Id: 1,
                Subject: "Music Class",
                StartTime: new Date(2017, 1, 7, 6, 0, 0),
                EndTime: new Date(2017, 1, 7, 7, 0, 0)
            }, {
                Id: 2,
                Subject: "School",
                StartTime: new Date(2017, 1, 7, 9, 0, 0),
                EndTime: new Date(2017, 1, 7, 14, 30, 0)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> In **desktop** mode, the default height value of the cells is set to **20px**, whereas for **mobile** mode – the Scheduler cells are rendered with **40px** by default.

### Cell Auto-Height

The height of the cells specifically in timeline view can be made to adjust automatically based on its exceeding appointment count. It is controlled by an API named [showOverflowButton](/api/js/ejschedule#members:showOverflowButton) which accepts true or false value, denoting whether to enable/disable the cell auto-height adjusting option. To enable this option, set the value of `showOverflowButton` as `false` whereas its default value is `true`.

In **Vertical** view, the same functionality is made applicable only in the **Month View** whereas in **Horizontal** mode, it is applicable in all the views.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="month" e-showoverflowbutton="false" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //Array of JSON data configure in dataSource
            $scope.appointments = [{
                Id: 1,
                Subject: "Music Class",
                StartTime: new Date(2017, 1, 7, 6, 0, 0),
                EndTime: new Date(2017, 1, 7, 7, 0, 0)
            }, {
                Id: 2,
                Subject: "School",
                StartTime: new Date(2017, 1, 7, 9, 0, 0),
                EndTime: new Date(2017, 1, 7, 14, 30, 0)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

### Cell Width

The `e-cellwidth` property allows the Scheduler to set the width of the cells in pixels. The appointment width adjusts based on the cell width of the Scheduler.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-cellwidth="100px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //Array of JSON data configure in dataSource
            $scope.appointments = [{
                Id: 1,
                Subject: "Music Class",
                StartTime: new Date(2017, 1, 7, 6, 0, 0),
                EndTime: new Date(2017, 1, 7, 7, 0, 0)
            }, {
                Id: 2,
                Subject: "School",
                StartTime: new Date(2017, 1, 7, 9, 0, 0),
                EndTime: new Date(2017, 1, 7, 14, 30, 0)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> When the **e-cellheight** and **e-cellwidth** properties are set with some specific pixel values, the cell size does not adapt to the responsive behavior of the Scheduler while resizing it in desktop/mobile mode.

