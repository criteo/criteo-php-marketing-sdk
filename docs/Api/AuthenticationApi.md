# Criteo\Marketing\AuthenticationApi

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**oAuth2TokenPost**](AuthenticationApi.md#oAuth2TokenPost) | **POST** /oauth2/token | Authenticates provided credentials and returns an access token



## oAuth2TokenPost

> \Criteo\Marketing\Model\InlineResponse200 oAuth2TokenPost($client_id, $client_secret, $grant_type)

Authenticates provided credentials and returns an access token

Get the token necessary to perform any action through our API. You can create your API User in our Criteo platform <a href='https://marketing.criteo.com' target='_blank'>here</a>. If you forgot your credentials (client_id and/or client_secret) you will need to reset them there.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


$apiInstance = new Criteo\Marketing\Api\AuthenticationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$client_id = 'client_id_example'; // string | API Client-Id or Username
$client_secret = 'client_secret_example'; // string | API Client secret or password
$grant_type = 'client_credentials'; // string | Other grant types are not available

try {
    $result = $apiInstance->oAuth2TokenPost($client_id, $client_secret, $grant_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthenticationApi->oAuth2TokenPost: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **client_id** | **string**| API Client-Id or Username | [optional]
 **client_secret** | **string**| API Client secret or password | [optional]
 **grant_type** | **string**| Other grant types are not available | [optional] [default to &#39;client_credentials&#39;]

### Return type

[**\Criteo\Marketing\Model\InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/x-www-form-urlencoded
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

