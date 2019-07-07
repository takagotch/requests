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

```py
payload = {'key1': 'value1', 'key2': 'value2'}
r = requests.post("https://httpbin.org/post", data=payload)
print(r.text)

payload_tuples = [('key1', 'value1'), ('key1', 'value2')]
r1 = requests.post('https://httpbin.org/post', data=payload_tuples)
payload_dict = {'key1': ['value1', 'value2']}
r2 = requests.post('https://httpbin.org/post', data=payload_dict)
print(r1.text)

r1.text == r2.text

import json
url = 'https://api.github.com/some/endpoint'
payload = {'some': 'data'}
r = requests.post(url, data=json.dumps(payload))

url = 'https://api.github.com/some/endpoint'
payload = {'some': 'data'}

r = requests.post(url, json=payload)

url = 'https://httpbin.org/post'
files = {'file': open('report.xlx', 'rb')}

r = requests.post(url, files=files)
r.text

url = 'https://httpbin.org/post'
files = {'file': ('report.xls', open('report.xls', 'rb', 'application/vnd.ms-ex'))}

r = requests.post(url, files=files)
r.text

url = 'https://httpbin.org/post'
files = {'file': ('report.csv', 'some,data,to,send\nanother,row,to,send\n')}

r = requests.post(url, files=files)
r.text

r = requsts.get('http://httpbin.org/get')
r.status_code

r.status_code == requests.codes.ok

bad_r = requests.get('https://httpbin.org/status/404')
bad_r.status_code

bad_r.raise_for_status()

r.raise_for_status()

r.headers

r.headers['Content-Type']
r.headers.get('content-type')

url = 'http://example.com/some/cookie/setting/url'
r = requests.get(url)

r.cookies['example_cookie_name']

url = 'https://httpbin.org/cookies'
cookies = dict(cookies_are='working')

r = requests.get(url, cookies=cookies)
r.text

jar = requests.cookies.RequestCookieJar()
jar.set('tasty_cookie', 'yum', domain='httpbin.org', path='/cookies')
jar.set('gross_cookie', 'blech', domain='httpbin.org', path='/elsewhere')
url = 'https://httpbin.org/cookies'
r = requests.get(url, cookies=jar)
r.text

r = request.get('http://github.com/')
r.url
r.status_code
r.histroy

r = requests.get('http://github.com/', allow_redirects=False)
r.status_code
r.histroy

r = requests.head('http://github.com/', allow_redirects=True)
r.url
r.history

requests.get('https://github.com/', timeout=0.001)
```


