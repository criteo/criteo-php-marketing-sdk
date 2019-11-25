# Criteo\Marketing\PublishersApi

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getStats**](PublishersApi.md#getStats) | **POST** /v1/publishers/stats | 



## getStats

> \Criteo\Marketing\Model\PublisherStatsMessage[] getStats($authorization, $query_message)



### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\PublishersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$query_message = new \Criteo\Marketing\Model\PublisherStatsQueryMessage(); // \Criteo\Marketing\Model\PublisherStatsQueryMessage | 

try {
    $result = $apiInstance->getStats($authorization, $query_message);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PublishersApi->getStats: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **query_message** | [**\Criteo\Marketing\Model\PublisherStatsQueryMessage**](../Model/PublisherStatsQueryMessage.md)|  |

### Return type

[**\Criteo\Marketing\Model\PublisherStatsMessage[]**](../Model/PublisherStatsMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

