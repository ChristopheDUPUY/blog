title: US Airports and Heliports
date: 2018-07-03 06:00
authors: Matthew Kudija
comments: true
slug: us-airports
tags: python, altair, vega, interactive, map
include: vega


<!-- PELICAN_BEGIN_SUMMARY -->

![alt]({filename}/images/us-heliports.png)

In a [previous post](http://matthewkudija.com/blog/2018/06/22/altair-interactive/#airports-example) I used Altair to plot an interactive map of US airports using data from [vega examples](https://github.com/vega/vega-datasets). I found another dataset that includes airport elevation which makes exploring the data all the more interesting.

<!-- PELICAN_END_SUMMARY -->

The [OurAirports](http://ourairports.com/data/) `airports.csv` dataset includes elevation data for airports and heliports. I filtered the global dataset to include small, medium, and large airports in the United States.

## US Airports

<div id="vis"></div>
<script type="text/javascript">
var embed_opt = {"mode": "vega-lite"};

function showError(el, error){
el.innerHTML = ('<div class="error">'
+ '<p>JavaScript Error: ' + error.message + '</p>'
+ "<p>This usually means there's a typo in your chart specification. "
+ "See the javascript console for the full traceback.</p>"
+ '</div>');
throw error;
}
const el = document.getElementById('vis');
vegaEmbed("#vis", spec, embed_opt)
.catch(error => showError(el, error));
</script>


## US Heliports


<div id="vis2"></div>
<script type="text/javascript">
var embed_opt2 = {"mode": "vega-lite"};

function showError(el2, error){
el.innerHTML = ('<div class="error">'
+ '<p>JavaScript Error: ' + error.message + '</p>'
+ "<p>This usually means there's a typo in your chart specification. "
+ "See the javascript console for the full traceback.</p>"
+ '</div>');
throw error;
}
const el2 = document.getElementById('vis2');
vegaEmbed("#vis2", spec2, embed_opt2)
.catch(error => showError(el2, error));
</script>



### Alternate Colors
I don't know how to change the color scheme directly with the Altair API, but it is straightforward to add the necessary vega json modifier, like `"scale": {"scheme": "Plasma"}` to the `"color"` property. There are a number of [available D3 color schemes](https://github.com/d3/d3-scale-chromatic). 


---

- *You can view the original [Jupyter Notebook](https://github.com/mkudija/General-Examples/blob/master/Altair/Altair-interactive.ipynb) that was used to generate these maps.*
- *All code examples in this notebook use Altair 2.1.0*