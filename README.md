# boston-corrected-squared
The corrected Boston Dataset, but with (crudely) accurate longitudes and latitudes so the points match up on Folium / geopandas.

I found this problem when I was trying to map each tract on the corrected Boston Dataset (reference: http://lib.stat.cmu.edu/datasets/boston_corrected.txt) as part of AI Hack 2021. The points did not match up at all with the geography of Boston, and also the names of the towns attached at each point.

What I did was to get two points that had to be quite far from each other - one at Nahant (the first entry) and one at Ashland with a CMEDV value of 21.9. Then I chose a representative spot those places should be at on Google Maps, by searching the towns' names  (LAT_new and LON_new). Then, I did a crude correction equation (basically x_corr = ax + b) to transform all the latitudes and longitudes to their right places.

The points were:
<table>
  <tr>
    <th>Town</th>
    <th>LON_original</th>
    <th>LAT_original</th>
    <th>LON_new</th>
    <th>LAT_new</th>
    <th>CMEDV</th>
  </tr>
  <tr>
    <td>Nahant</td>
    <td>-70.955</td>
    <td>42.255</td>
    <td>-70.9278</td>
    <td>42.426</td>
    <td>24</td>
  </tr>
  <tr>
    <td>Ashland</td>
    <td>-71.2895</td>
    <td>42.1575</td>
    <td>-71.465395</td>
    <td>42.259635</td>
    <td>21.9</td>
  </tr>
</table>

Testing with Folium shows that i) no points are in the water and ii) each point is way closer to the name of the town the point contains.

Feel free to use my dataset!
