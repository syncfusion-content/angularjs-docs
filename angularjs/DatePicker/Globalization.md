---
layout: post
title: Globalization | TimePicker | AngularJS | Syncfusion
description: globalization
platform: AngularJS
control: DatePicker
documentation: ug
---

# Globalization

**DatePicker** has been provided with Built-in localization support, so that it will be able adapt based on culture specific locale defined for it.

**ej.globalize** library is used to globalize **DatePicker** calendar. Globalize values will be automatically used when **locale property** is set with locale string value for example fr-FR.

More than 350 culture specific files are available to localize the date. To know more about EJ globalize support, please refer the below link 

[http://help.syncfusion.com/js/localization](http://help.syncfusion.com/js/localization)

To translate our control content from default English to any of the culture, say For example - German language, then you need to refer the **ej.culture.de-DE.min.js** file in your application,

The en-US locale is currently being used as default culture in DatePicker. You can set any other culture to DatePicker by using Locale property. Below code example shows German cultured DatePicker.

Refer the below German culture file in head section of HTML page after the reference of ej.web.all.min.js file.

{% highlight html %}

     <script type="text/javascript" src="http://cdn.jsdelivr.net/syncfusion-ej-global/15.1.33/i18n/ej.culture.de-DE.min.js"></script>

{% endhighlight %}

To get the customized text for preferred culture refer below script after above file

{% highlight html %}

     <script type="text/javascript" src="https://cdn.jsdelivr.net/syncfusion-ej-global/15.1.33/l10n/ej.localetexts.de-DE.js"></script>

{% endhighlight %}

Please check with the below code example to achieve the localization after referring these files.

{% highlight html %}

     <input id="datepic_2" ej-datepicker e-locale="'de-DE'" />

{% endhighlight %}