# aiorequests

A lightweight package for initiating parallel requests, with similar api as the default python requests library.

```python 
import aiorequests
requests = [
    aiorequests.get('http://worldtimeapi.org/api/timezone/Europe/Stockholm'),
    aiorequests.get('http://worldtimeapi.org/api/timezone/Europe/Stockholm'),
    aiorequests.get('http://worldtimeapi.org/api/timezone/Europe/Stockholm'),
    aiorequests.get('http://worldtimeapi.org/api/timezone/Europe/Stockholm'),
    aiorequests.get('http://worldtimeapi.org/api/timezone/Europe/Stockholm'),
]
aiorequests.run_async(requests)

# Yields results
[
    (200, {'utc_datetime': '2023-02-06T09:58:21.832839+00:00', ...})
    (200, {'utc_datetime': '2023-02-06T09:58:21.830673+00:00', ...})
    ...
]
```

By default this uses the ```.json()``` method, but any other be used with 
```.get(..., response_method='read')```. Other supported http methods are 
```.post()```, ```.put()```, ```.patch()```, ```.delete()```, ```.head()```, 
```.options()```, ```.request(METHOD, ...)```


