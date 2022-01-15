## query using LEFT OUTER JOIN with json_agg and json_build_object

**Challenge :**
To get product data using the specific productId from the db, I had to get the data from two tables. One table was from productdetail table and the other from features table in the database. And they're sharing the productId as the foreign key.
Basically, I needed to get data from two tables and combine as JSON object to send data to the client. The below features's value is come from the features table and both of them had same productId.

````javascript
{
    "id": 11,
    "name": "Air Minis 250",
    "slogan": "Full court support",
    "description": "This optimized air cushion pocket reduces impact but keeps a perfect balance underfoot.",
    "category": "Basketball Shoes",
    "default_price": "0",
    "features": [
  	{
            "feature": "Sole",
            "value": "Rubber"
        },
  	{
            "feature": "Material",
            "value": "FullControlSkin"
        },
  	// ...
    ],
}
````

**Result Observed :**
This above object is the data that the server needs to respond to client, when the client request with productId. To get the features' array that includes two different features come from the features table, I used **json_agg** and **json_build_object.**

**json_agg :** returns a JSON array whose elements are the JSON values formed from each of the to-be aggregated values.

**json_build_object :** build a JSON object out of a variadic argument list. By convention, the argument list consists of alternating keys and values.

````javascript
SELECT
  p.id,
  p.productname,
  p.slogan,
  p.description,
  p.category,
  p.defaultPrice,
  json_agg(json_build_object
  ('feature', f.feature, 'value', f.value )) as features
FROM productdetail p
LEFT OUTER JOIN features f
on p.id = f.productId WHERE p.id=${productId} GROUP BY p.id;
````

