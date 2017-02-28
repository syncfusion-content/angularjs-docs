---
layout: post
title: Localization in DropDownList widget
description: Localization in DropDownList widget
platform: Angular-1
control: DropDownList
documentation: ug
keywords: Localization, DropDownList, dropdown
---
# Localization

The DropDownList provides option to localize its strings, it is used to adapting the DropDownList to a particular local language. By default, the DropDownList will use the US English (en-US) as its language.

N> The culture name has to be specified in a standard format such as [Language Code]-[County/Region Code].

To localize the dropdownlist’s strings with your own localization, copy the default language informations and localize the strings in the values column. For example, to localize the DropDownList in German language (“de-DE”).

{% highlight javascript %}

ej.DropDownList.Locale["de-DE"] = {
    emptyResultText: "Keine Vorschläge" //replace with your text  
};
    
{% endhighlight %}

Set the locale property of the DropDownList to the new language.

{% highlight javascript %}

<input type="text" id="selectcompany" ej-dropdownlist e-datasource="data" e-fields-text="CompanyName" e-fields-value="ContactName" e-width="260" e-showcheckbox="true" e-locale="de-DE" e-enablefiltersearch="true" e-enablepopupresize="true" />

<script type="text/javascript">

var datalist = ej.DataManager({ url: "http://mvc.syncfusion.com/services/Northwnd.svc/Customers" });
angular.module('dropdownlistApp', ['ejangular'])
.controller('dropdownlistCtrl', function ($scope) {
    $scope.data = datalist;
    ej.DropDownList.Locale["de-DE"] = {
        emptyResultText: "Keine Vorschlage" //replace with your text  
    };
});

</script>
    
{% endhighlight %}