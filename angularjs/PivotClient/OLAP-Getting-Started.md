---
layout: post
title: OLAP-Getting-Started
description: olap-getting started
platform: AngularJS
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Getting Started

The AngularJS directives are usually included within the `ej.widget.angular.min.js` file and all these directives are usually packed together in a common module known as `ejangular`. For basic details on how to configure Syncfusion widgets in AngularJS framework, refer [here](https://help.syncfusion.com/js/angularjs).

To get start with the PivotClient control in AngularJS framework, the following list of external dependencies are mandatory, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [AngularJS](https://angularjs.org/)

The external AngularJS script file `angular.min.js` can also be accessed from the following installed location. 

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\external

An another mandatory script is `ej.widget.angular.min.js`, which can be accessed from the below specified location.

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\common

## Script/CSS Reference

Create a new HTML file and include the below initial code.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title> </title>
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

Refer the CSS file from the specific theme folder to your HTML file within the head section as shown below. Refer the built-in available themes from [here](https://help.syncfusion.com/js/theming-in-essential-javascript-components).

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - PivotClient</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
</head>

{% endhighlight %}

The scripts and style sheets listed below in the <head> tag could be found in any of the following locations:

Local Disk: [Click here](http://helpjs.syncfusion.com/js/installation-and-deployment) to know more about script and style sheets installed in local machine.
 
CDN Link: [Click here](http://helpjs.syncfusion.com/js/cdn) to know more about script and style sheets available online.

NuGet Package: [Click here](http://helpjs.syncfusion.com/js/installation-and-deployment#configuring-syncfusion-nuget-packages) to know more about script and style sheets available in NuGet package.

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - PivotClient</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
</head>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use[CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

## Creating a simple application with PivotClient and OLAP datasource (Client Mode)

This section covers the information that you need to know to populate a simple PivotClient with OLAP data completely on the client-side.  

### Initialize PivotClient
Create the PivotClient control using `ej-pivotclient` directive and define all its other properties prefixed with `e-` as shown in the below code.

{% highlight html %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotClientApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotClientCtrl">
        <div id="PivotClient1" ej-pivotclient e-datasource="dataSource"/>
    </div>
</body>
</html>

{% endhighlight %}

### Populate PivotClient with DataSource

Initializes the OLAP datasource for PivotClient widget as shown below.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotClientApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotClientCtrl">
        <div id="PivotClient1" ej-pivotclient e-datasource="dataSource" e-title="OLAP Browser"/>
    </div>
    <script>
        angular.module('PivotClientApp', ['ejangular']).controller('PivotClientPivotCtrl', function ($scope) {
            $scope.datasource = {
                data: "http://bi.syncfusion.com/olap/msmdpump.dll",
                catalog: "Adventure Works DW 2008 SE",
                cube: "Adventure Works",
                rows: [{
                    fieldName: "[Date].[Fiscal]"
                }],
                columns: [{
                    fieldName: "[Customer].[Customer Geography]"
                }],
                values: [{
                    measures: [{
                        fieldName: "[Measures].[Internet Sales Amount]",
                    }],
                    axis: "columns"
                }]
            };
            $scope.dataSource = $scope.datasource;
        });
    </script>
</body>
</html>

{% endhighlight %}

Now, PivotClient is rendered with PivotChart and PivotGrid with "Customer Geography" in Column, "Fiscal" in Row and "Internet Sales Amount" measure in Value section.

![](Getting-Started_images/OlapClientside.png) 

## Creating a simple application with PivotClient and OLAP datasource (Server Mode)

This section covers the information required to create a simple PivotClient bound to OLAP datasource from server-side.

N> We will be illustrating this section by creating a simple Web Application through Visual Studio IDE since PivotClient bound with data from server-side requires .NET dependency. The Web Application would contain a HTML page and a service that would transfer data to server-side, process and return back the data to client-side for control re-rendering. The service utilized for communication could be either WCF or WebAPI based on user requirement and we have illustrated both for user convenience.

### Project Initialization
Create a new **ASP.NET Empty Web Application** by using Visual Studio IDE and name the project as **???PivotClientDemo???**.

Next, add a HTML page. To add a HTML page in your Web Application, right-click on the project in Solution Explorer and select **Add > New Item.** In the **Add New Item** window, select **HTML Page** and name it as ???GettingStarted.html???, click **Add.**

Now, set ???GettingStarted.html??? as start-up page by right-clicking on ???GettingStarted.html??? page and select **???Set As Start Page???.**

### Control Initialization
Create the PivotClient control using `ej-pivotclient` directive and define all its other properties prefixed with `e-` as shown in the below code.

{% highlight html %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotClientApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotClientCtrl">
        <div id="PivotClient1" ej-pivotclient e-url="url" e-title="OLAP Browser" />
    </div>
    <script>
        angular.module('PivotClientApp', ['ejangular']).controller('PivotClientCtrl', function ($scope) {
            $scope.url: "/Olap"
        });
    </script>
</body>
</html>

{% endhighlight %}

The ???url??? property in PivotClient widget points the service endpoint, where data are processed and fetched in the form of JSON. The service used for the PivotClient widget as endpoint are WCF and WebAPI.

N> The above "GettingStarted.html" contains WebAPI URL, which is **???/Olap???**. Suppose if you are using WCF service, then the URL would look like **???/OlapService.svc???**. 

### WebAPI

**Adding a WebAPI Controller**

To add a WebAPI controller in your existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item.** In the **Add New Item** window, select **WebAPI Controller Class** and name it as **???OlapController.cs???**, click **Add.**

Now, WebAPI controller is added into your application successfully with the following file. The utilization of this file will be explained in the following sections.
 
* OlapController.cs

N> While adding WebAPI Controller Class, name it with the suffix ???Controller??? which is mandatory. For example, in demo the controller is named ???OlapController???.

Next, remove all the existing methods such as ???Get???, ???Post???, ???Put??? and ???Delete??? present inside `OlapController.cs` file. 

{% highlight c# %}

namespace PivotClientDemo
{
    public class OlapController: ApiController
    {
    
    }
}

{% endhighlight %}

**List of Dependency Libraries**

Next, add the following dependency libraries into your Web Application. You can find these libraries in GAC (Global Assembly Cache) in your machine.

To add them to your Web Application, right-click on **References** in Solution Explorer and select **Add Reference.** Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries are found. 

>**NOTE: If you have installed any version of SQL Server Analysis Service (SSAS) or Microsoft ADOMD.NET utility, then the location of Microsoft.AnalysisServices.AdomdClient library is [system drive:\Program Files (x86)\Microsoft.NET\ADOMD.NET]**

* Microsoft.AnalysisServices.AdomdClient
* Syncfusion.Compression.Base
* Syncfusion.Linq.Base
* Syncfusion.Olap.Base
* Syncfusion.PivotAnalysis.Base
* System.Data.SqlServerCe (Version: 4.0.0.0)
* Syncfusion.XlsIO.Base
* Syncfusion.Pdf.Base
* Syncfusion.DocIO.Base
* Syncfusion.EJ
* Syncfusion.EJ.Export
* Syncfusion.EJ.Pivot

**List of Namespaces**

The following are the list of namespaces to be added on top of the main class inside `OlapController.cs` file.

{% highlight c# %}

using Syncfusion.JavaScript;
using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using System;
using System.Collections.Generic;
using System.Configuration;
using System.Data;
using System.Data.SqlServerCe;
using System.Linq;
using System.Text;
using System.Web;
using System.Web.Http;
using System.Web.Script.Serialization;
using OLAPUTILS = Syncfusion.JavaScript.Olap;

namespace PivotClientDemo
{
    public class OlapController: ApiController
    {
    
    }
}

{% endhighlight %}

**Datasource Initialization**

Now, the connection string to connect OLAP Cube, PivotClient and JavaScriptSerializer instances are created immediately inside the main class in `OlapController.cs` file. Also, the database connection for saving and loading reports is provided appropriately. 

{% highlight c# %}

namespace PivotClientDemo
{
    public class OlapController: ApiController
    {
        PivotClient pivotClientHelper = new PivotClient();
        PivotTreeMap treeMapHelper = new PivotTreeMap();
        PivotChart chartHelper = new PivotChart();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        string conStringforDB = "";//Enter appropriate connection string to connect database for saving and loading operation of reports
        //Other codes
    }
}

{% endhighlight %}

**Service methods in WebAPI Controller**

Now you need to define the service methods inside OlapController class, found inside `OlapController.cs` file, created while adding WebAPI Controller Class to your Web Application.
 
{% highlight c# %}

namespace PivotClientDemo
{
    public class OlapController: ApiController
    {
        PivotClient pivotClientHelper = new PivotClient();
        PivotTreeMap treeMapHelper = new PivotTreeMap();
        PivotChart chartHelper = new PivotChart();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        string conStringforDB = "";//Enter appropriate connection string to connect database for saving and loading operation of reports

        [System.Web.Http.ActionName("InitializeClient")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> InitializeClient(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = null;
            DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(CreateOlapReport());
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientParams"].ToString());
        }

        [System.Web.Http.ActionName("InitializeGrid")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> InitializeGrid(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return jsonResult.ContainsKey("gridLayout") ? pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["gridLayout"].ToString()) : pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager);
        }

        [System.Web.Http.ActionName("InitializeChart")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> InitializeChart(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return chartHelper.GetJsonData(jsonResult["action"].ToString(), DataManager);
        }

        [System.Web.Http.ActionName("InitializeTreeMap")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> InitializeTreeMap(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return treeMapHelper.GetJsonData(jsonResult["action"].ToString(), DataManager);
        }

        [System.Web.Http.ActionName("DrillChart")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> DrillChart(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            return chartHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["drilledSeries"].ToString());
        }

        [System.Web.Http.ActionName("DrillTreeMap")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> DrillTreeMap(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            return treeMapHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["drillInfo"].ToString());
        }

        [System.Web.Http.ActionName("FilterElement")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> FilterElement(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientParams"].ToString());
        }

        [System.Web.Http.ActionName("RemoveSplitButton")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> RemoveSplitButton(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientParams"].ToString());
        }

        [System.Web.Http.ActionName("FetchMemberTreeNodes")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> FetchMemberTreeNodes(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["dimensionName"].ToString());
        }

        [System.Web.Http.ActionName("DrillGrid")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> DrillGrid(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["cellPosition"].ToString(), jsonResult["headerInfo"].ToString(), jsonResult["layout"].ToString());
        }

        [System.Web.Http.ActionName("NodeDropped")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> NodeDropped(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["dropType"].ToString(), jsonResult["nodeInfo"].ToString());
        }

        [System.Web.Http.ActionName("CubeChanged")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> CubeChanged(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            dynamic customData = serializer.Deserialize<dynamic>(jsonResult["customObject"].ToString());
            if (customData is Dictionary<string, object> && customData.ContainsKey("isPaging"))
            {
                DataManager.CurrentReport.EnablePaging = true;
                DataManager.CurrentReport.PagerOptions.SeriesPageSize = 5;
                DataManager.CurrentReport.PagerOptions.CategoricalPageSize = 3;
            }
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["cubeName"].ToString(), jsonResult["clientParams"].ToString());
        }

        [System.Web.Http.ActionName("MeasureGroupChanged")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> MeasureGroupChanged(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["measureGroupName"].ToString());
        }

        [System.Web.Http.ActionName("ToolbarOperations")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> ToolbarOperations(Dictionary<string, object> jsonResult)
        {
            var toolbarOperation = "";
            dynamic customData = "";
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            if ((jsonResult["olapReport"]) != null && !string.IsNullOrEmpty(jsonResult["olapReport"].ToString()))
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            if ((jsonResult["clientReports"]) != null && !string.IsNullOrEmpty(jsonResult["clientReports"].ToString()))
                DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            toolbarOperation = jsonResult["toolbarOperation"] == null ? null : jsonResult["toolbarOperation"].ToString();
            if (jsonResult.ContainsKey("customObject") && (jsonResult["customObject"]) != null && !string.IsNullOrEmpty(jsonResult["customObject"].ToString()))
                customData = serializer.Deserialize<dynamic>(jsonResult["customObject"].ToString());
            if ((customData is Dictionary<string, object> && customData.ContainsKey("isPaging") && (toolbarOperation == "Add Report" || toolbarOperation == "New Report")))
            {
                DataManager.CurrentReport.EnablePaging = true;
                DataManager.CurrentReport.PagerOptions.SeriesPageSize = 5;
                DataManager.CurrentReport.PagerOptions.CategoricalPageSize = 3;
            }
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, toolbarOperation, jsonResult["clientInfo"].ToString());
        }

        [System.Web.Http.ActionName("MemberExpanded")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> MemberExpanded(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            if (!string.IsNullOrEmpty(jsonResult["olapReport"].ToString()))
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            if (!string.IsNullOrEmpty(jsonResult["clientReports"].ToString()))
                DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, Convert.ToBoolean(jsonResult["checkedStatus"].ToString()), jsonResult["parentNode"].ToString(), jsonResult["tag"].ToString(), jsonResult["dimensionName"].ToString(), jsonResult["cubeName"].ToString());
        }

        [System.Web.Http.ActionName("UpdateReport")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> UpdateReport(Dictionary<string, object> jsonResult)
        {
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), jsonResult["clientParams"].ToString(), jsonResult["olapReport"].ToString(), jsonResult["clientReports"].ToString());
        }

        [System.Web.Http.ActionName("SaveReportToDB")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> SaveReportToDB(Dictionary<string, object> jsonResult)
        {
            string operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString(), reportName = string.Empty;
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            reportName = jsonResult["reportName"].ToString() + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            SqlCeCommand cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
            cmd1.Parameters.Add("@ReportName", reportName);
            if (operationalMode.ToLower() == "servermode" && analysisMode == "olap")
                cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(jsonResult["clientReports"].ToString()).ToArray());
            else
                cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(jsonResult["clientReports"].ToString()).ToArray());
            cmd1.ExecuteNonQuery();
            con.Close();
            return null;
        }

        [System.Web.Http.ActionName("RemoveReportFromDB")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> RemoveReportFromDB(Dictionary<string, object> jsonResult)
        {
            string operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString(), reportName = string.Empty;
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            reportName = jsonResult["reportName"].ToString() + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    cmd1 = new SqlCeCommand("DELETE FROM ReportsTable WHERE ReportName LIKE '%" + reportName + "%'", con);
                }
            }
            cmd1.ExecuteNonQuery();
            con.Close();
            return null;
        }

        [System.Web.Http.ActionName("RenameReportInDB")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> RenameReportInDB(Dictionary<string, object> jsonResult)
        {
            string operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString(), reportName = string.Empty, renameReport = string.Empty;
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            reportName = jsonResult["selectedReport"].ToString() + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            renameReport = jsonResult["renameReport"].ToString() + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    cmd1 = new SqlCeCommand("update ReportsTable set ReportName=@RenameReport where ReportName like '%" + reportName + "%'", con);
                }
            }
            cmd1.Parameters.Add("@RenameReport", renameReport);
            cmd1.ExecuteNonQuery();
            con.Close();
            return null;
        }

        [System.Web.Http.ActionName("FetchReportListFromDB")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> FetchReportListFromDB(Dictionary<string, object> jsonResult)
        {
            string reportNames = string.Empty, currentRptName = string.Empty, operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString();
            foreach (System.Data.DataRow row in GetDataTable().Rows)
            {
                currentRptName = (row.ItemArray[0] as string);
                if (currentRptName.IndexOf("##" + operationalMode + "#>>#" + analysisMode) >= 0)
                {
                    currentRptName = currentRptName.Replace("##" + operationalMode + "#>>#" + analysisMode, "");
                    reportNames = reportNames == "" ? currentRptName : reportNames + "__" + currentRptName;
                }
            }
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("ReportNameList", reportNames);
            dictionary.Add("action", jsonResult["action"].ToString());
            return dictionary;
        }

        [System.Web.Http.ActionName("LoadReportFromDB")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> LoadReportFromDB(Dictionary<string, object> jsonResult)
        {
            PivotReport report = new PivotReport();
            string operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            string currentRptName = string.Empty;
            foreach (DataRow row in GetDataTable().Rows)
            {
                currentRptName = (row.ItemArray[0] as string).Replace("##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower(), "");
                if (currentRptName.Equals(jsonResult["reportName"].ToString()))
                {
                    if (operationalMode.ToLower() == "servermode" && analysisMode == "olap")
                    {
                        var reportString = "";
                        OlapDataManager DataManager = new OlapDataManager(connectionString);
                        reportString = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                        DataManager.Reports = pivotClientHelper.DeserializedReports(reportString);
                        DataManager.SetCurrentReport(DataManager.Reports[0]);
                        return pivotClientHelper.GetJsonData("toolbarOperation", DataManager, "Load Report", jsonResult["reportName"].ToString());
                    }
                }
            }
            return dictionary;
        }

        private DataTable GetDataTable()
        {
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            DataSet dSet = new DataSet();
            new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
            con.Close();
            return dSet.Tables[0];
        }

        [System.Web.Http.ActionName("Export")]
        [System.Web.Http.HttpPost]
        public void Export()
        {
            string args = HttpContext.Current.Request.Form.GetValues(0)[0];
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            string fileName = "Sample";
            pivotClientHelper.ExportPivotClient(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
        }

        [System.Web.Http.ActionName("GetMDXQuery")]
        [System.Web.Http.HttpPost]
        public string GetMDXQuery(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
            return DataManager.GetMDXQuery();
        }

        [System.Web.Http.ActionName("ToggleAxis")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> ToggleAxis(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            DataManager.Reports = pivotClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            DataManager.ToggleAxis(DataManager.CurrentReport);
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientReports"].ToString());
        }

        [System.Web.Http.ActionName("Paging")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> Paging(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.SetPaging(jsonResult["currentReport"].ToString(), jsonResult["pagingInfo"].ToString()));
            return pivotClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["layout"].ToString());
        }

        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport() { Name = "Default Report" };
            olapReport.CurrentCubeName = "Adventure Works";

            MeasureElements measureElement = new MeasureElements();
            measureElement.Elements.Add(new MeasureElement { UniqueName = "[Measures].[Customer Count]" });

            DimensionElement dimensionElementRow = new DimensionElement();
            dimensionElementRow.Name = "Date";
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

            olapReport.SeriesElements.Add(dimensionElementRow);
            olapReport.CategoricalElements.Add(measureElement);

            return olapReport;
        }
    }
}

{% endhighlight %}

**Configure routing in Global Application Class**

To add a Global.asax in your existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item.** In the **Add New Item** window, select **Global Application Class** and name it as ???Global.asax???, click **Add.**
Once you finish adding the **Global.asax** file, immediately add the namespace **???using System.Web.Http;???** and then you can configure routing like in the following code example.

{% highlight c# %}

public class Global: System.Web.HttpApplication
{
    protected void Application_Start(object sender, EventArgs e)
    {
        System.Web.Http.GlobalConfiguration.Configuration.Routes.MapHttpRoute(name: "DefaultApi", routeTemplate: "{controller}/{action}/{id}", defaults: new
        {
            id = RouteParameter.Optional
        });
        AppDomain.CurrentDomain.SetData("SQLServerCompactEditionUnderWebHosting", true);
    }
}

{% endhighlight %}

Now, PivotClient is rendered with PivotChart and PivotGrid showing Customer Count over a period of fiscal years.

![](Getting-Started_images/olapwebapi.png) 

### WCF
This section demonstrates the utilization of WCF service as endpoint binding OLAP datasource to a simple PivotClient. For more details on this topic, [click here](http://help.syncfusion.com/angularjs/pivotclient/olap-connectivity#wcf).




