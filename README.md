# Android-Simple-api

+ Add Volley to Project [📃](https://developer.android.com/training/volley) / [🐙](https://github.com/google/volley)

   dependencies {
   ```groovy
	   api 'com.android.volley:volley' //+':version'
   ```
   }

+ JSON Object
   ```java
   Volley.newRequestQueue(this).add(
   	new JsonObjectRequest(
		Request.Method.GET,
		"https://api.github.com/users/ShivaShirsath",
		null,
		new Response.Listener<JSONObject>(){
			@Override
			public void onResponse(JSONObject response) {
				try{
					Toast.makeText(MainActivity.this, response.toString() , Toast.LENGTH_LONG).show();
				} catch(Exception e){
					Toast.makeText(MainActivity.this, e.getMessage(), Toast.LENGTH_LONG).show();
				}
			}
		},
		new Response.ErrorListener(){
			@Override
			public void onErrorResponse(VolleyError e) {
			    Toast.makeText(MainActivity.this, e.getMessage(), Toast.LENGTH_LONG).show();
			}
		}
	)
   );
```
+ JSON Array
   ```java
   Volley.newRequestQueue(this).add(
   	new JsonArrayRequest(
		Request.Method.GET,
		"https://api.github.com/users/ShivaShirsath/repos",
		null,
		new Response.Listener<JSONArray>(){
			@Override
			public void onResponse(JSONArray response) {
				try{
					Toast.makeText(MainActivity.this, response.toString() , Toast.LENGTH_LONG).show();
				} catch(Exception e){
					Toast.makeText(MainActivity.this, e.getMessage(), Toast.LENGTH_LONG).show();
				}
			}
		},
		new Response.ErrorListener(){
			@Override
			public void onErrorResponse(VolleyError e) {
			    Toast.makeText(MainActivity.this, e.getMessage(), Toast.LENGTH_LONG).show();	
			}
		}
	)
   );
```

