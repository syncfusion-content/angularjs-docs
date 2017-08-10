---
title: SpellCheck - Functionalities
description: SpellCheck Functionalities
platform: AngularJS
control: spellcheck
documentation: ug
keywords: spellcheck functionalities, check spelling, ignore words, change words, change, ignore, ignore settings,
---
# Functionalities

## Check Spelling

The main functionality of the SpellCheck control is checking the spelling of a word and returns the suggestions for an error word.

For example, if you pass the sentence that contains misspell words as input, you can know the error words in this sentence and its suggestions (apt words to replace).

## Ignore Words

The SpellCheck control provides the support to ignore the words from an error word consideration and also to ignore an error words whenever needed. Please refer the following options to ignore the words.

### Ignore

The `ignore` option is used to ignore a specific word once from the given input string. 

The following code example describes the above method implementation.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
    </div>
</div>

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    angular.element(document).ready(function () {
        var targetSentence = 'The <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display the spell errors.';
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
		var result = spellObj.ignore("textarea",targetSentence, null);
		alert(result.resultHTML); // This will display the corrected text after the ignore operation performed
    });
});

{% endhighlight %}

### Ignore All

The `ignore all` option is used to ignore all the error word occurrences from the given input string.

The following code example describes the way of using ignore all method.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
    </div>
</div>

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    angular.element(document).ready(function () {
        var targetSentence = 'This <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display all the <span class="errorspan e-errorword">textarea</span> spell errors.';
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
		var result = spellObj.ignoreAll("textarea",targetSentence, null);
		alert(result.resultHTML); // This will display the corrected text after the ignoreAll operation performed
    });
});

{% endhighlight %}

### Word Collection to Ignore

The `ignore words` option is used to ignore the collection of words from an error word checking. You can pass the technical terms, brand names which is not present in the dictionary file to this property "ignoreWords" as shown in the following code example and then while checking the spelling these passed words are considered as a correct word.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings" e-ignoreWords="ignoreWords">
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
    $scope.ignoreWords=["Facebook","Zuckerberg"];
});

{% endhighlight %}

## Ignore Settings

The `ignore settings` helps to ignore the uppercase, mixed case words, alphanumeric words, file path and email addresses from the error word checking. Ignore settings contains the following options to ignore the words based on their category.

* `ignoreAlphaNumericWords` - ignoring the alpha numeric words from an error word consideration.
* `ignoreUpperCase` - ignoring the upper case words from an error word consideration.
* `ignoreMixedCaseWords` - ignoring the mixed case words from an error word consideration.
* `ignoreFileNames` - ignoring the file address path from an error word consideration.
* `ignoreUrl` - ignoring the url links from an error word consideration.
* `ignoreEmailAddress` - ignoring the email address from an error word consideration.

The following code example uses to enable the checking of all the words formed with alphanumeric, uppercase, mixed case words and file paths and email addresses.  

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings" e-ignoreSettings="ignoreSettings">
        Amazon.com, Inc., often refered to as simply Amazon, is an American electronic commerce and cloud computing company with headquarters in Seattle, Washington. It is the largest web-based retailer in the United States. Amazon.com started as bookstore on the web, later diversifying to sell DVDs, Blu-rays, CDs, video downloads/streaming, MP3 downloads/streaming, audiobook downloads/streaming, software, video games, electronics, apparel, furniture, food, toys and jewelry. The company also produces consumer electronics notably, Amazon Kindle e-book readers, Fire tablets,Fire TV and Fire Phone and is the world's largest provider of cloud infrastructure services (IaaS). Amazon also sells certain low-end products like USB cables under its in-house brand AmazonBasics. Amazon has separate retail websites for United States, United Kingdom and Ireland, France, Canada, Germany, Italy, Spain, Netherlands, Australia, Brazil, Japan, China, India and Mexico. Amazon also offers international shipping to cetain other countries for some of its products.
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
    $scope.ignoreSettings={
                    ignoreAlphaNumericWords:false,
                    ignoreMixedCaseWords:false,
                    ignoreUpperCase:false,
                    ignoreUrl:false,
                    ignoreEmailAddress:false,
                    ignoreFileNames:false
                };
});

{% endhighlight %}

## Change Words

The SpellCheck control provides the support to change an error words from its possible suggestions. Please refer the following options to change an error word.

### Change

The `change` option is used to replace an error word occurrences once from the given input string with the correct word.

The following code example describes the behavior of change method.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
    </div>
</div>

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    angular.element(document).ready(function () {
        var targetSentence = 'The <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display the spell errors.';
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
		var result = spellObj.change("textarea",targetSentence,"text area", null);
		alert(result.resultHTML); // This will display the corrected text after the change operation performed
    });
});

{% endhighlight %}

### Change All

The `change all` option is used to replace all the occurrences of an error word with the correct word(selected from the suggestions list) from the given inputs string.

The following code example uses to change all the error word occurrences.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
    </div>
</div>

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    angular.element(document).ready(function () {
        var targetSentence = 'This <span class="errorspan e-errorword">textarea</span> sample uses a dialog to display all the <span class="errorspan e-errorword">textarea</span> spell errors.';
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
		var result = spellObj.changeAll("textarea",targetSentence,"text area", null);
		alert(result.resultHTML); // This will display the corrected text after the changeAll operation performed
    });
});

{% endhighlight %}

## Custom Words

The SpellCheck control provides the support to add the custom words into the custom dictionary file.

The `addToDictionary` option is used to add the custom words into the custom dictionary file.

The following code example uses to add the custom word into the custom dictionary file.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
    </div>
</div>

{% endhighlight %}

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    angular.element(document).ready(function () {
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
		var result = spellObj.addToDictionary("textarea");
    });
});

{% endhighlight %}

You can also add the custom words into the custom dictionary file through the dialog mode or context menu mode add to dictionary option.

* Dialog Mode - Add To Dictionary button is available in the dialog window, while highlighting the error word in the given input string and clicking this button then the word will be adding into the custom dictionary file.
* Context Menu Mode - Add To Dictionary option is available while right click on the error word and selecting this option, the word will be adding into the custom dictionary file.