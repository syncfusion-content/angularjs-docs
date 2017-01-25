---
layout: post
title: multiselection
description: multiselection
platform: js
control: Autocomplete
documentation: ug
---

## MultiSelection

The AutoComplete component helps you to select multiple values from the suggestion list using the **e-multiselectmode** property.

There are two types of multi-selection mode.

1. VisualMode – Selection values are displayed in separate box with close like button.



{% highlight html %}


                            <input type="text" ej-autocomplete e-datasource="dataList" e-multiselectmode="multiselect" e-showpopupbutton="true" e-width="100%" />


<script type="text/javascript">
        var carList = [
                    "Audi S6", "Austin-Healey", "Alfa Romeo", "Aston Martin",
                    "BMW 7 ", "Bentley Mulsanne", "Bugatti Veyron",
                    "Chevrolet Camaro", "Cadillac ",
                    "Duesenberg J ", "Dodge Sprinter",
                    "Elantra", "Excavator",
                    "Ford Boss 302", "Ferrari 360", "Ford Thunderbird ",
                    "GAZ Siber",
                    "Honda S2000", "Hyundai Santro",
                    "Isuzu Swift", "Infiniti Skyline",
                    "Jaguar XJS",
                    "Kia Sedona EX", "Koenigsegg Agera",
                    "Lotus Esprit", "Lamborghini Diablo ",
                    "Mercedes-Benz ", "Mercury Coupe", "Maruti Alto 800",
                    "Nissan Qashqai",
                    "Oldsmobile S98", "Opel Superboss",
                    "Porsche 356 ", "Pontiac Sunbird",
                    "Scion SRS/SC/SD", "Saab Sportcombi", "Subaru Sambar", "Suzuki Swift",
                    "Triumph Spitfire ", "Toyota 2000GT",
                    "Volvo P1800", "Volkswagen Shirako"
        ];
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = carList;
$scope.multiselect=ej.MultiSelectMode.VisualMode;
             });
    </script>


{% endhighlight %}



Run the above code to render the following output. 

![](multiselection_images\multiselection_img1.png)

2. Delimiter – Selection values are separated using the delimiter character which can be specified using **e-delimitercChar** API.



{% highlight html %}


                            <input type="text" ej-autocomplete e-datasource="dataList" e-multiselectmode="multiselect" e-width="205" />

<script type="text/javascript">
        var carList = [
                    "Audi S6", "Austin-Healey", "Alfa Romeo", "Aston Martin",
                    "BMW 7 ", "Bentley Mulsanne", "Bugatti Veyron",
                    "Chevrolet Camaro", "Cadillac ",
                    "Duesenberg J ", "Dodge Sprinter",
                    "Elantra", "Excavator",
                    "Ford Boss 302", "Ferrari 360", "Ford Thunderbird ",
                    "GAZ Siber",
                    "Honda S2000", "Hyundai Santro",
                    "Isuzu Swift", "Infiniti Skyline",
                    "Jaguar XJS",
                    "Kia Sedona EX", "Koenigsegg Agera",
                    "Lotus Esprit", "Lamborghini Diablo ",
                    "Mercedes-Benz ", "Mercury Coupe", "Maruti Alto 800",
                    "Nissan Qashqai",
                    "Oldsmobile S98", "Opel Superboss",
                    "Porsche 356 ", "Pontiac Sunbird",
                    "Scion SRS/SC/SD", "Saab Sportcombi", "Subaru Sambar", "Suzuki Swift",
                    "Triumph Spitfire ", "Toyota 2000GT",
                    "Volvo P1800", "Volkswagen Shirako"
        ];
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = carList;
$scope.multiselect=ej.MultiSelectMode.Delimiter;
             });
    </script>


{% endhighlight %}



Run the above code to render the following output. 

![](multiselection_images\multiselection_img2.png)

