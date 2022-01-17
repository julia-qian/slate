---
title: up.svc.ls v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins v4.0.1

---

<h1 id="up-svc-ls">up.svc.ls v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="/">/</a>

* <a href="/dev01/">/dev01/</a>

<h2 id="up-svc-ls-loan">Loan</h2>

Operations read or write data pertaining to the top level loan

### post__loan_next-payment-date_update

> Code samples

```shell
# You can also use wget
curl -X POST /loan/next-payment-date/update \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 568ff2b1-c5a1-4927-af23-82f703e08588' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/next-payment-date/update HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 568ff2b1-c5a1-4927-af23-82f703e08588
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "next_payment_date": "2022-01-17T20:57:12.143245Z",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'568ff2b1-c5a1-4927-af23-82f703e08588',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/next-payment-date/update',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '568ff2b1-c5a1-4927-af23-82f703e08588',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/next-payment-date/update',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '568ff2b1-c5a1-4927-af23-82f703e08588',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/next-payment-date/update', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '568ff2b1-c5a1-4927-af23-82f703e08588',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/next-payment-date/update', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/next-payment-date/update");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"568ff2b1-c5a1-4927-af23-82f703e08588"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/next-payment-date/update", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/next-payment-date/update`

Set the next payment date of a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "next_payment_date": "2022-01-17T20:57:12.143245Z",
  "dry_run": null
}
```

<h4 id="post__loan_next-payment-date_update-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» next_payment_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678",
  "next_payment_date": "2022-01-17"
}
```

<h4 id="post__loan_next-payment-date_update-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_next-payment-date_update-responseschema">Response Schema</h4>

Status Code **200**

*UpdateNextPaymentDateResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» next_payment_date|string(date)|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_upload

> Code samples

```shell
# You can also use wget
curl -X POST /loan/upload \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 95b85e52-46eb-4a47-b046-d285d01b0e83' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/upload HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 95b85e52-46eb-4a47-b046-d285d01b0e83
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "account_id": "E99449944",
  "application_id": "C333111777555",
  "origination_date": "2022-01-16",
  "exact_interest_rate": "21.99095000",
  "term": 11,
  "loan_amount": 122427,
  "payment_amount": 12593,
  "origination_fee": 2000,
  "subsidy_balance": 2500,
  "country_code": "US",
  "region_code": "CA",
  "currency_code": "USD",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'95b85e52-46eb-4a47-b046-d285d01b0e83',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/upload',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '95b85e52-46eb-4a47-b046-d285d01b0e83',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/upload',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '95b85e52-46eb-4a47-b046-d285d01b0e83',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/upload', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '95b85e52-46eb-4a47-b046-d285d01b0e83',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/upload', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/upload");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"95b85e52-46eb-4a47-b046-d285d01b0e83"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/upload", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/upload`

Upload a loan into NLS, as well as a customer if necessary

> Body parameter

```json
{
  "loan_id": "T12345678",
  "account_id": "E99449944",
  "application_id": "C333111777555",
  "origination_date": "2022-01-16",
  "exact_interest_rate": "21.99095000",
  "term": 11,
  "loan_amount": 122427,
  "payment_amount": 12593,
  "origination_fee": 2000,
  "subsidy_balance": 2500,
  "country_code": "US",
  "region_code": "CA",
  "currency_code": "USD",
  "dry_run": null
}
```

<h4 id="post__loan_upload-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» account_id|body|string|true|none|
|» application_id|body|string|true|none|
|» origination_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» exact_interest_rate|body|number|true|none|
|» term|body|integer|true|none|
|» loan_amount|body|integer|true|none|
|» payment_amount|body|integer|true|none|
|» origination_fee|body|integer|true|none|
|» subsidy_balance|body|integer|false|none|
|» country_code|body|string|true|none|
|» currency_code|body|string|true|none|
|» region_code|body|string|true|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678",
  "application_id": "E99449944"
}
```

<h4 id="post__loan_upload-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_upload-responseschema">Response Schema</h4>

Status Code **200**

*UploadResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» application_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_credit-bureau_special-comment

> Code samples

```shell
# You can also use wget
curl -X POST /loan/credit-bureau/special-comment \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 4826ae8f-5ab1-4136-a6f0-7844d66cf87c' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/credit-bureau/special-comment HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 4826ae8f-5ab1-4136-a6f0-7844d66cf87c
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "do_not_report": false,
  "special_comment": "AW",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'4826ae8f-5ab1-4136-a6f0-7844d66cf87c',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/credit-bureau/special-comment',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '4826ae8f-5ab1-4136-a6f0-7844d66cf87c',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/credit-bureau/special-comment',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '4826ae8f-5ab1-4136-a6f0-7844d66cf87c',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/credit-bureau/special-comment', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '4826ae8f-5ab1-4136-a6f0-7844d66cf87c',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/credit-bureau/special-comment', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/credit-bureau/special-comment");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"4826ae8f-5ab1-4136-a6f0-7844d66cf87c"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/credit-bureau/special-comment", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/credit-bureau/special-comment`

Adds a special comment to the loan for credit reporting

> Body parameter

```json
{
  "loan_id": "T12345678",
  "do_not_report": false,
  "special_comment": "AW",
  "dry_run": null
}
```

<h4 id="post__loan_credit-bureau_special-comment-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» special_comment|body|string|true|An enumeration.|
|» do_not_report|body|boolean|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» special_comment|AW|
|» special_comment|AH|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678"
}
```

<h4 id="post__loan_credit-bureau_special-comment-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_credit-bureau_special-comment-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_delete

> Code samples

```shell
# You can also use wget
curl -X POST /loan/delete \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: fa77915a-beb0-49f0-b6f1-192418535007' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/delete HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: fa77915a-beb0-49f0-b6f1-192418535007
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "TL12345678",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'fa77915a-beb0-49f0-b6f1-192418535007',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/delete',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'fa77915a-beb0-49f0-b6f1-192418535007',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/delete',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'fa77915a-beb0-49f0-b6f1-192418535007',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/delete', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'fa77915a-beb0-49f0-b6f1-192418535007',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/delete', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/delete");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"fa77915a-beb0-49f0-b6f1-192418535007"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/delete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/delete`

Delete a loan from NLS (loan must be closed)

> Body parameter

```json
{
  "loan_id": "TL12345678",
  "dry_run": null
}
```

<h4 id="post__loan_delete-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678"
}
```

<h4 id="post__loan_delete-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_delete-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_status_update

> Code samples

```shell
# You can also use wget
curl -X POST /loan/status/update \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: c45349a4-3ac9-485a-980b-274debd0659b' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/status/update HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: c45349a4-3ac9-485a-980b-274debd0659b
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "primary_status": "ACTIVE",
  "secondary_status": {
    "status": "CANCELED (REFUND)",
    "effective_date": "2022-01-17T20:57:12.141566Z",
    "delete": false
  },
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'c45349a4-3ac9-485a-980b-274debd0659b',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/status/update',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'c45349a4-3ac9-485a-980b-274debd0659b',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/status/update',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'c45349a4-3ac9-485a-980b-274debd0659b',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/status/update', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'c45349a4-3ac9-485a-980b-274debd0659b',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/status/update', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/status/update");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"c45349a4-3ac9-485a-980b-274debd0659b"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/status/update", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/status/update`

Update primary and/or secondary statuses on the loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "primary_status": "ACTIVE",
  "secondary_status": {
    "status": "CANCELED (REFUND)",
    "effective_date": "2022-01-17T20:57:12.141566Z",
    "delete": false
  },
  "dry_run": null
}
```

<h4 id="post__loan_status_update-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» primary_status|body|string|false|An enumeration.|
|» secondary_status|body|object|false|none|
|»» status|body|any|true|none|
|»»» *anonymous*|body|string|false|An enumeration.|
|»»» *anonymous*|body|string|false|none|
|»» effective_date|body|any|false|none|
|»»» *anonymous*|body|string(date-time)|false|none|
|»»» *anonymous*|body|string(date)|false|none|
|»» delete|body|boolean|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» primary_status|ACTIVE|
|» primary_status|CLOSED|
|»»» *anonymous*|FORGIVEN|
|»»» *anonymous*|PAID OFF|
|»»» *anonymous*|NON-ACCRUAL|
|»»» *anonymous*|GL CHARGE OFF|
|»»» *anonymous*|CANCELED (REFUND)|
|»»» *anonymous*|CANCELED (UNWIND)|
|»»» *anonymous*|FULLY PAID (MERCHANT)|
|»»» *anonymous*|SOLD DEBT|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678"
}
```

<h4 id="post__loan_status_update-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_status_update-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_group

> Code samples

```shell
# You can also use wget
curl -X POST /loan/group \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 8063f86c-b6d3-4e82-adbb-fc44d2f23d6e' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/group HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 8063f86c-b6d3-4e82-adbb-fc44d2f23d6e
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "TL12345678",
  "group_no": 3,
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'8063f86c-b6d3-4e82-adbb-fc44d2f23d6e',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/group',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '8063f86c-b6d3-4e82-adbb-fc44d2f23d6e',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/group',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '8063f86c-b6d3-4e82-adbb-fc44d2f23d6e',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/group', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '8063f86c-b6d3-4e82-adbb-fc44d2f23d6e',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/group', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/group");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"8063f86c-b6d3-4e82-adbb-fc44d2f23d6e"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/group", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/group`

Change loan group no

> Body parameter

```json
{
  "loan_id": "TL12345678",
  "group_no": 3,
  "dry_run": null
}
```

<h4 id="post__loan_group-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» group_no|body|integer|true|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678"
}
```

<h4 id="post__loan_group-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_group-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="up-svc-ls-payment-transaction">Payment/Transaction</h2>

Operations that read/write payments or transactions

### post__loan_interest_adjust

> Code samples

```shell
# You can also use wget
curl -X POST /loan/interest/adjust \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 3311bb38-3874-4efe-9f47-6f890e13f9bb' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/interest/adjust HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 3311bb38-3874-4efe-9f47-6f890e13f9bb
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "amount": "3.495",
  "effective_date": "2022-01-17",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'3311bb38-3874-4efe-9f47-6f890e13f9bb',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/interest/adjust',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '3311bb38-3874-4efe-9f47-6f890e13f9bb',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/interest/adjust',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '3311bb38-3874-4efe-9f47-6f890e13f9bb',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/interest/adjust', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '3311bb38-3874-4efe-9f47-6f890e13f9bb',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/interest/adjust', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/interest/adjust");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"3311bb38-3874-4efe-9f47-6f890e13f9bb"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/interest/adjust", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/interest/adjust`

Adjust the interest balance of a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "amount": "3.495",
  "effective_date": "2022-01-17",
  "dry_run": null
}
```

<h4 id="post__loan_interest_adjust-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» adjustment|body|number|true|none|
|» date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "TL12345678"
}
```

<h4 id="post__loan_interest_adjust-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_interest_adjust-responseschema">Response Schema</h4>

Status Code **200**

*AdjustInterestResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__payment_reverse

> Code samples

```shell
# You can also use wget
curl -X POST /payment/reverse \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: fa041303-8ffa-4bf7-989e-913a33e8de0c' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /payment/reverse HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: fa041303-8ffa-4bf7-989e-913a33e8de0c
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "amount": 12593,
  "invoice_id": "T12345678-2",
  "date_paid": "2022-01-17",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'fa041303-8ffa-4bf7-989e-913a33e8de0c',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/payment/reverse',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'fa041303-8ffa-4bf7-989e-913a33e8de0c',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/payment/reverse',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'fa041303-8ffa-4bf7-989e-913a33e8de0c',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/payment/reverse', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'fa041303-8ffa-4bf7-989e-913a33e8de0c',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/payment/reverse', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/payment/reverse");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"fa041303-8ffa-4bf7-989e-913a33e8de0c"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/payment/reverse", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /payment/reverse`

Reverse a payment on a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "amount": 12593,
  "invoice_id": "T12345678-2",
  "date_paid": "2022-01-17",
  "dry_run": null
}
```

<h4 id="post__payment_reverse-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» amount|body|integer|true|none|
|» invoice_id|body|string|true|none|
|» date_paid|body|any|false|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» row_id|body|integer|false|none|
|» dry_run|body|boolean|false|none|
|» charge_id|body|string|false|none|
|» external_id|body|string|false|none|
|» servicer_name|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678",
  "invoice_id": "T12345678-2"
}
```

<h4 id="post__payment_reverse-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__payment_reverse-responseschema">Response Schema</h4>

Status Code **200**

*ReverseResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» invoice_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__payment_defer

> Code samples

```shell
# You can also use wget
curl -X POST /payment/defer \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 1b1a6b4f-ce63-4f4b-847e-dff21a7c78e0' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /payment/defer HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 1b1a6b4f-ce63-4f4b-847e-dff21a7c78e0
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "TL12345678",
  "payment_numbers": [
    3,
    4
  ],
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'1b1a6b4f-ce63-4f4b-847e-dff21a7c78e0',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/payment/defer',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '1b1a6b4f-ce63-4f4b-847e-dff21a7c78e0',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/payment/defer',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '1b1a6b4f-ce63-4f4b-847e-dff21a7c78e0',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/payment/defer', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '1b1a6b4f-ce63-4f4b-847e-dff21a7c78e0',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/payment/defer', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/payment/defer");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"1b1a6b4f-ce63-4f4b-847e-dff21a7c78e0"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/payment/defer", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /payment/defer`

Defer payments on a loan

> Body parameter

```json
{
  "loan_id": "TL12345678",
  "payment_numbers": [
    3,
    4
  ],
  "dry_run": null
}
```

<h4 id="post__payment_defer-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» payment_numbers|body|[integer]|true|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "TL12345678",
  "payment_numbers": [
    3,
    4
  ]
}
```

<h4 id="post__payment_defer-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__payment_defer-responseschema">Response Schema</h4>

Status Code **200**

*DeferResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» payment_numbers|[integer]|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__transaction_create

> Code samples

```shell
# You can also use wget
curl -X POST /transaction/create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 18c2d29a-8c12-4218-8a80-1464aa02c4c3' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /transaction/create HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 18c2d29a-8c12-4218-8a80-1464aa02c4c3
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "effective_date": "2022-01-17",
  "transaction_type": "principal-advance",
  "amount": 10000,
  "payment_method": "card-stripe",
  "external_id": "ch_1ee2417e694e745f7b7c51e8bfbb8cfc3",
  "external_source": "FCS",
  "due_date": "2022-01-18",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'18c2d29a-8c12-4218-8a80-1464aa02c4c3',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/transaction/create',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '18c2d29a-8c12-4218-8a80-1464aa02c4c3',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/transaction/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '18c2d29a-8c12-4218-8a80-1464aa02c4c3',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/transaction/create', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '18c2d29a-8c12-4218-8a80-1464aa02c4c3',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/transaction/create', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/transaction/create");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"18c2d29a-8c12-4218-8a80-1464aa02c4c3"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/transaction/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /transaction/create`

Create a transaction on a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "effective_date": "2022-01-17",
  "transaction_type": "principal-advance",
  "amount": 10000,
  "payment_method": "card-stripe",
  "external_id": "ch_1ee2417e694e745f7b7c51e8bfbb8cfc3",
  "external_source": "FCS",
  "due_date": "2022-01-18",
  "dry_run": null
}
```

<h4 id="post__transaction_create-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» effective_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» transaction_type|body|string|true|An enumeration.|
|» amount|body|integer|true|none|
|» payment_method|body|string|false|An enumeration.|
|» invoice_id|body|string|false|none|
|» external_id|body|string|false|none|
|» external_source|body|string|false|none|
|» servicer_name|body|string|false|none|
|» due_date|body|any|false|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» transaction_type|principal-advance|
|» transaction_type|principal-and-interest-billing|
|» transaction_type|amortized-income-fee|
|» transaction_type|amortization-of-income-fee|
|» transaction_type|pi-principal-payment|
|» transaction_type|pi-interest-payment|
|» transaction_type|principal-reduction|
|» transaction_type|interest-reduction|
|» transaction_type|capitalize-overpaid-interest|
|» transaction_type|write-off-principal|
|» transaction_type|write-off-interest|
|» transaction_type|write-off-suspense|
|» transaction_type|suspense|
|» transaction_type|suspense-refund|
|» transaction_type|origination-fee|
|» transaction_type|subvention-refund|
|» transaction_type|refund-paid-interest|
|» transaction_type|refund-paid-origination-fee|
|» transaction_type|charge-off-balance|
|» transaction_type|sale-post-charge-off|
|» transaction_type|write-off-principal-post-charge-off|
|» transaction_type|write-off-interest-post-charge-off|
|» transaction_type|restructure-principal-transfer|
|» transaction_type|restructure-interest-transfer|
|» payment_method|Check|
|» payment_method|ach|
|» payment_method|card|
|» payment_method|ach-chase|
|» payment_method|card-chase|
|» payment_method|credit-from-wex|
|» payment_method|unused-funds|
|» payment_method|card-stripe|
|» payment_method|ach-stripe|
|» payment_method|credit-from-uatp|
|» payment_method|card-wells-fargo|
|» payment_method|ffam-fee|
|» payment_method|ffam|
|» payment_method|credit-from-stripe|
|» payment_method|ach-bmo|
|» payment_method|zelle|
|» payment_method|sale-post-charge-off|
|» payment_method|nlex-fee|
|» payment_method|trueaccord|
|» payment_method|trueaccord-fee|
|» payment_method|credit-wire-receipt|

> Example responses

> 200 Response

```json
{
  "loan_id": "TL12345678"
}
```

<h4 id="post__transaction_create-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__transaction_create-responseschema">Response Schema</h4>

Status Code **200**

*CreateResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__payment_delay

> Code samples

```shell
# You can also use wget
curl -X POST /payment/delay \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: f3f09607-6b26-4a73-93ca-45a06bd0fe7d' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /payment/delay HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: f3f09607-6b26-4a73-93ca-45a06bd0fe7d
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "old_due_date": "2022-01-18",
  "new_due_date": "2022-01-20",
  "amount": 7500,
  "effective_date": "2022-01-17"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'f3f09607-6b26-4a73-93ca-45a06bd0fe7d',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/payment/delay',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'f3f09607-6b26-4a73-93ca-45a06bd0fe7d',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/payment/delay',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'f3f09607-6b26-4a73-93ca-45a06bd0fe7d',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/payment/delay', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'f3f09607-6b26-4a73-93ca-45a06bd0fe7d',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/payment/delay', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/payment/delay");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"f3f09607-6b26-4a73-93ca-45a06bd0fe7d"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/payment/delay", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /payment/delay`

Delays a payment by updating billing due date

> Body parameter

```json
{
  "loan_id": "T12345678",
  "old_due_date": "2022-01-18",
  "new_due_date": "2022-01-20",
  "amount": 7500,
  "effective_date": "2022-01-17"
}
```

<h4 id="post__payment_delay-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» effective_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» amount|body|integer|true|none|
|» old_due_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» new_due_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» dry_run|body|boolean|false|none|
|» payment_id|body|integer|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678"
}
```

<h4 id="post__payment_delay-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__payment_delay-responseschema">Response Schema</h4>

Status Code **200**

*DelayResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__transaction_reverse

> Code samples

```shell
# You can also use wget
curl -X POST /transaction/reverse \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: ac509e94-88bb-42b0-ae2a-1a147c904725' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /transaction/reverse HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: ac509e94-88bb-42b0-ae2a-1a147c904725
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "effective_date": "2022-01-17",
  "transaction_date": "2022-01-17",
  "transaction_type": "principal-advance",
  "amount": 10000,
  "payment_method": "card-stripe",
  "invoice_id": "T12345678-2",
  "external_id": "",
  "external_source": "FCS",
  "servicer_name": "FFAM",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'ac509e94-88bb-42b0-ae2a-1a147c904725',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/transaction/reverse',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'ac509e94-88bb-42b0-ae2a-1a147c904725',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/transaction/reverse',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'ac509e94-88bb-42b0-ae2a-1a147c904725',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/transaction/reverse', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'ac509e94-88bb-42b0-ae2a-1a147c904725',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/transaction/reverse', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/transaction/reverse");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"ac509e94-88bb-42b0-ae2a-1a147c904725"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/transaction/reverse", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /transaction/reverse`

Reverse a transaction on a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "effective_date": "2022-01-17",
  "transaction_date": "2022-01-17",
  "transaction_type": "principal-advance",
  "amount": 10000,
  "payment_method": "card-stripe",
  "invoice_id": "T12345678-2",
  "external_id": "",
  "external_source": "FCS",
  "servicer_name": "FFAM",
  "dry_run": null
}
```

<h4 id="post__transaction_reverse-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» effective_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» transaction_type|body|string|true|An enumeration.|
|» amount|body|integer|true|none|
|» transaction_id|body|integer|false|none|
|» transaction_date|body|any|false|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» row_id|body|integer|false|none|
|» due_date|body|any|false|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» payment_method|body|string|false|An enumeration.|
|» invoice_id|body|string|false|none|
|» external_id|body|string|false|none|
|» external_source|body|string|false|none|
|» servicer_name|body|string|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» transaction_type|principal-advance|
|» transaction_type|principal-and-interest-billing|
|» transaction_type|amortized-income-fee|
|» transaction_type|amortization-of-income-fee|
|» transaction_type|pi-principal-payment|
|» transaction_type|pi-interest-payment|
|» transaction_type|principal-reduction|
|» transaction_type|interest-reduction|
|» transaction_type|capitalize-overpaid-interest|
|» transaction_type|write-off-principal|
|» transaction_type|write-off-interest|
|» transaction_type|write-off-suspense|
|» transaction_type|suspense|
|» transaction_type|suspense-refund|
|» transaction_type|origination-fee|
|» transaction_type|subvention-refund|
|» transaction_type|refund-paid-interest|
|» transaction_type|refund-paid-origination-fee|
|» transaction_type|charge-off-balance|
|» transaction_type|sale-post-charge-off|
|» transaction_type|write-off-principal-post-charge-off|
|» transaction_type|write-off-interest-post-charge-off|
|» transaction_type|restructure-principal-transfer|
|» transaction_type|restructure-interest-transfer|
|» payment_method|Check|
|» payment_method|ach|
|» payment_method|card|
|» payment_method|ach-chase|
|» payment_method|card-chase|
|» payment_method|credit-from-wex|
|» payment_method|unused-funds|
|» payment_method|card-stripe|
|» payment_method|ach-stripe|
|» payment_method|credit-from-uatp|
|» payment_method|card-wells-fargo|
|» payment_method|ffam-fee|
|» payment_method|ffam|
|» payment_method|credit-from-stripe|
|» payment_method|ach-bmo|
|» payment_method|zelle|
|» payment_method|sale-post-charge-off|
|» payment_method|nlex-fee|
|» payment_method|trueaccord|
|» payment_method|trueaccord-fee|
|» payment_method|credit-wire-receipt|

> Example responses

> 200 Response

```json
{
  "loan_id": "TL12345678"
}
```

<h4 id="post__transaction_reverse-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__transaction_reverse-responseschema">Response Schema</h4>

Status Code **200**

*ReverseResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__payment_create

> Code samples

```shell
# You can also use wget
curl -X POST /payment/create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 8d08bb21-9bb3-474e-9ccf-a47e30c0afd3' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /payment/create HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 8d08bb21-9bb3-474e-9ccf-a47e30c0afd3
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "invoice_id": "T12345678-2",
  "amount": 12593,
  "effective_date": "2022-01-17",
  "payment_method": "card-stripe",
  "external_id": "ch_1ee2417e694e745f7b7c51e8bfbb8cfc3",
  "external_source": "FCS",
  "servicer_name": "Uplift",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'8d08bb21-9bb3-474e-9ccf-a47e30c0afd3',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/payment/create',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '8d08bb21-9bb3-474e-9ccf-a47e30c0afd3',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/payment/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '8d08bb21-9bb3-474e-9ccf-a47e30c0afd3',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/payment/create', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '8d08bb21-9bb3-474e-9ccf-a47e30c0afd3',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/payment/create', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/payment/create");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"8d08bb21-9bb3-474e-9ccf-a47e30c0afd3"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/payment/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /payment/create`

Create a payment on a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "invoice_id": "T12345678-2",
  "amount": 12593,
  "effective_date": "2022-01-17",
  "payment_method": "card-stripe",
  "external_id": "ch_1ee2417e694e745f7b7c51e8bfbb8cfc3",
  "external_source": "FCS",
  "servicer_name": "Uplift",
  "dry_run": null
}
```

<h4 id="post__payment_create-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» amount|body|integer|true|none|
|» effective_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» payment_method|body|string|true|An enumeration.|
|» invoice_id|body|string|false|none|
|» external_id|body|string|false|none|
|» external_source|body|string|false|none|
|» servicer_name|body|string|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» payment_method|Check|
|» payment_method|ach|
|» payment_method|card|
|» payment_method|ach-chase|
|» payment_method|card-chase|
|» payment_method|credit-from-wex|
|» payment_method|unused-funds|
|» payment_method|card-stripe|
|» payment_method|ach-stripe|
|» payment_method|credit-from-uatp|
|» payment_method|card-wells-fargo|
|» payment_method|ffam-fee|
|» payment_method|ffam|
|» payment_method|credit-from-stripe|
|» payment_method|ach-bmo|
|» payment_method|zelle|
|» payment_method|sale-post-charge-off|
|» payment_method|nlex-fee|
|» payment_method|trueaccord|
|» payment_method|trueaccord-fee|
|» payment_method|credit-wire-receipt|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678",
  "invoice_id": "T12345678-2"
}
```

<h4 id="post__payment_create-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__payment_create-responseschema">Response Schema</h4>

Status Code **200**

*CreateResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» invoice_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_billings_delete

> Code samples

```shell
# You can also use wget
curl -X POST /loan/billings/delete \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 6e73a9f9-ec9e-47ad-aa55-ed265cfc9b6e' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/billings/delete HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 6e73a9f9-ec9e-47ad-aa55-ed265cfc9b6e
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "skip_billings": [
    3,
    4
  ],
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'6e73a9f9-ec9e-47ad-aa55-ed265cfc9b6e',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/billings/delete',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '6e73a9f9-ec9e-47ad-aa55-ed265cfc9b6e',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/billings/delete',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '6e73a9f9-ec9e-47ad-aa55-ed265cfc9b6e',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/billings/delete', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '6e73a9f9-ec9e-47ad-aa55-ed265cfc9b6e',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/billings/delete', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/billings/delete");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"6e73a9f9-ec9e-47ad-aa55-ed265cfc9b6e"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/billings/delete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/billings/delete`

Delete outstanding billings on a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "skip_billings": [
    3,
    4
  ],
  "dry_run": null
}
```

<h4 id="post__loan_billings_delete-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» skip_billings|body|[integer]|false|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678",
  "billings_deleted": [
    {
      "loan_id": "T12345678",
      "due_date": "2022-01-17",
      "amount": 7500,
      "amount_remaining": 7500,
      "payment_number": 3
    }
  ]
}
```

<h4 id="post__loan_billings_delete-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_billings_delete-responseschema">Response Schema</h4>

Status Code **200**

*DeleteBillingsResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» billings_deleted|[object]|false|none|none|
|»» DeletedBilling|object|false|none|none|
|»»» loan_id|string|false|none|none|
|»»» due_date|any|false|none|none|

*anyOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|string(date-time)|false|none|none|

*or*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»»» *anonymous*|string(date)|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»»» amount|integer|false|none|none|
|»»» amount_remaining|integer|false|none|none|
|»»» payment_number|integer|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="up-svc-ls-subvention">Subvention</h2>

Operations related to subvention (some temporary)

### post__loan_subsidy_create

> Code samples

```shell
# You can also use wget
curl -X POST /loan/subsidy/create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 9fb15bcd-eb19-4d63-b915-e303de5de8dc' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/subsidy/create HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 9fb15bcd-eb19-4d63-b915-e303de5de8dc
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "force_create": false,
  "loan_id": "TL4135193",
  "balance": 244986,
  "start_date": "2022-01-17"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'9fb15bcd-eb19-4d63-b915-e303de5de8dc',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/subsidy/create',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '9fb15bcd-eb19-4d63-b915-e303de5de8dc',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/subsidy/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '9fb15bcd-eb19-4d63-b915-e303de5de8dc',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/subsidy/create', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '9fb15bcd-eb19-4d63-b915-e303de5de8dc',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/subsidy/create', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/subsidy/create");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"9fb15bcd-eb19-4d63-b915-e303de5de8dc"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/subsidy/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/subsidy/create`

Updates a loan to add a subsidy

> Body parameter

```json
{
  "force_create": false,
  "loan_id": "TL4135193",
  "balance": 244986,
  "start_date": "2022-01-17"
}
```

<h4 id="post__loan_subsidy_create-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|[LoanSubsidyCreateRequest](#schemaloansubsidycreaterequest)|false|none|

> Example responses

> 200 Response

```json
{
  "error": "Loan not found",
  "loan_id": "TL4135193"
}
```

<h4 id="post__loan_subsidy_create-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The general response for creating subsidy|[LoanSubsidyCreateResponse](#schemaloansubsidycreateresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Failed when writing to NLS|[LoanSubsidyCreateResponse](#schemaloansubsidycreateresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Loan does not exist|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

### get__loan_subsidy_refund_implicit

> Code samples

```shell
# You can also use wget
curl -X GET /loan/subsidy/refund/implicit \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 6fab9713-a725-473b-8cb2-66a280c53a50' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
GET /loan/subsidy/refund/implicit HTTP/1.1

Accept: application/json
x-up-correlation-id: 6fab9713-a725-473b-8cb2-66a280c53a50
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-up-correlation-id':'6fab9713-a725-473b-8cb2-66a280c53a50',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/subsidy/refund/implicit',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-up-correlation-id' => '6fab9713-a725-473b-8cb2-66a280c53a50',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.get '/loan/subsidy/refund/implicit',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-up-correlation-id': '6fab9713-a725-473b-8cb2-66a280c53a50',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.get('/loan/subsidy/refund/implicit', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-up-correlation-id' => '6fab9713-a725-473b-8cb2-66a280c53a50',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/loan/subsidy/refund/implicit', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/subsidy/refund/implicit");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"6fab9713-a725-473b-8cb2-66a280c53a50"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/loan/subsidy/refund/implicit", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /loan/subsidy/refund/implicit`

Gets subvented loans for implicit refunding, will not include loans with 191 subsidy reversal

<h4 id="get__loan_subsidy_refund_implicit-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "transactions": [
      {
        "transaction_id": 0,
        "effective_date": "2019-08-24",
        "error": [
          "string"
        ],
        "loan_id": "string",
        "transaction_date": "2019-08-24",
        "transaction_amount": 0,
        "transaction_code": 0,
        "payment_method_no": 0
      }
    ],
    "secondary_status": "string",
    "open_date": "2019-08-24",
    "original_note_amount": 0,
    "error": [
      "string"
    ],
    "loan_id": "string",
    "current_payoff_balance": 0,
    "term": 0,
    "current_principal_balance": 0,
    "open_maturity_date": "2019-08-24",
    "primary_status": "string"
  }
]
```

<h4 id="get__loan_subsidy_refund_implicit-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The list of subvented loans|Inline|

<h4 id="get__loan_subsidy_refund_implicit-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SubsidyLoan](#schemasubsidyloan)]|false|none|none|
|» transactions|[[SubsidyTransaction](#schemasubsidytransaction)]|false|none|none|
|»» transaction_id|integer(int32)|false|none|none|
|»» effective_date|string(date)|false|none|none|
|»» error|[string]|false|none|none|
|»» loan_id|string|true|none|none|
|»» transaction_date|string(date)|false|none|none|
|»» transaction_amount|integer(int32)|false|none|none|
|»» transaction_code|integer(int32)|false|none|none|
|»» payment_method_no|integer(int32)|false|none|none|
|» secondary_status|string|false|none|none|
|» open_date|string(date)|false|none|none|
|» original_note_amount|integer(int32)|false|none|none|
|» error|[string]|false|none|none|
|» loan_id|string|true|none|none|
|» current_payoff_balance|integer(int32)|false|none|none|
|» term|integer(int32)|false|none|none|
|» current_principal_balance|integer(int32)|false|none|none|
|» open_maturity_date|string(date)|false|none|none|
|» primary_status|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_subsidy_refund_implicit

> Code samples

```shell
# You can also use wget
curl -X POST /loan/subsidy/refund/implicit \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: e860e2bd-fcac-41a7-b909-bb7e83eee1df' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/subsidy/refund/implicit HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: e860e2bd-fcac-41a7-b909-bb7e83eee1df
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "date": "2022-01-17",
  "loan_id": "TL4135193",
  "transaction_id": 1501,
  "amount": 66671
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'e860e2bd-fcac-41a7-b909-bb7e83eee1df',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/subsidy/refund/implicit',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'e860e2bd-fcac-41a7-b909-bb7e83eee1df',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/subsidy/refund/implicit',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'e860e2bd-fcac-41a7-b909-bb7e83eee1df',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/subsidy/refund/implicit', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'e860e2bd-fcac-41a7-b909-bb7e83eee1df',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/subsidy/refund/implicit', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/subsidy/refund/implicit");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"e860e2bd-fcac-41a7-b909-bb7e83eee1df"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/subsidy/refund/implicit", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/subsidy/refund/implicit`

Implicit refund for subsidy (reopen, transaction codes 191, close)

> Body parameter

```json
{
  "date": "2022-01-17",
  "loan_id": "TL4135193",
  "transaction_id": 1501,
  "amount": 66671
}
```

<h4 id="post__loan_subsidy_refund_implicit-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|[LoanSubsidyRefundImplicitRequest](#schemaloansubsidyrefundimplicitrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "error": "Loan not found",
  "loan_id": "TL4135193"
}
```

<h4 id="post__loan_subsidy_refund_implicit-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The general response for implicitly refunding subsidy|[LoanSubsidyRefundImplicitResponse](#schemaloansubsidyrefundimplicitresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Failed when writing to NLS|[LoanSubsidyRefundImplicitResponse](#schemaloansubsidyrefundimplicitresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Loan does not exist|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

### get__loan_subsidy_refund_explicit

> Code samples

```shell
# You can also use wget
curl -X GET /loan/subsidy/refund/explicit \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 14979d12-560b-4206-9a68-b1e944e1f519' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
GET /loan/subsidy/refund/explicit HTTP/1.1

Accept: application/json
x-up-correlation-id: 14979d12-560b-4206-9a68-b1e944e1f519
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-up-correlation-id':'14979d12-560b-4206-9a68-b1e944e1f519',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/subsidy/refund/explicit',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-up-correlation-id' => '14979d12-560b-4206-9a68-b1e944e1f519',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.get '/loan/subsidy/refund/explicit',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-up-correlation-id': '14979d12-560b-4206-9a68-b1e944e1f519',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.get('/loan/subsidy/refund/explicit', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-up-correlation-id' => '14979d12-560b-4206-9a68-b1e944e1f519',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/loan/subsidy/refund/explicit', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/subsidy/refund/explicit");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"14979d12-560b-4206-9a68-b1e944e1f519"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/loan/subsidy/refund/explicit", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /loan/subsidy/refund/explicit`

Gets subvented loans for explicit refunding, will not include loans with 510 refund transaction

<h4 id="get__loan_subsidy_refund_explicit-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "transactions": [
      {
        "transaction_id": 0,
        "effective_date": "2019-08-24",
        "error": [
          "string"
        ],
        "loan_id": "string",
        "transaction_date": "2019-08-24",
        "transaction_amount": 0,
        "transaction_code": 0,
        "payment_method_no": 0
      }
    ],
    "secondary_status": "string",
    "open_date": "2019-08-24",
    "original_note_amount": 0,
    "error": [
      "string"
    ],
    "loan_id": "string",
    "current_payoff_balance": 0,
    "term": 0,
    "current_principal_balance": 0,
    "open_maturity_date": "2019-08-24",
    "primary_status": "string"
  }
]
```

<h4 id="get__loan_subsidy_refund_explicit-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The list of subvented loans|Inline|

<h4 id="get__loan_subsidy_refund_explicit-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SubsidyLoan](#schemasubsidyloan)]|false|none|none|
|» transactions|[[SubsidyTransaction](#schemasubsidytransaction)]|false|none|none|
|»» transaction_id|integer(int32)|false|none|none|
|»» effective_date|string(date)|false|none|none|
|»» error|[string]|false|none|none|
|»» loan_id|string|true|none|none|
|»» transaction_date|string(date)|false|none|none|
|»» transaction_amount|integer(int32)|false|none|none|
|»» transaction_code|integer(int32)|false|none|none|
|»» payment_method_no|integer(int32)|false|none|none|
|» secondary_status|string|false|none|none|
|» open_date|string(date)|false|none|none|
|» original_note_amount|integer(int32)|false|none|none|
|» error|[string]|false|none|none|
|» loan_id|string|true|none|none|
|» current_payoff_balance|integer(int32)|false|none|none|
|» term|integer(int32)|false|none|none|
|» current_principal_balance|integer(int32)|false|none|none|
|» open_maturity_date|string(date)|false|none|none|
|» primary_status|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_subsidy_refund_explicit

> Code samples

```shell
# You can also use wget
curl -X POST /loan/subsidy/refund/explicit \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 58f18068-eff0-4961-ab17-062de8aeed6c' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/subsidy/refund/explicit HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 58f18068-eff0-4961-ab17-062de8aeed6c
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "date": "2022-01-17",
  "loan_id": "TL4135193",
  "amount": 66671,
  "force_create": false
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'58f18068-eff0-4961-ab17-062de8aeed6c',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/subsidy/refund/explicit',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '58f18068-eff0-4961-ab17-062de8aeed6c',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/subsidy/refund/explicit',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '58f18068-eff0-4961-ab17-062de8aeed6c',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/subsidy/refund/explicit', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '58f18068-eff0-4961-ab17-062de8aeed6c',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/subsidy/refund/explicit', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/subsidy/refund/explicit");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"58f18068-eff0-4961-ab17-062de8aeed6c"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/subsidy/refund/explicit", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/subsidy/refund/explicit`

Explicit refund for subsidy (reopen, transaction code 510, close)

> Body parameter

```json
{
  "date": "2022-01-17",
  "loan_id": "TL4135193",
  "amount": 66671,
  "force_create": false
}
```

<h4 id="post__loan_subsidy_refund_explicit-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|[LoanSubsidyRefundExplicitRequest](#schemaloansubsidyrefundexplicitrequest)|false|none|

> Example responses

> 200 Response

```json
{
  "error": "Loan not found",
  "loan_id": "TL4135193"
}
```

<h4 id="post__loan_subsidy_refund_explicit-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The general response for explicitly refunding subsidy|[LoanSubsidyRefundExplicitResponse](#schemaloansubsidyrefundexplicitresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Failed when writing to NLS|[LoanSubsidyRefundExplicitResponse](#schemaloansubsidyrefundexplicitresponse)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Loan does not exist|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

### get__loans_subsidy

> Code samples

```shell
# You can also use wget
curl -X GET /loans/subsidy \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: cf35d617-9238-49f6-bc07-c7d6703b4dc4' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
GET /loans/subsidy HTTP/1.1

Accept: application/json
x-up-correlation-id: cf35d617-9238-49f6-bc07-c7d6703b4dc4
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-up-correlation-id':'cf35d617-9238-49f6-bc07-c7d6703b4dc4',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loans/subsidy',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'cf35d617-9238-49f6-bc07-c7d6703b4dc4',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.get '/loans/subsidy',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-up-correlation-id': 'cf35d617-9238-49f6-bc07-c7d6703b4dc4',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.get('/loans/subsidy', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'cf35d617-9238-49f6-bc07-c7d6703b4dc4',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/loans/subsidy', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loans/subsidy");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"cf35d617-9238-49f6-bc07-c7d6703b4dc4"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/loans/subsidy", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /loans/subsidy`

Get loans with subsidy

<h4 id="get__loans_subsidy-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|

> Example responses

> 200 Response

```json
[
  {
    "transactions": [
      {
        "transaction_id": 0,
        "effective_date": "2019-08-24",
        "error": [
          "string"
        ],
        "loan_id": "string",
        "transaction_date": "2019-08-24",
        "transaction_amount": 0,
        "transaction_code": 0,
        "payment_method_no": 0
      }
    ],
    "secondary_status": "string",
    "open_date": "2019-08-24",
    "original_note_amount": 0,
    "error": [
      "string"
    ],
    "loan_id": "string",
    "current_payoff_balance": 0,
    "term": 0,
    "current_principal_balance": 0,
    "open_maturity_date": "2019-08-24",
    "primary_status": "string"
  }
]
```

<h4 id="get__loans_subsidy-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The subvented loans|Inline|

<h4 id="get__loans_subsidy-responseschema">Response Schema</h4>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SubsidyLoan](#schemasubsidyloan)]|false|none|none|
|» transactions|[[SubsidyTransaction](#schemasubsidytransaction)]|false|none|none|
|»» transaction_id|integer(int32)|false|none|none|
|»» effective_date|string(date)|false|none|none|
|»» error|[string]|false|none|none|
|»» loan_id|string|true|none|none|
|»» transaction_date|string(date)|false|none|none|
|»» transaction_amount|integer(int32)|false|none|none|
|»» transaction_code|integer(int32)|false|none|none|
|»» payment_method_no|integer(int32)|false|none|none|
|» secondary_status|string|false|none|none|
|» open_date|string(date)|false|none|none|
|» original_note_amount|integer(int32)|false|none|none|
|» error|[string]|false|none|none|
|» loan_id|string|true|none|none|
|» current_payoff_balance|integer(int32)|false|none|none|
|» term|integer(int32)|false|none|none|
|» current_principal_balance|integer(int32)|false|none|none|
|» open_maturity_date|string(date)|false|none|none|
|» primary_status|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### get__loan_{loan_id}_subsidy

> Code samples

```shell
# You can also use wget
curl -X GET /loan/{loan_id}/subsidy \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 66248ab0-1cdf-4d09-b516-a02363b729ca' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
GET /loan/{loan_id}/subsidy HTTP/1.1

Accept: application/json
x-up-correlation-id: 66248ab0-1cdf-4d09-b516-a02363b729ca
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-up-correlation-id':'66248ab0-1cdf-4d09-b516-a02363b729ca',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/{loan_id}/subsidy',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-up-correlation-id' => '66248ab0-1cdf-4d09-b516-a02363b729ca',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.get '/loan/{loan_id}/subsidy',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-up-correlation-id': '66248ab0-1cdf-4d09-b516-a02363b729ca',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.get('/loan/{loan_id}/subsidy', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-up-correlation-id' => '66248ab0-1cdf-4d09-b516-a02363b729ca',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/loan/{loan_id}/subsidy', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/{loan_id}/subsidy");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"66248ab0-1cdf-4d09-b516-a02363b729ca"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/loan/{loan_id}/subsidy", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /loan/{loan_id}/subsidy`

Get loan with transactions with subsidy

<h4 id="get__loan_{loan_id}_subsidy-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|loan_id|path|string|true|none|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|

> Example responses

> 200 Response

```json
{
  "transactions": [
    {
      "transaction_id": 0,
      "effective_date": "2019-08-24",
      "error": [
        "string"
      ],
      "loan_id": "string",
      "transaction_date": "2019-08-24",
      "transaction_amount": 0,
      "transaction_code": 0,
      "payment_method_no": 0
    }
  ],
  "secondary_status": "string",
  "open_date": "2019-08-24",
  "original_note_amount": 0,
  "error": [
    "string"
  ],
  "loan_id": "string",
  "current_payoff_balance": 0,
  "term": 0,
  "current_principal_balance": 0,
  "open_maturity_date": "2019-08-24",
  "primary_status": "string"
}
```

<h4 id="get__loan_{loan_id}_subsidy-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The subvented loan|[SubsidyLoan](#schemasubsidyloan)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Loan does not exist|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="up-svc-ls-development">Development</h2>

Tools useful for testing or during development

### post__accrual_status

> Code samples

```shell
# You can also use wget
curl -X POST /accrual/status \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: fbae7698-c8c5-4143-abf5-f49f4b8426f8' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /accrual/status HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: fbae7698-c8c5-4143-abf5-f49f4b8426f8
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "accrual_date": "2022-01-16"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'fbae7698-c8c5-4143-abf5-f49f4b8426f8',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/accrual/status',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'fbae7698-c8c5-4143-abf5-f49f4b8426f8',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/accrual/status',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'fbae7698-c8c5-4143-abf5-f49f4b8426f8',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/accrual/status', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'fbae7698-c8c5-4143-abf5-f49f4b8426f8',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/accrual/status', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accrual/status");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"fbae7698-c8c5-4143-abf5-f49f4b8426f8"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/accrual/status", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /accrual/status`

Get Accrual Status- active loans accrued through

> Body parameter

```json
{
  "accrual_date": "2022-01-16"
}
```

<h4 id="post__accrual_status-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» accrual_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|

> Example responses

> 200 Response

```json
{
  "count_loans_remaining": 0,
  "count_loans_active": 1000
}
```

<h4 id="post__accrual_status-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__accrual_status-responseschema">Response Schema</h4>

Status Code **200**

*AccrualStatusResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» count_loans_remaining|integer|false|none|none|
|» count_loans_active|integer|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__loan_accrue

> Code samples

```shell
# You can also use wget
curl -X POST /loan/accrue \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: e2682c6f-e652-48d1-9f34-de101454acb7' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /loan/accrue HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: e2682c6f-e652-48d1-9f34-de101454acb7
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loan_id": "T12345678",
  "through_date": "2022-01-18T20:57:12.145227Z",
  "dry_run": null
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'e2682c6f-e652-48d1-9f34-de101454acb7',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/loan/accrue',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'e2682c6f-e652-48d1-9f34-de101454acb7',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/loan/accrue',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'e2682c6f-e652-48d1-9f34-de101454acb7',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/loan/accrue', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'e2682c6f-e652-48d1-9f34-de101454acb7',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/loan/accrue', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/loan/accrue");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"e2682c6f-e652-48d1-9f34-de101454acb7"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/loan/accrue", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /loan/accrue`

Accrues a loan

> Body parameter

```json
{
  "loan_id": "T12345678",
  "through_date": "2022-01-18T20:57:12.145227Z",
  "dry_run": null
}
```

<h4 id="post__loan_accrue-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loan_id|body|string|true|none|
|» through_date|body|any|false|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_id": "T12345678"
}
```

<h4 id="post__loan_accrue-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__loan_accrue-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_id|string|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__accrual_loans

> Code samples

```shell
# You can also use wget
curl -X POST /accrual/loans \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: ad8e289a-0e9f-4543-a44a-0f1b3688d53d' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /accrual/loans HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: ad8e289a-0e9f-4543-a44a-0f1b3688d53d
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "accrual_date": "2022-01-16"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'ad8e289a-0e9f-4543-a44a-0f1b3688d53d',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/accrual/loans',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => 'ad8e289a-0e9f-4543-a44a-0f1b3688d53d',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/accrual/loans',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': 'ad8e289a-0e9f-4543-a44a-0f1b3688d53d',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/accrual/loans', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => 'ad8e289a-0e9f-4543-a44a-0f1b3688d53d',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/accrual/loans', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/accrual/loans");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"ad8e289a-0e9f-4543-a44a-0f1b3688d53d"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/accrual/loans", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /accrual/loans`

Get Accrual Status- active loans accrued through

> Body parameter

```json
{
  "accrual_date": "2022-01-16"
}
```

<h4 id="post__accrual_loans-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» accrual_date|body|any|true|none|
|»» *anonymous*|body|string(date-time)|false|none|
|»» *anonymous*|body|string(date)|false|none|

> Example responses

> 200 Response

```json
{
  "loan_ids": [
    "SA12345"
  ]
}
```

<h4 id="post__accrual_loans-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__accrual_loans-responseschema">Response Schema</h4>

Status Code **200**

*AccrualLoansResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_ids|[string]|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="up-svc-ls-batch">Batch</h2>

Atomic bulk operations

### post__batch_loans_group

> Code samples

```shell
# You can also use wget
curl -X POST /batch/loans/group \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 0c8cc1b9-e396-42c1-85ee-b3f85c16a4a6' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /batch/loans/group HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 0c8cc1b9-e396-42c1-85ee-b3f85c16a4a6
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loans": [
    {
      "loan_id": "TL12345678",
      "group_no": 3,
      "dry_run": null
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'0c8cc1b9-e396-42c1-85ee-b3f85c16a4a6',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/batch/loans/group',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '0c8cc1b9-e396-42c1-85ee-b3f85c16a4a6',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/batch/loans/group',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '0c8cc1b9-e396-42c1-85ee-b3f85c16a4a6',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/batch/loans/group', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '0c8cc1b9-e396-42c1-85ee-b3f85c16a4a6',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/batch/loans/group', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/batch/loans/group");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"0c8cc1b9-e396-42c1-85ee-b3f85c16a4a6"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/batch/loans/group", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /batch/loans/group`

Atomic bulk group move operation

> Body parameter

```json
{
  "loans": [
    {
      "loan_id": "TL12345678",
      "group_no": 3,
      "dry_run": null
    }
  ]
}
```

<h4 id="post__batch_loans_group-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loans|body|[object]|true|none|
|»» GroupRequest|body|object|false|none|
|»»» loan_id|body|string|true|none|
|»»» group_no|body|integer|true|none|
|»»» dry_run|body|boolean|false|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "loan_ids": [
    "string"
  ],
  "dry_run": true
}
```

<h4 id="post__batch_loans_group-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__batch_loans_group-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_ids|[string]|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__batch_transactions_create

> Code samples

```shell
# You can also use wget
curl -X POST /batch/transactions/create \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 10c12b19-c1bd-4e0b-bb3a-34219b2e7504' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /batch/transactions/create HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 10c12b19-c1bd-4e0b-bb3a-34219b2e7504
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "transactions": [
    {
      "loan_id": "T12345678",
      "effective_date": "2022-01-17",
      "transaction_type": "principal-advance",
      "amount": 10000,
      "payment_method": "card-stripe",
      "external_id": "ch_1ee2417e694e745f7b7c51e8bfbb8cfc3",
      "external_source": "FCS",
      "due_date": "2022-01-18",
      "dry_run": null
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'10c12b19-c1bd-4e0b-bb3a-34219b2e7504',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/batch/transactions/create',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '10c12b19-c1bd-4e0b-bb3a-34219b2e7504',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/batch/transactions/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '10c12b19-c1bd-4e0b-bb3a-34219b2e7504',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/batch/transactions/create', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '10c12b19-c1bd-4e0b-bb3a-34219b2e7504',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/batch/transactions/create', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/batch/transactions/create");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"10c12b19-c1bd-4e0b-bb3a-34219b2e7504"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/batch/transactions/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /batch/transactions/create`

Upload transactions in bulk

> Body parameter

```json
{
  "transactions": [
    {
      "loan_id": "T12345678",
      "effective_date": "2022-01-17",
      "transaction_type": "principal-advance",
      "amount": 10000,
      "payment_method": "card-stripe",
      "external_id": "ch_1ee2417e694e745f7b7c51e8bfbb8cfc3",
      "external_source": "FCS",
      "due_date": "2022-01-18",
      "dry_run": null
    }
  ]
}
```

<h4 id="post__batch_transactions_create-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» transactions|body|[object]|true|none|
|»» CreateRequest|body|object|false|none|
|»»» loan_id|body|string|true|none|
|»»» effective_date|body|any|true|none|
|»»»» *anonymous*|body|string(date-time)|false|none|
|»»»» *anonymous*|body|string(date)|false|none|
|»»» transaction_type|body|string|true|An enumeration.|
|»»» amount|body|integer|true|none|
|»»» payment_method|body|string|false|An enumeration.|
|»»» invoice_id|body|string|false|none|
|»»» external_id|body|string|false|none|
|»»» external_source|body|string|false|none|
|»»» servicer_name|body|string|false|none|
|»»» due_date|body|any|false|none|
|»»»» *anonymous*|body|string(date-time)|false|none|
|»»»» *anonymous*|body|string(date)|false|none|
|»»» dry_run|body|boolean|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»» transaction_type|principal-advance|
|»»» transaction_type|principal-and-interest-billing|
|»»» transaction_type|amortized-income-fee|
|»»» transaction_type|amortization-of-income-fee|
|»»» transaction_type|pi-principal-payment|
|»»» transaction_type|pi-interest-payment|
|»»» transaction_type|principal-reduction|
|»»» transaction_type|interest-reduction|
|»»» transaction_type|capitalize-overpaid-interest|
|»»» transaction_type|write-off-principal|
|»»» transaction_type|write-off-interest|
|»»» transaction_type|write-off-suspense|
|»»» transaction_type|suspense|
|»»» transaction_type|suspense-refund|
|»»» transaction_type|origination-fee|
|»»» transaction_type|subvention-refund|
|»»» transaction_type|refund-paid-interest|
|»»» transaction_type|refund-paid-origination-fee|
|»»» transaction_type|charge-off-balance|
|»»» transaction_type|sale-post-charge-off|
|»»» transaction_type|write-off-principal-post-charge-off|
|»»» transaction_type|write-off-interest-post-charge-off|
|»»» transaction_type|restructure-principal-transfer|
|»»» transaction_type|restructure-interest-transfer|
|»»» payment_method|Check|
|»»» payment_method|ach|
|»»» payment_method|card|
|»»» payment_method|ach-chase|
|»»» payment_method|card-chase|
|»»» payment_method|credit-from-wex|
|»»» payment_method|unused-funds|
|»»» payment_method|card-stripe|
|»»» payment_method|ach-stripe|
|»»» payment_method|credit-from-uatp|
|»»» payment_method|card-wells-fargo|
|»»» payment_method|ffam-fee|
|»»» payment_method|ffam|
|»»» payment_method|credit-from-stripe|
|»»» payment_method|ach-bmo|
|»»» payment_method|zelle|
|»»» payment_method|sale-post-charge-off|
|»»» payment_method|nlex-fee|
|»»» payment_method|trueaccord|
|»»» payment_method|trueaccord-fee|
|»»» payment_method|credit-wire-receipt|

> Example responses

> 200 Response

```json
{
  "loan_ids": [
    "string"
  ],
  "dry_run": true
}
```

<h4 id="post__batch_transactions_create-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__batch_transactions_create-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_ids|[string]|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__batch_loans_status_update

> Code samples

```shell
# You can also use wget
curl -X POST /batch/loans/status/update \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 30c7fc90-2f0c-486b-8670-b9a6b831fea4' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /batch/loans/status/update HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 30c7fc90-2f0c-486b-8670-b9a6b831fea4
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loans": [
    {
      "loan_id": "T12345678",
      "primary_status": "ACTIVE",
      "secondary_status": {
        "status": "CANCELED (REFUND)",
        "effective_date": "2022-01-17T20:57:12.141566Z",
        "delete": false
      },
      "dry_run": null
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'30c7fc90-2f0c-486b-8670-b9a6b831fea4',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/batch/loans/status/update',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '30c7fc90-2f0c-486b-8670-b9a6b831fea4',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/batch/loans/status/update',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '30c7fc90-2f0c-486b-8670-b9a6b831fea4',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/batch/loans/status/update', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '30c7fc90-2f0c-486b-8670-b9a6b831fea4',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/batch/loans/status/update', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/batch/loans/status/update");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"30c7fc90-2f0c-486b-8670-b9a6b831fea4"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/batch/loans/status/update", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /batch/loans/status/update`

Atomic bulk status code update

> Body parameter

```json
{
  "loans": [
    {
      "loan_id": "T12345678",
      "primary_status": "ACTIVE",
      "secondary_status": {
        "status": "CANCELED (REFUND)",
        "effective_date": "2022-01-17T20:57:12.141566Z",
        "delete": false
      },
      "dry_run": null
    }
  ]
}
```

<h4 id="post__batch_loans_status_update-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loans|body|[object]|true|none|
|»» UpdateStatusRequest|body|object|false|none|
|»»» loan_id|body|string|true|none|
|»»» primary_status|body|string|false|An enumeration.|
|»»» secondary_status|body|object|false|none|
|»»»» status|body|any|true|none|
|»»»»» *anonymous*|body|string|false|An enumeration.|
|»»»»» *anonymous*|body|string|false|none|
|»»»» effective_date|body|any|false|none|
|»»»»» *anonymous*|body|string(date-time)|false|none|
|»»»»» *anonymous*|body|string(date)|false|none|
|»»»» delete|body|boolean|false|none|
|»»» dry_run|body|boolean|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»» primary_status|ACTIVE|
|»»» primary_status|CLOSED|
|»»»»» *anonymous*|FORGIVEN|
|»»»»» *anonymous*|PAID OFF|
|»»»»» *anonymous*|NON-ACCRUAL|
|»»»»» *anonymous*|GL CHARGE OFF|
|»»»»» *anonymous*|CANCELED (REFUND)|
|»»»»» *anonymous*|CANCELED (UNWIND)|
|»»»»» *anonymous*|FULLY PAID (MERCHANT)|
|»»»»» *anonymous*|SOLD DEBT|

> Example responses

> 200 Response

```json
{
  "loan_ids": [
    "string"
  ],
  "dry_run": true
}
```

<h4 id="post__batch_loans_status_update-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__batch_loans_status_update-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_ids|[string]|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

### post__batch_loans_credit-bureau

> Code samples

```shell
# You can also use wget
curl -X POST /batch/loans/credit-bureau \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 3d022470-e055-4524-a292-3498cb983a95' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /batch/loans/credit-bureau HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 3d022470-e055-4524-a292-3498cb983a95
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "loans": [
    {
      "loan_id": "T12345678",
      "do_not_report": false,
      "special_comment": "AW",
      "dry_run": null
    }
  ],
  "dry_run": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'3d022470-e055-4524-a292-3498cb983a95',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/batch/loans/credit-bureau',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '3d022470-e055-4524-a292-3498cb983a95',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/batch/loans/credit-bureau',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '3d022470-e055-4524-a292-3498cb983a95',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/batch/loans/credit-bureau', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '3d022470-e055-4524-a292-3498cb983a95',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/batch/loans/credit-bureau', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/batch/loans/credit-bureau");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"3d022470-e055-4524-a292-3498cb983a95"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/batch/loans/credit-bureau", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /batch/loans/credit-bureau`

Atomic bulk status code update

> Body parameter

```json
{
  "loans": [
    {
      "loan_id": "T12345678",
      "do_not_report": false,
      "special_comment": "AW",
      "dry_run": null
    }
  ],
  "dry_run": true
}
```

<h4 id="post__batch_loans_credit-bureau-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» loans|body|[object]|true|none|
|»» AddSpecialCommentRequest|body|object|false|none|
|»»» loan_id|body|string|true|none|
|»»» special_comment|body|string|true|An enumeration.|
|»»» do_not_report|body|boolean|false|none|
|»»» dry_run|body|boolean|false|none|
|» dry_run|body|boolean|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»»» special_comment|AW|
|»»» special_comment|AH|

> Example responses

> 200 Response

```json
{
  "loan_ids": [
    "string"
  ],
  "dry_run": true
}
```

<h4 id="post__batch_loans_credit-bureau-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__batch_loans_credit-bureau-responseschema">Response Schema</h4>

Status Code **200**

*GenericResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» loan_ids|[string]|false|none|none|
|» dry_run|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="up-svc-ls-customer">Customer</h2>

### post__customer_update

> Code samples

```shell
# You can also use wget
curl -X POST /customer/update \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-up-correlation-id: 0bf2babc-fac8-4d43-9e7d-7a35632fc809' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /customer/update HTTP/1.1

Content-Type: application/json
Accept: application/json
x-up-correlation-id: 0bf2babc-fac8-4d43-9e7d-7a35632fc809
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "customers": [
    {
      "account_id": "E99449944",
      "TIN": "000-00-0000"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-up-correlation-id':'0bf2babc-fac8-4d43-9e7d-7a35632fc809',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/customer/update',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-up-correlation-id' => '0bf2babc-fac8-4d43-9e7d-7a35632fc809',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/customer/update',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-up-correlation-id': '0bf2babc-fac8-4d43-9e7d-7a35632fc809',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/customer/update', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-up-correlation-id' => '0bf2babc-fac8-4d43-9e7d-7a35632fc809',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/customer/update', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/customer/update");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-up-correlation-id": []string{"0bf2babc-fac8-4d43-9e7d-7a35632fc809"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/customer/update", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /customer/update`

Update customer information

> Body parameter

```json
{
  "customers": [
    {
      "account_id": "E99449944",
      "TIN": "000-00-0000"
    }
  ]
}
```

<h4 id="post__customer_update-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|object|false|none|
|» customers|body|[object]|false|none|
|»» UpdateCustomer|body|object|false|none|
|»»» account_id|body|string|true|none|
|»»» TIN|body|string|false|none|
|» dry_run|body|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "account_ids": [
    "E99449944"
  ]
}
```

<h4 id="post__customer_update-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h4 id="post__customer_update-responseschema">Response Schema</h4>

Status Code **200**

*UpdateCustomerResponse*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» account_ids|[string]|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="up-svc-ls-graphql">GraphQL</h2>

### post__graphql

> Code samples

```shell
# You can also use wget
curl -X POST /graphql \
  -H 'Content-Type: application/json' \
  -H 'x-up-correlation-id: 73076b3a-4c4e-4c47-9a6c-610e44210bad' \
  -H 'x-up-requested-from: svc-process' \
  -H 'x-up-requested-by: test' \
  -H 'x-up-test: {}'

```

```http
POST /graphql HTTP/1.1

Content-Type: application/json

x-up-correlation-id: 73076b3a-4c4e-4c47-9a6c-610e44210bad
x-up-requested-from: svc-process
x-up-requested-by: test
x-up-test: {}

```

```javascript
const inputBody = '{
  "query": "string",
  "variables": null,
  "operationName": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'x-up-correlation-id':'73076b3a-4c4e-4c47-9a6c-610e44210bad',
  'x-up-requested-from':'svc-process',
  'x-up-requested-by':'test',
  'x-up-test':'{}'
};

fetch('/graphql',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'x-up-correlation-id' => '73076b3a-4c4e-4c47-9a6c-610e44210bad',
  'x-up-requested-from' => 'svc-process',
  'x-up-requested-by' => 'test',
  'x-up-test' => '{}'
}

result = RestClient.post '/graphql',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'x-up-correlation-id': '73076b3a-4c4e-4c47-9a6c-610e44210bad',
  'x-up-requested-from': 'svc-process',
  'x-up-requested-by': 'test',
  'x-up-test': '{}'
}

r = requests.post('/graphql', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'x-up-correlation-id' => '73076b3a-4c4e-4c47-9a6c-610e44210bad',
    'x-up-requested-from' => 'svc-process',
    'x-up-requested-by' => 'test',
    'x-up-test' => '{}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/graphql', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/graphql");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "x-up-correlation-id": []string{"73076b3a-4c4e-4c47-9a6c-610e44210bad"},
        "x-up-requested-from": []string{"svc-process"},
        "x-up-requested-by": []string{"test"},
        "x-up-test": []string{"{}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/graphql", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /graphql`

Queries for data using GraphQL

> Body parameter

```json
{
  "query": "string",
  "variables": null,
  "operationName": "string"
}
```

<h4 id="post__graphql-parameters">Parameters</h4>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-up-correlation-id|header|string|false|none|
|x-up-requested-from|header|string|false|none|
|x-up-requested-by|header|string|false|none|
|x-up-test|header|string|false|none|
|body|body|[GraphQLRequest](#schemagraphqlrequest)|false|none|

<h4 id="post__graphql-responses">Responses</h4>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The requested data|None|

<aside class="success">
This operation does not require authentication
</aside>

<h2 id="Schemas_up.svc.ls">Schemas</h2>

<h3 id="tocS_LoanSubsidyCreateRequest">LoanSubsidyCreateRequest</h3>

<a id="schemaloansubsidycreaterequest"></a>
<a id="schema_LoanSubsidyCreateRequest"></a>
<a id="tocSloansubsidycreaterequest"></a>
<a id="tocsloansubsidycreaterequest"></a>

```json
{
  "force_create": false,
  "loan_id": "TL4135193",
  "balance": 244986,
  "start_date": "2022-01-17"
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|force_create|boolean|false|none|none|
|loan_id|string|true|none|none|
|balance|integer(int32)|true|none|none|
|start_date|string(date)|true|none|none|

<h3 id="tocS_LoanSubsidyCreateResponse">LoanSubsidyCreateResponse</h3>

<a id="schemaloansubsidycreateresponse"></a>
<a id="schema_LoanSubsidyCreateResponse"></a>
<a id="tocSloansubsidycreateresponse"></a>
<a id="tocsloansubsidycreateresponse"></a>

```json
{
  "error": "Loan not found",
  "loan_id": "TL4135193"
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|[string]|false|none|none|
|loan_id|string|true|none|none|

<h3 id="tocS_Error">Error</h3>

<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "error": "string"
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|string|false|none|none|

<h3 id="tocS_SubsidyTransaction">SubsidyTransaction</h3>

<a id="schemasubsidytransaction"></a>
<a id="schema_SubsidyTransaction"></a>
<a id="tocSsubsidytransaction"></a>
<a id="tocssubsidytransaction"></a>

```json
{
  "transaction_id": 0,
  "effective_date": "2019-08-24",
  "error": [
    "string"
  ],
  "loan_id": "string",
  "transaction_date": "2019-08-24",
  "transaction_amount": 0,
  "transaction_code": 0,
  "payment_method_no": 0
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transaction_id|integer(int32)|false|none|none|
|effective_date|string(date)|false|none|none|
|error|[string]|false|none|none|
|loan_id|string|true|none|none|
|transaction_date|string(date)|false|none|none|
|transaction_amount|integer(int32)|false|none|none|
|transaction_code|integer(int32)|false|none|none|
|payment_method_no|integer(int32)|false|none|none|

<h3 id="tocS_SubsidyLoan">SubsidyLoan</h3>

<a id="schemasubsidyloan"></a>
<a id="schema_SubsidyLoan"></a>
<a id="tocSsubsidyloan"></a>
<a id="tocssubsidyloan"></a>

```json
{
  "transactions": [
    {
      "transaction_id": 0,
      "effective_date": "2019-08-24",
      "error": [
        "string"
      ],
      "loan_id": "string",
      "transaction_date": "2019-08-24",
      "transaction_amount": 0,
      "transaction_code": 0,
      "payment_method_no": 0
    }
  ],
  "secondary_status": "string",
  "open_date": "2019-08-24",
  "original_note_amount": 0,
  "error": [
    "string"
  ],
  "loan_id": "string",
  "current_payoff_balance": 0,
  "term": 0,
  "current_principal_balance": 0,
  "open_maturity_date": "2019-08-24",
  "primary_status": "string"
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|transactions|[[SubsidyTransaction](#schemasubsidytransaction)]|false|none|none|
|secondary_status|string|false|none|none|
|open_date|string(date)|false|none|none|
|original_note_amount|integer(int32)|false|none|none|
|error|[string]|false|none|none|
|loan_id|string|true|none|none|
|current_payoff_balance|integer(int32)|false|none|none|
|term|integer(int32)|false|none|none|
|current_principal_balance|integer(int32)|false|none|none|
|open_maturity_date|string(date)|false|none|none|
|primary_status|string|false|none|none|

<h3 id="tocS_LoanSubsidyRefundImplicitRequest">LoanSubsidyRefundImplicitRequest</h3>

<a id="schemaloansubsidyrefundimplicitrequest"></a>
<a id="schema_LoanSubsidyRefundImplicitRequest"></a>
<a id="tocSloansubsidyrefundimplicitrequest"></a>
<a id="tocsloansubsidyrefundimplicitrequest"></a>

```json
{
  "date": "2022-01-17",
  "loan_id": "TL4135193",
  "transaction_id": 1501,
  "amount": 66671
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|date|string(date)|true|none|none|
|loan_id|string|true|none|none|
|transaction_id|integer(int32)|true|none|none|
|amount|integer(int32)|true|none|none|

<h3 id="tocS_LoanSubsidyRefundImplicitResponse">LoanSubsidyRefundImplicitResponse</h3>

<a id="schemaloansubsidyrefundimplicitresponse"></a>
<a id="schema_LoanSubsidyRefundImplicitResponse"></a>
<a id="tocSloansubsidyrefundimplicitresponse"></a>
<a id="tocsloansubsidyrefundimplicitresponse"></a>

```json
{
  "error": "Loan not found",
  "loan_id": "TL4135193"
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|[string]|false|none|none|
|loan_id|string|true|none|none|

<h3 id="tocS_GraphQLRequest">GraphQLRequest</h3>

<a id="schemagraphqlrequest"></a>
<a id="schema_GraphQLRequest"></a>
<a id="tocSgraphqlrequest"></a>
<a id="tocsgraphqlrequest"></a>

```json
{
  "query": "string",
  "variables": null,
  "operationName": "string"
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|string|true|none|none|
|variables|any|false|none|none|
|operationName|string|false|none|none|

<h3 id="tocS_LoanSubsidyRefundExplicitRequest">LoanSubsidyRefundExplicitRequest</h3>

<a id="schemaloansubsidyrefundexplicitrequest"></a>
<a id="schema_LoanSubsidyRefundExplicitRequest"></a>
<a id="tocSloansubsidyrefundexplicitrequest"></a>
<a id="tocsloansubsidyrefundexplicitrequest"></a>

```json
{
  "date": "2022-01-17",
  "loan_id": "TL4135193",
  "amount": 66671,
  "force_create": false
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|date|string(date)|true|none|none|
|loan_id|string|true|none|none|
|amount|integer(int32)|true|none|none|
|force_create|boolean|false|none|none|

<h3 id="tocS_LoanSubsidyRefundExplicitResponse">LoanSubsidyRefundExplicitResponse</h3>

<a id="schemaloansubsidyrefundexplicitresponse"></a>
<a id="schema_LoanSubsidyRefundExplicitResponse"></a>
<a id="tocSloansubsidyrefundexplicitresponse"></a>
<a id="tocsloansubsidyrefundexplicitresponse"></a>

```json
{
  "error": "Loan not found",
  "loan_id": "TL4135193"
}

```

#### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|error|[string]|false|none|none|
|loan_id|string|true|none|none|

