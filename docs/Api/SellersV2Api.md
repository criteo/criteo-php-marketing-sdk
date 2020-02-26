# Criteo\Marketing\SellersV2Api

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createSellerBudgets**](SellersV2Api.md#createSellerBudgets) | **POST** /v2/crp/budgets | Create a collection of budgets.
[**createSellerCampaignsBySeller**](SellersV2Api.md#createSellerCampaignsBySeller) | **POST** /v2/crp/sellers/{sellerId}/seller-campaigns | Create a SellerCampaign
[**createSellers**](SellersV2Api.md#createSellers) | **POST** /v2/crp/advertisers/{advertiserId}/sellers | Create new sellers for an advertiser
[**getAdvertiserCampaigns**](SellersV2Api.md#getAdvertiserCampaigns) | **GET** /v2/crp/advertisers/{advertiserId} | Get the collection of CRP campaigns associated with the advertiserId.
[**getAdvertisers**](SellersV2Api.md#getAdvertisers) | **GET** /v2/crp/advertisers | Get the collection of advertisers associated with the user.
[**getBudgetsBySeller**](SellersV2Api.md#getBudgetsBySeller) | **GET** /v2/crp/sellers/{sellerId}/budgets | Get a collection of budgets for this seller.
[**getBudgetsBySellerCampaignId**](SellersV2Api.md#getBudgetsBySellerCampaignId) | **GET** /v2/crp/seller-campaigns/{sellerCampaignId}/budgets | Get a collection of budgets for this seller campaign.
[**getSeller**](SellersV2Api.md#getSeller) | **GET** /v2/crp/sellers/{sellerId} | Get details for a seller.
[**getSellerBudget**](SellersV2Api.md#getSellerBudget) | **GET** /v2/crp/budgets/{budgetId} | Get details for a budget.
[**getSellerBudgets**](SellersV2Api.md#getSellerBudgets) | **GET** /v2/crp/budgets | Get a collection of budgets.
[**getSellerCampaign**](SellersV2Api.md#getSellerCampaign) | **GET** /v2/crp/seller-campaigns/{sellerCampaignId} | Get details for a seller campaign.
[**getSellerCampaigns**](SellersV2Api.md#getSellerCampaigns) | **GET** /v2/crp/seller-campaigns | Get a collection of seller campaigns.
[**getSellerCampaignsBySeller**](SellersV2Api.md#getSellerCampaignsBySeller) | **GET** /v2/crp/sellers/{sellerId}/seller-campaigns | Get a collection of seller campaigns for this seller.
[**getSellers**](SellersV2Api.md#getSellers) | **GET** /v2/crp/sellers | Get a collection of sellers.
[**updateSellerBudget**](SellersV2Api.md#updateSellerBudget) | **PATCH** /v2/crp/budgets/{budgetId} | Modify a single budget.
[**updateSellerBudgets**](SellersV2Api.md#updateSellerBudgets) | **PATCH** /v2/crp/budgets | Modify a collection of budgets.
[**updateSellerCampaign**](SellersV2Api.md#updateSellerCampaign) | **PATCH** /v2/crp/seller-campaigns/{sellerCampaignId} | Update an existing seller campaign.
[**updateSellerCampaigns**](SellersV2Api.md#updateSellerCampaigns) | **PATCH** /v2/crp/seller-campaigns | Update a collection of seller campaigns.



## createSellerBudgets

> \Criteo\Marketing\Model\SellerBudgetMessage[] createSellerBudgets($authorization, $create_seller_budgets)

Create a collection of budgets.

Create one or more new budgets to enable spending with the given limitations.  All three types of budgets can be created this way.                The following constraints apply when creating a new budget.                • <b>sellerId</b>: the seller MUST be supplied<br />  • <b>campaignIds</b>: a non-empty array of campaign ids MUST be supplied<br />  • <b>budgetType</b>: a budget type MUST be supplied<br />  • <b>amount</b>: an amount MAY be supplied only if the type is not Uncapped and if supplied it MUST be non-negative<br />  • <b>startDate</b>: a future start date MUST be supplied<br />  • <b>endDate</b>: an end date MAY be supplied and if supplied MUST be greater than the start date<br />                Other attributes MUST NOT be supplied.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$create_seller_budgets = array(new \Criteo\Marketing\Model\CreateSellerBudgetMapiMessage()); // \Criteo\Marketing\Model\CreateSellerBudgetMapiMessage[] | 

try {
    $result = $apiInstance->createSellerBudgets($authorization, $create_seller_budgets);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->createSellerBudgets: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **create_seller_budgets** | [**\Criteo\Marketing\Model\CreateSellerBudgetMapiMessage[]**](../Model/CreateSellerBudgetMapiMessage.md)|  |

### Return type

[**\Criteo\Marketing\Model\SellerBudgetMessage[]**](../Model/SellerBudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## createSellerCampaignsBySeller

> \Criteo\Marketing\Model\SellerCampaignMessage createSellerCampaignsBySeller($seller_id, $authorization, $seller_campaign)

Create a SellerCampaign

Associate an existing Seller with an existing Campaign allowing for budget creation

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$seller_id = 'seller_id_example'; // string | Supply a generated Id of an existing Seller
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$seller_campaign = new \Criteo\Marketing\Model\CreateSellerCampaignMessageMapi(); // \Criteo\Marketing\Model\CreateSellerCampaignMessageMapi | Supply the campaign Id and bid to create the mapping

try {
    $result = $apiInstance->createSellerCampaignsBySeller($seller_id, $authorization, $seller_campaign);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->createSellerCampaignsBySeller: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seller_id** | **string**| Supply a generated Id of an existing Seller |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **seller_campaign** | [**\Criteo\Marketing\Model\CreateSellerCampaignMessageMapi**](../Model/CreateSellerCampaignMessageMapi.md)| Supply the campaign Id and bid to create the mapping |

### Return type

[**\Criteo\Marketing\Model\SellerCampaignMessage**](../Model/SellerCampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## createSellers

> \Criteo\Marketing\Model\SellerBase[] createSellers($advertiser_id, $authorization, $seller_names, $partner_id)

Create new sellers for an advertiser

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$advertiser_id = 56; // int | 
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$seller_names = array('seller_names_example'); // string[] | 
$partner_id = 56; // int | 

try {
    $result = $apiInstance->createSellers($advertiser_id, $authorization, $seller_names, $partner_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->createSellers: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **advertiser_id** | **int**|  |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **seller_names** | [**string[]**](../Model/string.md)|  |
 **partner_id** | **int**|  | [optional]

### Return type

[**\Criteo\Marketing\Model\SellerBase[]**](../Model/SellerBase.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getAdvertiserCampaigns

> \Criteo\Marketing\Model\AdvertiserCampaignMessage[] getAdvertiserCampaigns($advertiser_id, $authorization)

Get the collection of CRP campaigns associated with the advertiserId.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$advertiser_id = 56; // int | 
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getAdvertiserCampaigns($advertiser_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getAdvertiserCampaigns: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **advertiser_id** | **int**|  |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\AdvertiserCampaignMessage[]**](../Model/AdvertiserCampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getAdvertisers

> \Criteo\Marketing\Model\AdvertiserInfoMessage[] getAdvertisers($authorization)

Get the collection of advertisers associated with the user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getAdvertisers($authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getAdvertisers: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\AdvertiserInfoMessage[]**](../Model/AdvertiserInfoMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getBudgetsBySeller

> \Criteo\Marketing\Model\SellerBudgetMessage[] getBudgetsBySeller($seller_id, $authorization, $status, $with_balance, $with_spend, $end_after_date, $start_before_date, $campaign_id, $type)

Get a collection of budgets for this seller.

Return a collection of budgets for this seller filtered by optional filter parameters.  If all parameters are omitted the entire collection to which the user has  access is returned, except those whose endDate is in the past. Returned budgets must satisfy all supplied filter  criteria if multiple parameters are used. See the budgets endpoint for additional details.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$seller_id = 'seller_id_example'; // string | Return only budgets belonging to the given seller.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$status = 'status_example'; // string | Return only budgets with the given status.
$with_balance = True; // bool | Return only budgets with the given status.
$with_spend = True; // bool | Return budgets with any positive spend.
$end_after_date = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Return budgets that end after the given date using the `yyyy-MM-DD` format.              If param is not provided, default behavior is to only return budgets that have not yet ended.
$start_before_date = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Return budgets that start on or before the given date using the `yyyy-MM-DD` format.
$campaign_id = 56; // int | Return only budgets that pay for a given campaign.
$type = 'type_example'; // string | Return only budgets with the given budget type.

try {
    $result = $apiInstance->getBudgetsBySeller($seller_id, $authorization, $status, $with_balance, $with_spend, $end_after_date, $start_before_date, $campaign_id, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getBudgetsBySeller: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seller_id** | **string**| Return only budgets belonging to the given seller. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **status** | **string**| Return only budgets with the given status. | [optional]
 **with_balance** | **bool**| Return only budgets with the given status. | [optional]
 **with_spend** | **bool**| Return budgets with any positive spend. | [optional]
 **end_after_date** | **\DateTime**| Return budgets that end after the given date using the &#x60;yyyy-MM-DD&#x60; format.              If param is not provided, default behavior is to only return budgets that have not yet ended. | [optional]
 **start_before_date** | **\DateTime**| Return budgets that start on or before the given date using the &#x60;yyyy-MM-DD&#x60; format. | [optional]
 **campaign_id** | **int**| Return only budgets that pay for a given campaign. | [optional]
 **type** | **string**| Return only budgets with the given budget type. | [optional]

### Return type

[**\Criteo\Marketing\Model\SellerBudgetMessage[]**](../Model/SellerBudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getBudgetsBySellerCampaignId

> \Criteo\Marketing\Model\SellerBudgetMessage[] getBudgetsBySellerCampaignId($seller_campaign_id, $authorization, $status, $with_balance, $with_spend, $end_after_date, $start_before_date, $type)

Get a collection of budgets for this seller campaign.

Return a collection of budgets for this seller campaign filtered by optional filter parameters.  If all parameters are omitted the entire collection to which the user has  access is returned, except those whose endDate is in the past. Returned budgets must satisfy all supplied filter  criteria if multiple parameters are used.                See the budgets endpoint for additional details.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$seller_campaign_id = 'seller_campaign_id_example'; // string | Return only budgets belonging to the given seller campaign.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$status = 'status_example'; // string | Return only budgets with the given status.
$with_balance = True; // bool | Return only budgets with a positive balance.
$with_spend = True; // bool | Return budgets with a positive spend.
$end_after_date = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Return budgets that end after the given date using the `yyyy-MM-DD` format.               If param is not provided, default behavior is to only return budgets that have not yet ended.
$start_before_date = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Return budgets that start on or before the given date using the `yyyy-MM-DD` format.
$type = 'type_example'; // string | Return only budgets with the given budget type.

try {
    $result = $apiInstance->getBudgetsBySellerCampaignId($seller_campaign_id, $authorization, $status, $with_balance, $with_spend, $end_after_date, $start_before_date, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getBudgetsBySellerCampaignId: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seller_campaign_id** | **string**| Return only budgets belonging to the given seller campaign. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **status** | **string**| Return only budgets with the given status. | [optional]
 **with_balance** | **bool**| Return only budgets with a positive balance. | [optional]
 **with_spend** | **bool**| Return budgets with a positive spend. | [optional]
 **end_after_date** | **\DateTime**| Return budgets that end after the given date using the &#x60;yyyy-MM-DD&#x60; format.               If param is not provided, default behavior is to only return budgets that have not yet ended. | [optional]
 **start_before_date** | **\DateTime**| Return budgets that start on or before the given date using the &#x60;yyyy-MM-DD&#x60; format. | [optional]
 **type** | **string**| Return only budgets with the given budget type. | [optional]

### Return type

[**\Criteo\Marketing\Model\SellerBudgetMessage[]**](../Model/SellerBudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSeller

> \Criteo\Marketing\Model\SellerBase getSeller($seller_id, $authorization)

Get details for a seller.

Returns details for the selected seller.  For example                    {          \"id\" : \"123456\"          \"sellerName\": \"HBogart\",      }

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$seller_id = 'seller_id_example'; // string | Id of the seller.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getSeller($seller_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getSeller: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seller_id** | **string**| Id of the seller. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\SellerBase**](../Model/SellerBase.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSellerBudget

> \Criteo\Marketing\Model\SellerBudgetMessage getSellerBudget($budget_id, $authorization)

Get details for a budget.

Return a budget. For example:                    {          \"id\": \"1759183\",          \"sellerId\": \"321392\",          \"campaignIds\": [              143962          ],          \"budgetType\": \"Capped\",          \"amount\": 1000,          \"startDate\": \"2021-01-11\",          \"endDate\": \"2021-01-12\",          \"spend\": null,          \"status\": \"Active\"      }                A budget limits the spend of a seller for one or more campaigns.                There are three types of budget:<br /><b>Uncapped</b> budgets put no limit on the total amount of spend.<br /><b>Capped</b> budgets limit the total spend to a fixed amount.<br /><b>Daily</b> budgets limit daily spend to a fixed amount.<br />                In addition, budgets can limit the spend to a specific range of dates using  the start and end date attributes. Finally a budget must be active to be used.                <b>Spend</b> approximates the current spend against this budget. There may be a lag  between when an ad is clicked and the time it accrues to the spend.  Daily budgets  show spend against the most recent day only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$budget_id = 56; // int | Id of the budget.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getSellerBudget($budget_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getSellerBudget: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **budget_id** | **int**| Id of the budget. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\SellerBudgetMessage**](../Model/SellerBudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSellerBudgets

> \Criteo\Marketing\Model\SellerBudgetMessage[] getSellerBudgets($authorization, $status, $with_balance, $with_spend, $end_after_date, $start_before_date, $campaign_id, $seller_id, $type)

Get a collection of budgets.

Return a collection of budgets filtered by optional filter parameters.  If all parameters are omitted the entire collection to which the user has  access is returned, except those whose endDate is in the past. Returned budgets must satisfy all supplied filter  criteria if multiple parameters are used.                <b>Date filter.</b> Filtering can return only budgets that were active for a  date range by specifying the startBeforeDate and endAfterDate. Leaving off the startBeforeDate  value makes budgets with any startDate qualify, whereas when leaving off the endAfterDate value will only return  budgets whose endDate has not already passed. To get budgets that were active  on a specific date, set both values to that day.                <b>Spend.</b> If the endAfterDate is supplied, the spend excludes spend that  happened after that date. In the case of a daily budget, only the spend for  the final day is displayed.                See the budgets endpoint for additional details.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$status = 'status_example'; // string | Return only budgets with the given status.
$with_balance = True; // bool | Return only budgets with the given status.
$with_spend = True; // bool | Return budgets with any positive spend.
$end_after_date = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Return budgets that end after the given date using the `yyyy-MM-DD` format.               If param is not provided, default behavior is to only return budgets that have not yet ended.
$start_before_date = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Return budgets that start on or before the given date using the `yyyy-MM-DD` format.
$campaign_id = 56; // int | Return only budgets that pay for a given campaign.
$seller_id = 'seller_id_example'; // string | Return only budgets belonging to the given seller.
$type = 'type_example'; // string | Return only budgets with the given budget type.

try {
    $result = $apiInstance->getSellerBudgets($authorization, $status, $with_balance, $with_spend, $end_after_date, $start_before_date, $campaign_id, $seller_id, $type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getSellerBudgets: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **status** | **string**| Return only budgets with the given status. | [optional]
 **with_balance** | **bool**| Return only budgets with the given status. | [optional]
 **with_spend** | **bool**| Return budgets with any positive spend. | [optional]
 **end_after_date** | **\DateTime**| Return budgets that end after the given date using the &#x60;yyyy-MM-DD&#x60; format.               If param is not provided, default behavior is to only return budgets that have not yet ended. | [optional]
 **start_before_date** | **\DateTime**| Return budgets that start on or before the given date using the &#x60;yyyy-MM-DD&#x60; format. | [optional]
 **campaign_id** | **int**| Return only budgets that pay for a given campaign. | [optional]
 **seller_id** | **string**| Return only budgets belonging to the given seller. | [optional]
 **type** | **string**| Return only budgets with the given budget type. | [optional]

### Return type

[**\Criteo\Marketing\Model\SellerBudgetMessage[]**](../Model/SellerBudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSellerCampaign

> \Criteo\Marketing\Model\SellerCampaignMessage getSellerCampaign($seller_campaign_id, $authorization)

Get details for a seller campaign.

Return details for a seller campaign.  For example,                    {          \"id\": \"543210.123456\",          \"suspendedSince\": \"2018-07-30\",          \"sellerId\": \"543210\",          \"campaignId\": 123456,          \"bid\": 1.55      }                An active seller campaign is one for which the value of <b>suspendedSince</b> is null and  the <b>bid</b> is positive. The currency of the bid is the <b>bidCurrency</b> of the  associated campaign.                Any active seller campaign must also have an active total (capped or uncapped) budget.  It may optionally have an active daily budget as well to further limit spending.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$seller_campaign_id = 'seller_campaign_id_example'; // string | Id of the seller campaign.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->getSellerCampaign($seller_campaign_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getSellerCampaign: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seller_campaign_id** | **string**| Id of the seller campaign. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\SellerCampaignMessage**](../Model/SellerCampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSellerCampaigns

> \Criteo\Marketing\Model\SellerCampaignMessage[] getSellerCampaigns($authorization, $seller_status, $seller_id, $campaign_id, $budget_status)

Get a collection of seller campaigns.

Return a collection of seller campaigns filtered by optional filter parameters.  If all parameters are omitted the entire collection to which the user has  access is returned. Returned sellers must satisfy all supplied filter  criteria if multiple parameters are used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$seller_status = 'seller_status_example'; // string | Return only seller campaigns for sellers with the given status.
$seller_id = 'seller_id_example'; // string | Return only seller campaigns belonging to the given seller.
$campaign_id = 56; // int | Return only seller campaigns associated with the given campaign.
$budget_status = 'budget_status_example'; // string | Return only seller campaigns whose budget has the given status.

try {
    $result = $apiInstance->getSellerCampaigns($authorization, $seller_status, $seller_id, $campaign_id, $budget_status);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getSellerCampaigns: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **seller_status** | **string**| Return only seller campaigns for sellers with the given status. | [optional]
 **seller_id** | **string**| Return only seller campaigns belonging to the given seller. | [optional]
 **campaign_id** | **int**| Return only seller campaigns associated with the given campaign. | [optional]
 **budget_status** | **string**| Return only seller campaigns whose budget has the given status. | [optional]

### Return type

[**\Criteo\Marketing\Model\SellerCampaignMessage[]**](../Model/SellerCampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSellerCampaignsBySeller

> \Criteo\Marketing\Model\SellerCampaignMessage[] getSellerCampaignsBySeller($seller_id, $authorization, $seller_status, $campaign_id, $budget_status)

Get a collection of seller campaigns for this seller.

Return a collection of seller campaigns for this seller filtered by optional filter parameters.  If all parameters are omitted the entire collection to which the user has  access is returned. Returned sellers must satisfy all supplied filter  criteria if multiple parameters are used.  See the seller campaigns endpoint for additional details.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$seller_id = 'seller_id_example'; // string | Return only seller campaigns belonging to the given seller.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$seller_status = 'seller_status_example'; // string | Return only seller campaigns for sellers with the given status.
$campaign_id = 56; // int | Return only seller campaigns associated with the given campaign.
$budget_status = 'budget_status_example'; // string | Return only seller campaigns whose budget has the given status.

try {
    $result = $apiInstance->getSellerCampaignsBySeller($seller_id, $authorization, $seller_status, $campaign_id, $budget_status);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getSellerCampaignsBySeller: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seller_id** | **string**| Return only seller campaigns belonging to the given seller. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **seller_status** | **string**| Return only seller campaigns for sellers with the given status. | [optional]
 **campaign_id** | **int**| Return only seller campaigns associated with the given campaign. | [optional]
 **budget_status** | **string**| Return only seller campaigns whose budget has the given status. | [optional]

### Return type

[**\Criteo\Marketing\Model\SellerCampaignMessage[]**](../Model/SellerCampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getSellers

> \Criteo\Marketing\Model\SellerBase[] getSellers($authorization, $seller_status, $with_products, $with_budget_status, $seller_name)

Get a collection of sellers.

Return a collection of sellers filtered by optional filter parameters.  If all parameters are omitted the entire collection to which the user has  access is returned. Returned sellers must satisfy all supplied filter  criteria if multiple parameters are used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$seller_status = 'seller_status_example'; // string | Return only sellers with specific status.
$with_products = True; // bool | Return only sellers with or without products in catalog.
$with_budget_status = 'with_budget_status_example'; // string | Return only sellers with specific budget status.
$seller_name = 'seller_name_example'; // string | Return only sellers with the matching name.

try {
    $result = $apiInstance->getSellers($authorization, $seller_status, $with_products, $with_budget_status, $seller_name);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->getSellers: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **seller_status** | **string**| Return only sellers with specific status. | [optional]
 **with_products** | **bool**| Return only sellers with or without products in catalog. | [optional]
 **with_budget_status** | **string**| Return only sellers with specific budget status. | [optional]
 **seller_name** | **string**| Return only sellers with the matching name. | [optional]

### Return type

[**\Criteo\Marketing\Model\SellerBase[]**](../Model/SellerBase.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## updateSellerBudget

> \Criteo\Marketing\Model\SellerBudgetMessage updateSellerBudget($budget_id, $authorization, $message)

Modify a single budget.

Modify an existing active budget to change its limitations or status.  All three types of budgets can be modified.                See the additional restrictions listed in the PATCH budgets endpoint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$budget_id = 56; // int | 
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$message = new \Criteo\Marketing\Model\UpdateSellerBudgetMessageBase(); // \Criteo\Marketing\Model\UpdateSellerBudgetMessageBase | 

try {
    $result = $apiInstance->updateSellerBudget($budget_id, $authorization, $message);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->updateSellerBudget: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **budget_id** | **int**|  |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **message** | [**\Criteo\Marketing\Model\UpdateSellerBudgetMessageBase**](../Model/UpdateSellerBudgetMessageBase.md)|  |

### Return type

[**\Criteo\Marketing\Model\SellerBudgetMessage**](../Model/SellerBudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## updateSellerBudgets

> \Criteo\Marketing\Model\SellerBudgetMessage[] updateSellerBudgets($authorization, $update_seller_budgets)

Modify a collection of budgets.

Modify one or more existing active budgets to change their limitations or status.  All three types of budgets can be modified.                The following constraints apply when modifying an existing budget.                • <b>campaignIds</b>: a non-empty subset of the original campaign ids MAY be supplied<br />  • <b>amount</b>: an amount MAY be supplied only if the type is not Uncapped and if supplied it MUST be non-negative<br />  • <b>startDate</b>: a future start date MAY be supplied for budgets that have not yet started<br />  • <b>endDate</b>: an end date MAY be supplied and if supplied MUST be a future date greater than the start date<br />                Other attributes MUST NOT be supplied.                Adding new campaigns to a budget is not allowed. In addition, reducing the amount for  a Capped budget to a value less than the current spend not allowed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$update_seller_budgets = array(new \Criteo\Marketing\Model\UpdateSellerBudgetMessage()); // \Criteo\Marketing\Model\UpdateSellerBudgetMessage[] | 

try {
    $result = $apiInstance->updateSellerBudgets($authorization, $update_seller_budgets);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->updateSellerBudgets: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **update_seller_budgets** | [**\Criteo\Marketing\Model\UpdateSellerBudgetMessage[]**](../Model/UpdateSellerBudgetMessage.md)|  |

### Return type

[**\Criteo\Marketing\Model\SellerBudgetMessage[]**](../Model/SellerBudgetMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## updateSellerCampaign

> \Criteo\Marketing\Model\SellerCampaignMessage updateSellerCampaign($seller_campaign_id, $bid, $authorization)

Update an existing seller campaign.

Patching a seller campaign allows the bid to be modified. The bid must be a non-negative value.  Setting the bid to zero will make a seller campaign inactive.                The currency used for bids will be the default currency of the campaign.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$seller_campaign_id = 'seller_campaign_id_example'; // string | Id of the existing seller campaign to update
$bid = 3.4; // double | The new bid for the seller campaign.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->updateSellerCampaign($seller_campaign_id, $bid, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->updateSellerCampaign: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seller_campaign_id** | **string**| Id of the existing seller campaign to update |
 **bid** | **double**| The new bid for the seller campaign. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

[**\Criteo\Marketing\Model\SellerCampaignMessage**](../Model/SellerCampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## updateSellerCampaigns

> \Criteo\Marketing\Model\SellerCampaignMessage[] updateSellerCampaigns($authorization, $campaign_messages)

Update a collection of seller campaigns.

Patching a collection of seller campaigns allows their bids to be modified.  Each bid must be a non-negative value. Setting the bid to zero will make a seller campaign inactive.                The currency used for bids will be the default currency of the campaign.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\SellersV2Api(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$campaign_messages = array(new \Criteo\Marketing\Model\SellerCampaignUpdate()); // \Criteo\Marketing\Model\SellerCampaignUpdate[] | 

try {
    $result = $apiInstance->updateSellerCampaigns($authorization, $campaign_messages);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SellersV2Api->updateSellerCampaigns: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **campaign_messages** | [**\Criteo\Marketing\Model\SellerCampaignUpdate[]**](../Model/SellerCampaignUpdate.md)|  |

### Return type

[**\Criteo\Marketing\Model\SellerCampaignMessage[]**](../Model/SellerCampaignMessage.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

