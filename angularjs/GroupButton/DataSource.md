---
layout: post
title: DataSource Support
description: datasource
platform: Angular-1
control: GroupButton
documentation: ug
---

# DataSource

GroupButton can populate the button items based on data source and by specifying the associated fields. 

Refer the below table to know about the available fields.

<table>
<tr>
<td>
text<br/><br/></td><td>
Text to be displayed in button.<br/><br/></td></tr>
<tr>
<td>
prefixIcon<br/><br/></td><td>
Icon class name – prefixIcon will be displayed from the left margin of the button.<br/><br/></td></tr>
<tr>
<td>
suffixIcon<br/><br/></td><td>
Icon class name – suffixIcon will be displayed from the left margin of the button.<br/><br/></td></tr>
<tr>
<td>
contentType<br/><br/></td><td>
Specifies content type of button item.<br/><br/></td></tr>
<tr>
<td>
imagePosition<br/><br/></td><td>
Specifies position of the image in a button item.<br/><br/></td></tr>
<tr>
<td>
Selected<br/><br/></td><td>
Specifies the selection state of button item.<br/><br/></td></tr>
<tr>
<td>
URL<br/><br/></td><td>
Used to include the URL tag to the button item.<br/><br/></td></tr>
<tr>
<td>
htmlAttribute<br/><br/></td><td>
It defines the HTML attributes such as class and styles for an button item.<br/><br/></td></tr>
<tr>
<td>
linkAttribute<br/><br/></td><td>
It defines the image attributes such as height, width, styles, etc.<br/><br/></td></tr>
</table>


## Local Data

To set the local JSON data, define a JSON array and initialize the GroupButton with **dataSource** property. Specify the column names in the fields’ property.

N> the columns are bounded automatically when the field's are specified with the default names like id, text, etc...

Below is the sample to code to render the GroupButton JSON dataSource.

{% highlight html %}

<div id="groupButton" ej-groupbutton e-groupbuttonmode="radiobutton" e-width="100%" e-showroundedcorner="true" e-datasource="dataSource"></div>

{% endhighlight %}

{% highlight js %}

    <script>
        angular.module('GroupBtnCtrl', ['ejangular'])
        .controller('GroupBtnCtller', function ($scope) {
            
            var groupdata = [
                        { text: "Day", contentType: "textonly" },
                        { text: "Week", contentType: "textonly" },
                        { text: "Work Week", contentType: "textonly" },
                        { text: "Month", contentType: "textonly", selected: "selected" },
                        { text: "Agenda", contentType: "textonly" }];

            $scope.dataSource = groupdata;
        });
    </script>

{% endhighlight %}

![](DataSource_images/DataSoruce_img1.jpeg)

## Remote Data

To bind remote data to the GroupButton, you can assign a service data as an instance of `ejDataManager` to the `dataSource` property along with the fields mapping.

{% highlight html %}

<div id="groupButton" ej-groupbutton e-groupbuttonmode="radiobutton" e-width="100%" e-showroundedcorner="true" e-datasource="dataManager" e-fields="field" e-query="query" ></div>

{% endhighlight %}

{% highlight javascript %}

    <script>
        angular.module('GroupBtnCtrl', ['ejangular'])
        .controller('GroupBtnCtller', function ($scope) {   
            $scope.field = { text: "CustomerID" };         
            $scope.dataManager = ej.DataManager({
                url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"
            });
            $scope.query = ej.Query().from("Orders").take(6);            
        });
    </script>

{% endhighlight %}