# <span style="color: rgb(113, 195, 250);">How to Add New Cities</span>

<hr style="margin-top: 13px; margin-bottom: -10px;">

## <span style="color: rgb(173, 216, 230);">1. New Folder</span>

Create a new folder within the applications location at: <code style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">.../cities/&lt;your city&gt;</code>.

---

## <span style="color: rgb(173, 216, 230);">2. properties.txt</span>

Add a <code style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">properties.txt</code> which should include all the mappable attributes of the city-specific Colouring Cities platform.

- The first line allows you to decide which attributes should be base properties used for the spatial temporal indicator "Share of mapped base properties in total amount".<br>
  E.g.:<br>
  
  <pre style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">Base properties (change requires to redo the data converting): bp1, bp2, bp3, ...</pre>

- Following lines should be a list of all attributes always led by one line defining the category of the next attributes (preferably the Colouring Cities categories, but you may also choose your own).<br>
  E.g.:<br>
  
  <pre style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">
    Type & form---------------------------
    building_attachment_form
    size_roof_shape
    size_roof_shape_source
    building_owner
    building_owner_source
    Land use---------------------------
    is_domestic
    ...
</pre>

- You may use an already existing file of another city and just add/remove attributes if necessary.

---

## <span style="color: rgb(173, 216, 230);">3. CityDistricts.geojson</span>

Add a <code style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">CityDistricts.geojson</code> dividing your city into geographical districts.<br>
(You may find such a file on the internet)

- The GEOJSON needs to be in a specific format following:<br>
  
  <pre style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">
    &lt;General information&gt;
    &lt;...&gt; "coordinates":[[[&lt;lat1&gt;,&lt;lon1&gt;],[&lt;lat2&gt;,&lt;lon2&gt;],[&lt;lat3&gt;,&lt;lon3&gt;],&lt;more coordinates&gt;]]} &lt;...&gt; "properties":{ &lt;...&gt;
    &lt;...&gt; "coordinates":[[[&lt;lat1&gt;,&lt;lon1&gt;],[&lt;lat2&gt;,&lt;lon2&gt;],[&lt;lat3&gt;,&lt;lon3&gt;],&lt;more coordinates&gt;]]} &lt;...&gt; "properties":{ &lt;...&gt;
    &lt;...&gt; "coordinates":[[[&lt;lat1&gt;,&lt;lon1&gt;],[&lt;lat2&gt;,&lt;lon2&gt;],[&lt;lat3&gt;,&lt;lon3&gt;],&lt;more coordinates&gt;]]} &lt;...&gt; "properties":{ &lt;...&gt;
    &lt;More city districts (one per line)&gt;
    &lt;End data / closing brackets&gt;
  </pre>

---

## <span style="color: rgb(173, 216, 230);">4. Optionally: Reduced Geometries</span>

You may add reduced geometries as <code style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">CityDistrictsSimplified1.geojson</code>, <code style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">CityDistrictsSimplified2.geojson</code>, and <code style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">CityDistrictsSimplified3.geojson</code> in order to increase the performance while rendering.<br>
(You may create these files using a GIS application)

- The GEOJSONs need to be in the same specific format:<br>
  
  <pre style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">
    &lt;General information&gt;
    &lt;...&gt; "coordinates":[[[&lt;lat1&gt;,&lt;lon1&gt;],[&lt;lat2&gt;,&lt;lon2&gt;],[&lt;lat3&gt;,&lt;lon3&gt;],&lt;more coordinates&gt;]]} &lt;...&gt;
    &lt;...&gt; "coordinates":[[[&lt;lat1&gt;,&lt;lon1&gt;],[&lt;lat2&gt;,&lt;lon2&gt;],[&lt;lat3&gt;,&lt;lon3&gt;],&lt;more coordinates&gt;]]} &lt;...&gt;
    &lt;...&gt; "coordinates":[[[&lt;lat1&gt;,&lt;lon1&gt;],[&lt;lat2&gt;,&lt;lon2&gt;],[&lt;lat3&gt;,&lt;lon3&gt;],&lt;more coordinates&gt;]]} &lt;...&gt;
    &lt;More city districts (one per line)&gt;
    &lt;End data / closing brackets&gt;
</pre>

---

## <span style="color: rgb(173, 216, 230);">5. Optionally: Color classes</span>

You may add <code style="background-color: rgb(60, 60, 60); padding: 5px; border-radius: 3px;">ColorClasses.txt</code> if you don't want to use the classes that are defined in the config.txt for your city.

- Should be in the same format as the color classes defined in the config.txt.
- If values are defined both in the <code>ColorClasses.txt</code> and the <code>config.txt</code>, the city-specific values of the <code>ColorClasses.txt</code> will be prioritized.

