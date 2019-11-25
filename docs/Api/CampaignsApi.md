# Criteo\Marketing\CampaignsApi

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**getBids**](CampaignsApi.md#getBids) | **GET** /v1/campaigns/bids | Gets a the bids for campaigns and their categories
[**getCampaign**](CampaignsApi.md#getCampaign) | **GET** /v1/campaigns/{campaignId} | Gets a specific campaign
[**getCampaigns**](CampaignsApi.md#getCampaigns) | **GET** /v1/campaigns | Gets campaigns
[**getCategories**](CampaignsApi.md#getCategories) | **GET** /v1/campaigns/{campaignId}/categories | Gets categories
[**getCategory**](CampaignsApi.md#getCategory) | **GET** /v1/campaigns/{campaignId}/categories/{categoryHashCode} | Gets a specific category
[**updateBids**](CampaignsApi.md#updateBids) | **PUT** /v1/campaigns/bids | Update bids for campaigns and their categories



## getBids

> \Criteo\Marketing\Model\CampaignBidMessage[] getBids($authorization, $campaign_ids, $advertiser_ids, $category_hash_codes, $bid_type, $campaign_status, $pending_changes)

Gets a the bids for campaigns and their categories

Get the campaigns' bids, as well as the bids of their categories

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$campaign_ids = 'campaign_ids_example'; // string | Optional. The ids of the campaigns we want to get the bids on. If not specified, advertiserIds will be used.
$advertiser_ids = 'advertiser_ids_example'; // string | Optional. The ids of the advertisers' campaigns we want to get the bids on. If campaignIds not specified, and neither is advertiserIds, all the advertisers in the user's portfolio are used.
$category_hash_codes = 'category_hash_codes_example'; // string | Optional. Filters only specified categories. By default no filtering is applied.
$bid_type = 'bid_type_example'; // string | Optional. Filters by bid type. By default no filtering is applied.
$campaign_status = 'campaign_status_example'; // string | Optional. Filters by campaign status. By default no filtering is applied.
$pending_changes = True; // bool | Optional. Filters only pending changes or settled ones. By default no filtering is applied.

try {
    $result = $apiInstance->getBids($authorization, $campaign_ids, $advertiser_ids, $category_hash_codes, $bid_type, $campaign_status, $pending_changes);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CampaignsApi->getBids: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **campaign_ids** | **string**| Optional. The ids of the campaigns we want to get the bids on. If not specified, advertiserIds will be used. | [optional]
 **advertiser_ids** | **string**| Optional. The ids of the advertisers&#39; campaigns we want to get the bids on. If campaignIds not specified, and neither is advertiserIds, all the advertisers in the user&#39;s portfolio are used. | [optional]
 **category_hash_codes** | **string**| Optional. Filters only specified categories. By default no filtering is applied. | [optional]
 **bid_type** | **string**| Optional. Filters by bid type. By default no filtering is applied. | [optional]
 **campaign_status** | **string**| Optional. Filters by campaign status. By default no filtering is applied. | [optional]
 **pending_changes** | **bool**| Optional. Filters only pending changes or settled ones. By default no filtering is applied. | [optional]

### Return type

[**\Criteo\Marketing\Model\CampaignBidMessage[]**](../Model/CampaignBidMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getCampaign

> \Criteo\Marketing\Model\CampaignMessage getCampaign($campaign_id, $authorization)

Gets a specific campaign

Get a specific campaign

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 56; // int | Mandatory. The id of the campaign to return.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getCampaign($campaign_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CampaignsApi->getCampaign: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **int**| Mandatory. The id of the campaign to return. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\CampaignMessage**](../Model/CampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getCampaigns

> \Criteo\Marketing\Model\CampaignMessage[] getCampaigns($authorization, $campaign_ids, $advertiser_ids, $campaign_status, $bid_type)

Gets campaigns

Get the list of campaigns with the specified filters.  If a campaign is requested but is missing from current user's portfolio, it will not be included in the list.  If neither campaign ids nor advertisers ids are provided, then the user's portfolio will be used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$campaign_ids = 'campaign_ids_example'; // string | Optional. One or more campaign ids, E.g., 78, 12932, 45236. If the campaign ids requested are not linked to advertisers in the user's portfolio, they will be skipped.
$advertiser_ids = 'advertiser_ids_example'; // string | Optional. One or more advertiser ids, E.g., 78, 12932, 45236. If the advertiser ids requested are not part of the user's portfolio, they will be skipped.
$campaign_status = 'campaign_status_example'; // string | Optional. Filters by campaign status. By default no filtering is applied.
$bid_type = 'bid_type_example'; // string | Optional. Filters by campaign bid type. By default, no filtering is applied.

try {
    $result = $apiInstance->getCampaigns($authorization, $campaign_ids, $advertiser_ids, $campaign_status, $bid_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CampaignsApi->getCampaigns: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **campaign_ids** | **string**| Optional. One or more campaign ids, E.g., 78, 12932, 45236. If the campaign ids requested are not linked to advertisers in the user&#39;s portfolio, they will be skipped. | [optional]
 **advertiser_ids** | **string**| Optional. One or more advertiser ids, E.g., 78, 12932, 45236. If the advertiser ids requested are not part of the user&#39;s portfolio, they will be skipped. | [optional]
 **campaign_status** | **string**| Optional. Filters by campaign status. By default no filtering is applied. | [optional]
 **bid_type** | **string**| Optional. Filters by campaign bid type. By default, no filtering is applied. | [optional]

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

> \Criteo\Marketing\Model\CategoryMessage getCategories($campaign_id, $authorization, $enabled_only)

Gets categories

Get the list of categories linked to the requested campaign.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 56; // int | Mandatory. The id of the campaign the categories are linked to.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$enabled_only = True; // bool | Optional. Returns only categories you can bid on. Defaults to false.

try {
    $result = $apiInstance->getCategories($campaign_id, $authorization, $enabled_only);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CampaignsApi->getCategories: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **int**| Mandatory. The id of the campaign the categories are linked to. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **enabled_only** | **bool**| Optional. Returns only categories you can bid on. Defaults to false. | [optional]

### Return type

[**\Criteo\Marketing\Model\CategoryMessage**](../Model/CategoryMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getCategory

> \Criteo\Marketing\Model\CategoryMessage getCategory($campaign_id, $category_hash_code, $authorization)

Gets a specific category

Get a specific category linked to the requested campaign.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$campaign_id = 56; // int | Mandatory. The id of the campaign the categories are linked to.
$category_hash_code = 56; // int | Mandatory. The id of the category to return.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getCategory($campaign_id, $category_hash_code, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CampaignsApi->getCategory: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **campaign_id** | **int**| Mandatory. The id of the campaign the categories are linked to. |
 **category_hash_code** | **int**| Mandatory. The id of the category to return. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\CategoryMessage**](../Model/CategoryMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## updateBids

> \Criteo\Marketing\Model\CampaignMessage[] updateBids($authorization, $bid_changes)

Update bids for campaigns and their categories

If a campaign bid is updated, all (if any) category bids for this campaign will be updated with the new value if they are initially equal to the campaign bid.  If the category bid is not wanted to be cascaded to the categories with the same bid value, new change bids must be added in the request for the categories where the value should be kept (with the initial value).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\CampaignsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$bid_changes = array(new \Criteo\Marketing\Model\CampaignBidChangeRequest()); // \Criteo\Marketing\Model\CampaignBidChangeRequest[] | Specifies the list of bid changes to be applied.

try {
    $result = $apiInstance->updateBids($authorization, $bid_changes);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CampaignsApi->updateBids: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **bid_changes** | [**\Criteo\Marketing\Model\CampaignBidChangeRequest[]**](../Model/CampaignBidChangeRequest.md)| Specifies the list of bid changes to be applied. |

### Return type

[**\Criteo\Marketing\Model\CampaignMessage[]**](../Model/CampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

