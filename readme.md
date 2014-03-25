Chart.js
=======
*Simple HTML5 Charts using the canvas element* [chartjs.org](http://www.chartjs.org)

Further plans
-------
* Tooltips (see Branch [tooltips](https://github.com/Regaddi/Chart.js/tree/tooltips))
* Label positioning (inside, outside, legend)
* code refactoring for more object-oriented programming style and better extendability

Documentation
-------
You can find documentation at [chartjs.org/docs](http://www.chartjs.org/docs).

License
-------
Chart.js was taken down on the 19th March. It is now back online for good and IS available under MIT license.

Chart.js is available under the [MIT license] (http://opensource.org/licenses/MIT).

modified
-------
1. multi color in bar

mothod
-------
if you want use int in bar


    function wholeNumberAxisFix(data) {
      var maxValue = false;
      for (datasetIndex = 0; datasetIndex < data.datasets.length; ++datasetIndex) {
        var setMax = Math.max.apply(null, data.datasets[datasetIndex].data);
        if (maxValue === false || setMax > maxValue) maxValue = setMax;
      }
      var steps = new Number(maxValue);
      var stepWidth = new Number(1);
      if (maxValue > 10) {
        stepWidth = Math.floor(maxValue / 10);
        steps = Math.ceil(maxValue / stepWidth);
      }
      return { scaleOverride: true, scaleSteps: steps, scaleStepWidth: stepWidth, scaleStartValue: 0 };
    }

    new Chart(ctx).Bar(data, wholeNumberAxisFix(data))
