# Criteo\Marketing\CategoriesApi

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getCategories**](CategoriesApi.md#getCategories) | **GET** /v1/categories | Gets categories
[**updateCategories**](CategoriesApi.md#updateCategories) | **PUT** /v1/categories | Enables/disables categories



## getCategories

> \Criteo\Marketing\Model\CategoryMessage[] getCategories($authorization, $campaign_ids, $advertiser_ids, $category_hash_codes, $enabled_only)

Gets categories

Get the list of categories with the specified filters.  If a category is requested but is missing from current user's portfolio, it will not be included in the list.  If neither campaign ids nor advertisers ids are provided, then the user's portfolio will be used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CategoriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$campaign_ids = 'campaign_ids_example'; // string | Optional. One or more campaign ids, E.g., 78, 12932, 45236. If the campaign ids requested are not liked to advertisers in the user's portfolio, they will be skipped.
$advertiser_ids = 'advertiser_ids_example'; // string | Optional. One or more advertiser ids, E.g., 78, 12932, 45236. If the advertiser ids requested are not part of the user's portfolio, they will be skipped.
$category_hash_codes = 'category_hash_codes_example'; // string | Optional. One or more category hash codes.
$enabled_only = True; // bool | Optional. Returns only categories you can bid on. Defaults to false.

try {
    $result = $apiInstance->getCategories($authorization, $campaign_ids, $advertiser_ids, $category_hash_codes, $enabled_only);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CategoriesApi->getCategories: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **campaign_ids** | **string**| Optional. One or more campaign ids, E.g., 78, 12932, 45236. If the campaign ids requested are not liked to advertisers in the user&#39;s portfolio, they will be skipped. | [optional]
 **advertiser_ids** | **string**| Optional. One or more advertiser ids, E.g., 78, 12932, 45236. If the advertiser ids requested are not part of the user&#39;s portfolio, they will be skipped. | [optional]
 **category_hash_codes** | **string**| Optional. One or more category hash codes. | [optional]
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


## updateCategories

> \Criteo\Marketing\Model\CategoryUpdatesPerCatalog[] updateCategories($authorization, $categories_per_catalog)

Enables/disables categories

Update categories for multiple catalogs.<br />  Please note that all validations need to pass before applying the requested changes;  the subsequent validation error messages will be returned in the response.<br />  Please note that bidding will still happen for disabled categories, but using the Camapign's bid.  If the call is successful, full details about the changed categories will be returned.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CategoriesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$categories_per_catalog = array(new \Criteo\Marketing\Model\CategoryUpdatesPerCatalog()); // \Criteo\Marketing\Model\CategoryUpdatesPerCatalog[] | The list of categories to be enabled/disabled, grouped by catalog.

try {
    $result = $apiInstance->updateCategories($authorization, $categories_per_catalog);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CategoriesApi->updateCategories: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **categories_per_catalog** | [**\Criteo\Marketing\Model\CategoryUpdatesPerCatalog[]**](../Model/CategoryUpdatesPerCatalog.md)| The list of categories to be enabled/disabled, grouped by catalog. |

### Return type

[**\Criteo\Marketing\Model\CategoryUpdatesPerCatalog[]**](../Model/CategoryUpdatesPerCatalog.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

