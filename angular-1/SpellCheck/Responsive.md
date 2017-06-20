---
title: SpellCheck - Responsive
description: How to set the spellcheck, responsive to screen resolutions
platform: Angular-1
control: spellcheck
documentation: ug
keywords: Responsive, Responsive spellcheck dialog, Resize spellcheck dialog
---
# Responsive

The SpellCheck control has support for responsive behavior based on client browser’s width and height. To enable responsive, `isResponsive` property should be true.

The following code example describes the above behavior.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings" e-isresponsive="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum,Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
    </div>
</div>

{% endhighlight %}

The dialog of spell check control is rendering based on the client browser’s width and height. Refer to the following code to render the spellcheck dialog control with responsive.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings" e-isresponsive="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum,Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
    </div>
    <button id="CheckSpell" ej-button e-text="Spell Check" e-click="checkErrors"></button>
</div>

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    $scope.checkErrors = function (e) {
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
        spellObj.showInDialog();
    }
});

{% endhighlight %}

Mobile Rendering Screenshot:

![](Responsive_Images/Responsive_Image.png)