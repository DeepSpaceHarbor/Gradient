---
title: Elements
date: 2018-10-14 22:16:01
tags:
featured_image: images/elements.jpg
summary: "Pretend. You pretend the feelings are there, for the world, for the people around you. Who knows? Maybe one day they will be. Tell him time is of the essence. This man is a knight in shining armor. He taught me a code. To survive."
category: "#random"
---

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

---
### Paragraph

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras eu varius nisl, sit amet tempor turpis. Integer non lacinia odio. Nam sodales lacus tellus, sed ultrices nisl facilisis ut. Cras rutrum semper purus. Aliquam erat volutpat. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse finibus lobortis tempor. Etiam euismod sapien vel nisi lobortis condimentum. Sed porttitor quam ut ullamcorper pellentesque. Duis maximus odio sed nulla hendrerit placerat. Mauris sed ultrices tortor. Donec dictum tortor massa. Sed purus nisl, aliquam sed ullamcorper non, aliquet eget sapien.

---

### Emphasis
Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

Inline `code` and `even more code..`.

---

### Lists
1. First ordered list item
2. Another item
3. Fruit sublist
  * Apple
  * Orange
  * Banana
4. And another item.

* Unordered list
- First
+ Second


---
### Tables

Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

---

### Code

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
//
```

### Charts

<!-- Styles -->
<style>
#chartdiv {
  width: 100%;
  height: 500px;
}

</style>

<!-- Resources -->
<script src="https://www.amcharts.com/lib/4/core.js"></script>
<script src="https://www.amcharts.com/lib/4/charts.js"></script>
<script src="https://www.amcharts.com/lib/4/themes/animated.js"></script>

<!-- Chart code -->
<script>
am4core.ready(function() {

// Themes begin
am4core.useTheme(am4themes_animated);
// Themes end



// Create chart instance
var chart = am4core.create("chartdiv", am4charts.RadarChart);

// Add data
chart.data = [{
  "category": "Research",
  "value": 80,
  "full": 100
}, {
  "category": "Marketing",
  "value": 35,
  "full": 100
}, {
  "category": "Distribution",
  "value": 92,
  "full": 100
}, {
  "category": "Human Resources",
  "value": 68,
  "full": 100
}];

// Make chart not full circle
chart.startAngle = -90;
chart.endAngle = 180;
chart.innerRadius = am4core.percent(20);

// Set number format
chart.numberFormatter.numberFormat = "#.#'%'";

// Create axes
var categoryAxis = chart.yAxes.push(new am4charts.CategoryAxis());
categoryAxis.dataFields.category = "category";
categoryAxis.renderer.grid.template.location = 0;
categoryAxis.renderer.grid.template.strokeOpacity = 0;
categoryAxis.renderer.labels.template.horizontalCenter = "right";
categoryAxis.renderer.labels.template.fontWeight = 500;
categoryAxis.renderer.labels.template.adapter.add("fill", function(fill, target) {
  return (target.dataItem.index >= 0) ? chart.colors.getIndex(target.dataItem.index) : fill;
});
categoryAxis.renderer.minGridDistance = 10;

var valueAxis = chart.xAxes.push(new am4charts.ValueAxis());
valueAxis.renderer.grid.template.strokeOpacity = 0;
valueAxis.min = 0;
valueAxis.max = 100;
valueAxis.strictMinMax = true;

// Create series
var series1 = chart.series.push(new am4charts.RadarColumnSeries());
series1.dataFields.valueX = "full";
series1.dataFields.categoryY = "category";
series1.clustered = false;
series1.columns.template.fill = new am4core.InterfaceColorSet().getFor("alternativeBackground");
series1.columns.template.fillOpacity = 0.08;
series1.columns.template.cornerRadiusTopLeft = 20;
series1.columns.template.strokeWidth = 0;
series1.columns.template.radarColumn.cornerRadius = 20;

var series2 = chart.series.push(new am4charts.RadarColumnSeries());
series2.dataFields.valueX = "value";
series2.dataFields.categoryY = "category";
series2.clustered = false;
series2.columns.template.strokeWidth = 0;
series2.columns.template.tooltipText = "{category}: [bold]{value}[/]";
series2.columns.template.radarColumn.cornerRadius = 20;

series2.columns.template.adapter.add("fill", function(fill, target) {
  return chart.colors.getIndex(target.dataItem.index);
});

// Add cursor
chart.cursor = new am4charts.RadarCursor();

}); // end am4core.ready()
</script>

<!-- HTML -->
<div id="chartdiv"></div>