# Obtain Token
## API Information

**Detailed Explanation**:

The value of Authorization uses the authentication username and password connected by ":" and then generated using Base64 encryption. 
For example: String code = Base64(username + ":" + password); code is the value of key: Authorization

**API Path**
/api/v1/tokens

**Request Protocol**
HTTPS

**Request Method**
GET

**Request Headers**:
| Header Label | Required | Description | Type | Data Dictionary | Restriction | Header Content | Example |
| :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ |
|Authorization|Yes||[string]|||Basic YWRtaW5pc3RyYXRvcjpSd0AyMDI1Iw==|Basic YWRtaW5pc3RyYXRvcjpSd0AyMDI1Iw==|

**Return Result**
>Success (200)
Json
object

| Parameter Name  | Description | Required | Type | Data Dictionary | Restriction | Example |
| :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ |
|user| |Yes|[string]| ||administrator|
|value| |Yes|[string]| ||eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJhZG1pbmlzdHJhdG9yIiwiZXhwIjoxNzU3Mzg4MDg4OTkxfQ.wr1TxAC_c8gRpgGMlCaDBgnYhnGlpsuS-0QGPn5jXIM|

