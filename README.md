### requests
---
.py http requests
http://docs.python-requests.org/en/master/

https://github.com/requests/requests/

http://docs.python-requests.org/en/latest/#

```sh
pipenv install requests
```

```py
import requests
r = requests.get('http://api.github.com/user', auth=('user', 'pass'))
r.status_code
r.headers['content-type']
r.encoding
r.text
r.json()

```

```
```

