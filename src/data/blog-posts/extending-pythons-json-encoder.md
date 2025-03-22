---
title: Extending Python's JSON Encoder
slug: extending-pythons-json-encoder
description: I extended Python's JSON encoder to handle datetimes.  This is how I did it
publishDate: 11 Mar 2022
---

I recently ran into a situation where I needed to ensure consistent formatting of datetimes as I serialized a dict to JSON using python’s built-in [json](https://docs.python.org/3/library/json.html) library.

The [JSON specification](https://www.json.org/json-en.html) does not specify how to handle dates - so it follows that the [JSON encoder](https://docs.python.org/3/library/json.html#json.JSONEncoder) does not, by default, include any date formatting.

Attempting to convert a dict which includes a datetime to JSON using the default JSON Encoder will raise a TypeError.

```python
import json
from datetime import datetime

obj = {
    "name": "test",
    "created": datetime.utcnow()
}

obj_default_encoder = json.dumps(obj)
print(obj_default_encoder)
# TypeError: Object of type datetime is not JSON serializable
```

I was able to achieve the behavior I wanted by defining a class which extends `json.JSONEncoder`.  In this class I included instructions for handling dates - you could also include other modifications to the default behavior of JSONEncoder.  Finally, I passed the custom encoder class to the `cls` kwarg of `json.dumps`

From [the python docs](https://docs.python.org/3/library/json.html#json.dump):
>To use a custom [`JSONEncoder`](https://docs.python.org/3/library/json.html#json.JSONEncoder "json.JSONEncoder") subclass (e.g. one that overrides the `default()` method to serialize additional types), specify it with the _cls_ kwarg; otherwise [`JSONEncoder`](https://docs.python.org/3/library/json.html#json.JSONEncoder "json.JSONEncoder") is used.

## Usage Example

```python
import json
from datetime import datetime

#
# Defining a custom JSON encoder class
#

# Custom class extends json.JSONEncoder
 class CustomJSONEncoder(json.JSONEncoder):
   
    # Override default() method
    def default(self, obj):

        # Datetime to string
        if isinstance(obj, datetime):
            # Format datetime - `Fri, 21 Aug 2020 17:59:59 GMT`
            obj = obj.strftime('%a, %d %b %Y %H:%M:%S GMT')

            return obj

        # Default behavior for all other types
        return super().default(obj)

#
# Using custom class to serialize a dict to JSON
#

obj = {
    "name": "test",
    "created": datetime.utcnow()
}

obj_custom_encoder = json.dumps(obj, cls=CustomJSONEncoder)
print(obj_custom_encoder)
# {"name": "test", "created": "Fri, 11 Mar 2022 19:11:51 GMT"}
```
