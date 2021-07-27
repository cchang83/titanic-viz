	<!DOCTYPE html>
<html>
	<head>
	  <meta charset="utf-8">
	  <script src="https://d3js.org/d3.v3.min.js"></script>
	  <script src="//cdnjs.cloudflare.com/ajax/libs/d3-legend/1.1.0/d3-legend.js"></script>
	  <style> 

      .axis text {
        font-family: 'Open Sans', sans-serif;
        font-size: 12pt;
      }
      .axis .label {
        font-size: 20pt;
      }

      .axis path, .axis line {
        fill: none;
        stroke: #000;
        shape-rendering: crispEdges;
      }
	  
	  .color-legend text {
        font-family: 'Open Sans', sans-serif;
        font-size: 12pt;
      }
	  
	  h2 {
		text-indent: 80px;
		font-family: 'Open Sans', sans-serif;
	  }
	  
	  h5 {
		text-indent: 110px;
		font-family: 'Open Sans', sans-serif;
	  }

	  div {
		text-indent: 135px;
		font-family: 'Open Sans', sans-serif;
	  }
	  </style>
	</head>
	<body>
      <script type="text/javascript">
		d3.select('body')
		  .append('h2')
		  .text("Titanic Passenger Outcomes")
	   
		d3.select('body')
		  .append('h5')
		  .text("(Scroll over bars for additional information)")
		
		var outerWidth = 500;
        var outerHeight = 250;
        var margin = { left: 90, top: 30, right: 120, bottom: 60 };
        var barPadding = 0.2;
		
		var colorColumn = "Category";
		var yColumn = "Count";
		var xColumn = "Pclass";
	    var layerColumn = colorColumn
		
	    var innerWidth  = outerWidth  - margin.left - margin.right;
        var innerHeight = outerHeight - margin.top  - margin.bottom;
		
	    var svg = d3.select("body").append("svg")
          .attr("width",  outerWidth)
          .attr("height", outerHeight);
        var g = svg.append("g")
          .attr("transform", "translate(" + margin.left + "," + margin.top + ")");
        
		//Add axes and legend
		var xAxisG = g.append("g")
          .attr("class", "x axis")
          .attr("transform", "translate(0," + innerHeight + ")");
        var yAxisG = g.append("g")
          .attr("class", "y axis");
	    var colorLegendG = g.append("g")
          .attr("class", "color-legend")
          .attr("transform", "translate(25, 0)");
		
		
	    var xScale = d3.scale.ordinal().rangeBands([0, innerWidth], barPadding);
        var yScale = d3.scale.linear().range([innerHeight, 0]);
        var colorScale = d3.scale.ordinal()
		  .domain(['Male Casualty', 'Female Casualty', 'Male Survivor', 'Female Survivor'])
		  .range(['darkblue', 'darkred', 'cornflowerblue', 'palevioletred']);  

	    var xAxis = d3.svg.axis().scale(xScale).orient("bottom")
          .outerTickSize(0);
   	    var yAxis = d3.svg.axis().scale(yScale).orient("left")
		  .ticks(5)
		  .outerTickSize(0);

		
		var colorLegend = d3.legend.color()
			.scale(colorScale)
			//.ascending(true)
			.shapePadding(3)
			.shapeWidth(15)
			.shapeHeight(15)
			.labelOffset(4);
		
		
		// draw graph
		function render(data){
        
			var nested = d3.nest()
			  .key(function (d){ return d[layerColumn]; })
			  .entries(data);
			
			var stack = d3.layout.stack()
			  .y(function(d) { return d[yColumn]; })
			  .values(function (d) { return d.values; });
			  
			var layers = stack(nested); 
			
			xScale.domain(layers[0].values.map(function (d){
              return d[xColumn];
            }));

			yScale.domain([
				0,
				d3.max(layers, function (layer){
				  return d3.max(layer.values, function (d){
					return d.y0 + d.y;
					});
				})
			]);
			
			colorScale.domain(layers.map(function (layer){
			  return layer.key;
			}));

			xAxisG.call(xAxis);
			yAxisG.call(yAxis);

			var layerGroups = g.selectAll(".layer").data(layers);
			layerGroups.enter().append("g").attr("class", "layer");
			layerGroups.exit().remove();
			layerGroups.style("fill", function (d){
			  return colorScale(d.key);
			});

			var bars = layerGroups.selectAll("rect").data(function (d){
			  return d.values;
			});
			bars.enter()
				.append("rect")
				.on("mouseover", handleMouseOver)
				.on("mouseout", handleMouseOut)
			bars.exit().remove();
			bars
			  .attr("x", function (d){ return xScale(d[xColumn]); })
			  .attr("y", function (d){ return yScale(d.y0 + d.y); })
			  .attr("width", xScale.rangeBand())
			  .attr("height", function (d){ return innerHeight - yScale(d.y); })
			
			colorLegendG.call(colorLegend);
	    
			//add axes labels

			svg.append("text")
				.attr("class", "x label")
				.attr("text-anchor", "middle")
				.attr("x", 235)
				.attr("y", 240)
				.style("font-family", "sans-serif")
				.text("Passenger Class");
 
			svg.append("text")
				.attr("class", "y label")
				.attr("text-anchor", "end")
				.attr("y", 6)
				.attr("dy", "2em")
				.attr("transform", "rotate(-90)")
				.style("font-family", "sans-serif")
				.text("Number of Passengers");
		
			// Interactivity: define mouseover effects
			function handleMouseOver(d, i) {  // Add interactivity

				// Use D3 to select element, change color and size
				d3.select(this).attr({
				  fill: "orange"
				});
			
				// Select the infobox, use .text to set the content
				// d is the data point
				d3.select(".infobox").style('visibility', 'visible');
				d3.select(".infobox .Pclass").text(d['Pclass']);
				d3.select(".infobox .Category").text(d['Category']);
				d3.select(".infobox .Count").text(d['Count']);
				d3.select(".infobox .Percent_Total").text(d['Percent_Total']);
				d3.select(".infobox .Percent_Class").text(d['Percent_Class']);
				d3.select(this)
				  .transition()
				  .duration(100);
			}
			
			function handleMouseOut(d, i) {
				// Use D3 to select element, change color back to normal
				d3.select(this).attr({
				  fill: function(d) {return colorScale(d.Category)}
				})

				d3.select(".infobox").style('visibility', 'hidden');
			}
		}

		function type(d){
  		  d.Count = +d.Count;
		  return d;
		}

		d3.csv("titanic_surv.csv.csv", type, render);
		
	  </script>
	  <div class="infobox" style = "visibility: hidden;">
		<h4>Passenger Class: <strong class="Pclass"></strong></h3>
		<h4 class="Category">Outcome</h4>
		<p>Number of Passengers: <strong class="Count">N/A</strong></p>
		<p>Percent of Total Passengers: <strong class="Percent_Total">%</strong></p>
		<p>Percent of Class: <strong class="Percent_Class">%</strong></p>
	  </div>
	</body>
	</head>
</html>
