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
  height: 200px;
}

</style>
<!-- HTML -->
<div id="chartdiv"></div>

<!-- Resources -->
<script src="https://www.amcharts.com/lib/4/core.js"></script>
<script src="https://www.amcharts.com/lib/4/charts.js"></script>
<script src="https://www.amcharts.com/lib/4/themes/animated.js"></script>

<!-- Chart code -->
<script>
// Themes begin
am4core.useTheme(am4themes_animated);
// Themes end

// Create chart instance
var chart = am4core.create("chartdiv", am4charts.XYChart);

// Add data
chart.data = [{
    "name": "John",
    "points": 35654,
    "color": chart.colors.next(),
    "bullet": "https://www.amcharts.com/lib/images/faces/A04.png"
}, {
    "name": "Damon",
    "points": 65456,
    "color": chart.colors.next(),
    "bullet": "https://www.amcharts.com/lib/images/faces/C02.png"
}, {
    "name": "Patrick",
    "points": 45724,
    "color": chart.colors.next(),
    "bullet": "https://www.amcharts.com/lib/images/faces/D02.png"
}, {
    "name": "Mark",
    "points": 13654,
    "color": chart.colors.next(),
    "bullet": "https://www.amcharts.com/lib/images/faces/E01.png"
}];

// Create axes
var categoryAxis = chart.xAxes.push(new am4charts.CategoryAxis());
categoryAxis.dataFields.category = "name";
categoryAxis.renderer.grid.template.disabled = true;
categoryAxis.renderer.minGridDistance = 30;
categoryAxis.renderer.inside = true;
categoryAxis.renderer.labels.template.fill = am4core.color("#fff");
categoryAxis.renderer.labels.template.fontSize = 20;

var valueAxis = chart.yAxes.push(new am4charts.ValueAxis());
valueAxis.renderer.grid.template.strokeDasharray = "4,4";
valueAxis.renderer.labels.template.disabled = true;
valueAxis.min = 0;

// Do not crop bullets
chart.maskBullets = false;

// Remove padding
chart.paddingBottom = 0;

// Create series
var series = chart.series.push(new am4charts.ColumnSeries());
series.dataFields.valueY = "points";
series.dataFields.categoryX = "name";
series.columns.template.propertyFields.fill = "color";
series.columns.template.propertyFields.stroke = "color";
series.columns.template.column.cornerRadiusTopLeft = 15;
series.columns.template.column.cornerRadiusTopRight = 15;
series.columns.template.tooltipText = "{categoryX}: [bold]{valueY}[/b]";

// Add bullets
var bullet = series.bullets.push(new am4charts.Bullet());
var image = bullet.createChild(am4core.Image);
image.horizontalCenter = "middle";
image.verticalCenter = "bottom";
image.dy = 20;
image.y = am4core.percent(100);
image.propertyFields.href = "bullet";
image.tooltipText = series.columns.template.tooltipText;
image.propertyFields.fill = "color";
image.filters.push(new am4core.DropShadowFilter());
</script>

