# Vue Chartkick

Create beautiful charts with one line in Vue.js

[See it in action](http://ankane.github.io/chartkick.js/examples/)

Supports [Chart.js](http://www.chartjs.org/), [Google Charts](https://developers.google.com/chart/), and [Highcharts](http://www.highcharts.com/)

## Charts

Line chart

```vue
<line-chart :data='{"2013-02-10 00:00:00 -0800": 11, "2013-02-11 00:00:00 -0800": 6}'></line-chart>
```

Pie chart

```vue
<pie-chart :data='[["Blueberry", 44], ["Strawberry", 23]]'></pie-chart>
```

Column chart

```vue
<column-chart :data='[["Sun", 32], ["Mon", 46], ["Tue", 28]]'></column-chart>
```

Bar chart

```vue
<bar-chart :data='[["Work", 32], ["Play", 1492]]'></bar-chart>
```

Area chart

```vue
<area-chart :data='{"2013-02-10 00:00:00 -0800": 11, "2013-02-11 00:00:00 -0800": 6}'></area-chart>
```

Scatter chart

```vue
<scatter-chart :data='[[174.0, 80.0], [176.5, 82.3], [180.3, 73.6], [167.6, 74.1], [188.0, 85.9]]'></scatter-chart>
```

Geo chart - *Google Charts*

```vue
<geo-chart :data='[["United States", 44], ["Germany", 23], ["Brazil", 22]]'></geo-chart>
```

Timeline - *Google Charts*

```vue
<timeline :data='[["Washington", "1789-04-29", "1797-03-03"],["Adams", "1797-03-03", "1801-03-03"]]'></timeline>
```

Multiple series

```vue
data = [
  {name: "Workout", data: {"2013-02-10 00:00:00 -0800": 3, "2013-02-17 00:00:00 -0800": 4}},
  {name: "Call parents", data: {"2013-02-10 00:00:00 -0800": 5, "2013-02-17 00:00:00 -0800": 3}}
];

// and
<line-chart :data="data" />
```

### Say Goodbye To Timeouts

Make your pages load super fast and stop worrying about timeouts. Give each chart its own endpoint.

```vue
<line-chart data="/stocks"></line-chart>
```

### Options

Id, width, and height

```vue
<line-chart id="users-chart" width="800px" height="500px"></line-chart>
```

Min and max values

```vue
<line-chart :min="1000" :max="5000"></line-chart>
```

`min` defaults to 0 for charts with non-negative values. Use `null` to let the charting library decide.

Colors

```vue
<line-chart :colors='["pink", "#999"]'></line-chart>
```

Stacked columns or bars

```vue
<column-chart :stacked="true"></column-chart>
```

Discrete axis

```vue
<line-chart :discrete="true"></line-chart>
```

Label (for single series)

```vue
<line-chart label="Value"></line-chart>
```

Axis titles

```vue
<line-chart xtitle="Time" ytitle="Population"></line-chart>
```

You can pass options directly to the charting library with:

```vue
<line-chart :library='{backgroundColor: "#eee"}'></line-chart>
```

See the documentation for [Google Charts](https://developers.google.com/chart/interactive/docs/gallery), [Highcharts](http://api.highcharts.com/highcharts), and [Chart.js](http://www.chartjs.org/docs/) for more info.

### Data

Pass data as an array or object

```vue
<pie-chart :data='{"Blueberry": 44, "Strawberry": 23}'></pie-chart>
<pie-chart :data='[["Blueberry", 44], ["Strawberry", 23]]'></pie-chart>
```

Times can be a `Date`, a timestamp, or a string (strings are parsed)

```vue
<line-chart :data='[[new Date(), 5], [1368174456, 4], ["2013-05-07 00:00:00 UTC", 7]]'></line-chart>
```

## Installation

Run

```sh
npm install chartkick vue-chartkick --save
```

### Chart.js

Run

```sh
npm install chart.js --save
```

And add

```es6
window.Chart = require('chart.js');
```

### Google Charts

Include

```html
<script src="https://www.google.com/jsapi"></script>
```

### Highcharts

Run

```sh
npm install highcharts --save
```

And add

```javascript
window.Highcharts = require('highcharts');
```

### Without NPM

Include the charting library

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.3.0/Chart.bundle.js"></script>
```

And then the Chartkick libraries

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/chartkick/2.1.0/chartkick.js"></script>
<script src="dist/vue-chartkick.js"></script>
```

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/ankane/vue-chartkick/issues)
- Fix bugs and [submit pull requests](https://github.com/ankane/vue-chartkick/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features