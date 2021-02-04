`X + md5(subjectString+salt)`

```python
class WebSignDownloaderMiddleware(object):
    screen_key = "WSUDD"

    def process_request(self, request, spider):
        _st = request.url.split(".com")[-1] + self.screen_key
        md5String = spider.general_method.get_md5(_st).lower()
        request.headers['x-sign'] = "X" + md5String
```
