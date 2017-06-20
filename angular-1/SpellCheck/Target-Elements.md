---
title: SpellCheck - Working with Target Elements
description: Target element's text spell checking with Syncfusion SpellCheck
platform: Angular-1
control: spellcheck
documentation: ug
keywords: multiple target, target element check, iframe element check
---

# Supported Target Elements

The SpellCheck control has support for spell checking the HTML element’s texts such as div, span, textarea, input, address, article and IFrame elements.

## Multiple Target

The SpellCheck control has support for multiple target HTML element’s texts spelling and correct its error words. This can be achieved by passing the target HTML elements “id” values or “CSS Class Name” or combination of both id and class names to the property `controlsToValidate`.

The following code example describes the above behavior.

{% highlight html %}

<div id="control1">
    London, one of the most popular touist destinations in the world for a reason. A cultural and hisorical hub, London has an excellent public transportation system that allows visitors to see all the fantatic sights without spending a ton of money on a rental car. London contains four World Heritage Sites.
</div><br />
<textarea id="control2">
    Paris, the city of lihts and love - this short guide is full of ideas for how to make the most of the romnticism that oozes from every one of its beautiful corners.You couldn't possibly visit Paris without seeing the Eiffel Tower.     Even if you do not want to visit this world famous structure, you will see its top from all over Paris.
</textarea><br />
<span id="control3">
    Rome, one of the world's most facinating cities. The old adage that Rome was not built in a day - and that you won't see it in one or even in three - is true. For the intrepid traveler who can keep pace, here is a list of must-sees.         But reember what the Romans say: Even a lifetime isn't enough to see Rome.
</span><br />
<div id="SpellCheck" ej-spellcheck e-dictionarysettings="dictionarySettings" e-controlstovalidate="#control1,#control2,#control3"></div>

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
});

{% endhighlight %}

You need to pass the target HTML element’s id value or CSS class name or combination of the id value and class name with comma separator. Passing the class name followed by (.) character and passing the id value followed by the (#) character.

The following code example describes the spell checking of HTML element’s.

{% highlight html %}

<div id="control1">
    London, one of the most popular touist destinations in the world for a reason. A cultural and hisorical hub, London has an excellent public transportation system that allows visitors to see all the fantatic sights without spending a ton of money on a rental car. London contains four World Heritage Sites.
</div><br />
<textarea id="control2">
    Paris, the city of lihts and love - this short guide is full of ideas for how to make the most of the romnticism that oozes from every one of its beautiful corners.You couldn't possibly visit Paris without seeing the Eiffel Tower.     Even if you do not want to visit this world famous structure, you will see its top from all over Paris.
</textarea><br />
<span id="control3">
    Rome, one of the world's most facinating cities. The old adage that Rome was not built in a day - and that you won't see it in one or even in three - is true. For the intrepid traveler who can keep pace, here is a list of must-sees.         But reember what the Romans say: Even a lifetime isn't enough to see Rome.
</span><br />
<div id="SpellCheck" ej-spellcheck e-dictionarysettings="dictionarySettings" e-controlstovalidate="#control1,#control2,#control3"></div>
<input id="CheckSpell" type="button" class="ejinputtext" style="height:30px" value="Spell check" (click)="checkErrors($event)" />

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    $scope.checkErrors = function(args){
        var spellObj = $('#SpellCheck').data('ejSpellCheck');
        spellObj.showInDialog();
    }
});

{% endhighlight %}

The spellcheck component iterates through the target elements which specified in the “controlsToValidate” property, and process the element’s content one by one in the order of CSS elements, and id specified elements.

**IFrame Element**

The below code example shows the way to spell check the IFrame target element text.

{% highlight html %}

<iframe id="Spell" src="iframesource.html" height="300" width="800"></iframe>
<div id="SpellCheck" ej-spellcheck e-dictionarysettings="dictionarySettings" e-controlstovalidate="#Spell"></div>
<input id="CheckSpell" type="button" class="ejinputtext" style="height:30px" value="Spell check" (click)="checkErrors($event)" />

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    $scope.checkErrors = function(args){
        var spellObj = $('#SpellCheck').data('ejSpellCheck');
        spellObj.showInDialog();
    }
});

{% endhighlight %}

N> If you want to spell check the IFrame’s element content, you need to pass the IFrame element alone in ‘controlsToValidate” property. You could not perform the spell check with the combination of other elements with IFrame element.