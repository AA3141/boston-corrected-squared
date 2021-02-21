# boston-corrected-squared
The corrected Boston Dataset, but with (crudely) accurate longitudes and latitudes so the points match up on Folium / geopandas.

I found this problem when I was trying to map each tract on the corrected Boston Dataset (reference: http://lib.stat.cmu.edu/datasets/boston_corrected.txt) as part of AI Hack 2021. The points did not match up at all with the geography of Boston, and also the names of the towns attached at each point.

What I did was to get two points that had to be quite far from each other - one at Nahant (the first entry) and one at Ashland with a CMEDV value of 21.9. Then, I did a crude correction equation (basically x_corr = ax + b) to transform all the latitudes and longitudes to their right places.

Testing with Folium shows that i) no points are in the water and ii) each point is way closer to the name of the town the point contains.

Feel free to use my dataset!
