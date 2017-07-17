#Static Bar Chart
1. Generate some random data to populate the chart.
2. Set up svg container
3. Set up axes.  Place N data points axis ticks over the width and height of the chart.
4. Draw the svg container
5. Draw the axes, with an offset from the top of the container for the x axis.
6. Draw bars.  By applying the data() operator to our selection, we join data items and DOM elements, in this case rectangles, with each other.

#Animated Bar Chart 1
1. A lunatic chart with no real life purpose!
2. BUT it is mostly the same as the static bar chart, so it’s a good example.
3. There is now a setInterval function.  setInterval is native to JavaScript, and allows timed events.
4. The setInterval function shifts the queue of data one element off the start, and adds a new item at the end.
5. The setInterval function then calls redraw.  Redraw changes the height of all the bars to the new queue values.  
6. The duration in the redraw function is how long the chart should take to transition from the original state to the new state.

#Animated Bar Chart 2 – Enter, Update, Exit
1. A slightly less lunatic chart.  I created a stacked bar chart version of this for a project where they wanted to see how four variables were changing every hour.
2. Everything is the same as for the previous animated bar chart except for the redraw function.
3. The new redraw function demonstrates D3’s General Update Pattern.  This is usually referred to as the sequence, Enter, Update, Exit.  
4. Enter adds new elements, in our case rectangles, to match new data entering the visualisation that doesn’t have a rectangle associated with it yet.
5. Update simply updates existing rectangles with new data.
6. Exit removes rectangles that we don’t need anymore because the data isn’t needed.  In this example, rectangles that slide off the left the axis are removed.

# D3.js General Update Pattern
* The General Update Pattern is how D3 thinks about animating things.
* The first animated bar chart does not add or delete bars, so it only uses UPDATE for existing bars.
* The second animated bar chart both adds and deletes bars, so it uses ENTER, UPDATE and EXIT.
