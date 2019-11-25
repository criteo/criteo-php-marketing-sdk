# Criteo\Marketing\AdvertisersApi

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getCampaigns**](AdvertisersApi.md#getCampaigns) | **GET** /v1/advertisers/{advertiserId}/campaigns | Gets all advertiser&#39;s campaigns
[**getCategories**](AdvertisersApi.md#getCategories) | **GET** /v1/advertisers/{advertiserId}/categories | Gets all advertiser&#39;s categories
[**getCategory**](AdvertisersApi.md#getCategory) | **GET** /v1/advertisers/{advertiserId}/categories/{categoryHashCode} | Gets a specific advertiser&#39;s category



## getCampaigns

> \Criteo\Marketing\Model\CampaignMessage[] getCampaigns($advertiser_id, $authorization)

Gets all advertiser's campaigns

Get the list of all the campaigns linked to the requested advertiser.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AdvertisersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$advertiser_id = 56; // int | Mandatory. The id of the advertiser to return.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getCampaigns($advertiser_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdvertisersApi->getCampaigns: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **advertiser_id** | **int**| Mandatory. The id of the advertiser to return. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\CampaignMessage[]**](../Model/CampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getCategories

> \Criteo\Marketing\Model\CategoryMessage[] getCategories($advertiser_id, $authorization, $enabled_only)

Gets all advertiser's categories

Get the list of all the categories linked to the requested advertiser.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AdvertisersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$advertiser_id = 56; // int | Mandatory. The id of the advertiser to return.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$enabled_only = True; // bool | Optional. Returns only categories you can bid on. Defaults to false.

try {
    $result = $apiInstance->getCategories($advertiser_id, $authorization, $enabled_only);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdvertisersApi->getCategories: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **advertiser_id** | **int**| Mandatory. The id of the advertiser to return. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **enabled_only** | **bool**| Optional. Returns only categories you can bid on. Defaults to false. | [optional]

### Return type

[**\Criteo\Marketing\Model\CategoryMessage[]**](../Model/CategoryMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getCategory

> \Criteo\Marketing\Model\CategoryMessage[] getCategory($advertiser_id, $category_hash_code, $authorization)

Gets a specific advertiser's category

Get a specific category linked to the requested advertiser.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AdvertisersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$advertiser_id = 56; // int | Mandatory. The id of the advertiser to return.
$category_hash_code = 56; // int | Mandatory. The id of the category to return.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getCategory($advertiser_id, $category_hash_code, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AdvertisersApi->getCategory: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **advertiser_id** | **int**| Mandatory. The id of the advertiser to return. |
 **category_hash_code** | **int**| Mandatory. The id of the category to return. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\CategoryMessage[]**](../Model/CategoryMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

