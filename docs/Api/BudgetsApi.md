# Criteo\Marketing\BudgetsApi

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get**](BudgetsApi.md#get) | **GET** /v1/budgets | Gets budgets



## get

> \Criteo\Marketing\Model\BudgetMessage[] get($authorization, $advertiser_ids, $budget_ids, $only_active_campaigns)

Gets budgets

Get the list of budgets with the specified filters.  If an advertiser or a budget is requested but is missing from current user's portfolio, it will not be included in the list.  If neither budgets ids nor advertisers ids are provided, then the user's portfolio will be used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\BudgetsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$advertiser_ids = 'advertiser_ids_example'; // string | Optional. One or more advertiser ids, E.g. 78, 12932, 45236. If the requested advertiser ids are not part of the user's portfolio, they will be skipped.
$budget_ids = 'budget_ids_example'; // string | Optional. One or more budget ids, E.g. 75, 1931, 532. If the requested budget ids are not part of the user's portfolio, they will be skipped.
$only_active_campaigns = True; // bool | Optional. Filters by campaign status, allowing to only display active campaigns or not. Default value is true.

try {
    $result = $apiInstance->get($authorization, $advertiser_ids, $budget_ids, $only_active_campaigns);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BudgetsApi->get: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **advertiser_ids** | **string**| Optional. One or more advertiser ids, E.g. 78, 12932, 45236. If the requested advertiser ids are not part of the user&#39;s portfolio, they will be skipped. | [optional]
 **budget_ids** | **string**| Optional. One or more budget ids, E.g. 75, 1931, 532. If the requested budget ids are not part of the user&#39;s portfolio, they will be skipped. | [optional]
 **only_active_campaigns** | **bool**| Optional. Filters by campaign status, allowing to only display active campaigns or not. Default value is true. | [optional]

### Return type

[**\Criteo\Marketing\Model\BudgetMessage[]**](../Model/BudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

