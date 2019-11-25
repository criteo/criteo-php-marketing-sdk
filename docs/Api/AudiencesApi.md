# Criteo\Marketing\AudiencesApi

All URIs are relative to *https://api.criteo.com/marketing*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addRemoveUsersToAudience**](AudiencesApi.md#addRemoveUsersToAudience) | **PATCH** /v1/audiences/userlist/{audienceId} | Add/Remove users to an Audience.
[**createAudience**](AudiencesApi.md#createAudience) | **POST** /v1/audiences/userlist | Create a new Audience.
[**deleteAudience**](AudiencesApi.md#deleteAudience) | **DELETE** /v1/audiences/{audienceId} | Delete an Audience.
[**getAudiences**](AudiencesApi.md#getAudiences) | **GET** /v1/audiences | Get the list of Audiences.
[**removeUsersFromAudience**](AudiencesApi.md#removeUsersFromAudience) | **DELETE** /v1/audiences/userlist/{audienceId}/users | Remove all users from an Audience.
[**updateAudienceMetadata**](AudiencesApi.md#updateAudienceMetadata) | **PUT** /v1/audiences/{audienceId} | Update an Audience metadata.



## addRemoveUsersToAudience

> \Criteo\Marketing\Model\AudiencePatchResponse addRemoveUsersToAudience($audience_id, $authorization, $request)

Add/Remove users to an Audience.

Add/Remove users to an Audience.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AudiencesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$audience_id = 56; // int | Mandatory. The id of the audience to add or remove users to.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$request = new \Criteo\Marketing\Model\AudiencePatchRequest(); // \Criteo\Marketing\Model\AudiencePatchRequest | Mandatory. The request to create the Audience.

try {
    $result = $apiInstance->addRemoveUsersToAudience($audience_id, $authorization, $request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AudiencesApi->addRemoveUsersToAudience: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **audience_id** | **int**| Mandatory. The id of the audience to add or remove users to. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **request** | [**\Criteo\Marketing\Model\AudiencePatchRequest**](../Model/AudiencePatchRequest.md)| Mandatory. The request to create the Audience. |

### Return type

[**\Criteo\Marketing\Model\AudiencePatchResponse**](../Model/AudiencePatchResponse.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## createAudience

> \Criteo\Marketing\Model\AudienceCreateResponse createAudience($authorization, $create_request)

Create a new Audience.

Create a new Audience for the given Advertiser.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AudiencesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$create_request = new \Criteo\Marketing\Model\AudienceCreateRequest(); // \Criteo\Marketing\Model\AudienceCreateRequest | 

try {
    $result = $apiInstance->createAudience($authorization, $create_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AudiencesApi->createAudience: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **create_request** | [**\Criteo\Marketing\Model\AudienceCreateRequest**](../Model/AudienceCreateRequest.md)|  |

### Return type

[**\Criteo\Marketing\Model\AudienceCreateResponse**](../Model/AudienceCreateResponse.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## deleteAudience

> object deleteAudience($audience_id, $authorization)

Delete an Audience.

Delete an Audience.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AudiencesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$audience_id = 56; // int | Mandatory. The id of the audience to delete.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->deleteAudience($audience_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AudiencesApi->deleteAudience: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **audience_id** | **int**| Mandatory. The id of the audience to delete. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

**object**

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## getAudiences

> \Criteo\Marketing\Model\AudiencesGetResponse getAudiences($authorization, $advertiser_id)

Get the list of Audiences.

Get the list of Audiences for the given Advertiser.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AudiencesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$advertiser_id = 56; // int | Mandatory. Advertiser to get all Audiences for.

try {
    $result = $apiInstance->getAudiences($authorization, $advertiser_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AudiencesApi->getAudiences: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **advertiser_id** | **int**| Mandatory. Advertiser to get all Audiences for. | [optional]

### Return type

[**\Criteo\Marketing\Model\AudiencesGetResponse**](../Model/AudiencesGetResponse.md)

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## removeUsersFromAudience

> object removeUsersFromAudience($audience_id, $authorization)

Remove all users from an Audience.

Remove all users from an Audience.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AudiencesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$audience_id = 56; // int | Mandatory. The id of the audience to empty.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token

try {
    $result = $apiInstance->removeUsersFromAudience($audience_id, $authorization);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AudiencesApi->removeUsersFromAudience: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **audience_id** | **int**| Mandatory. The id of the audience to empty. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]

### Return type

**object**

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)


## updateAudienceMetadata

> object updateAudienceMetadata($audience_id, $authorization, $request)

Update an Audience metadata.

Update an Audience metadata.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: Authorization
$config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKey('Authorization', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Criteo\Marketing\Configuration::getDefaultConfiguration()->setApiKeyPrefix('Authorization', 'Bearer');


$apiInstance = new Criteo\Marketing\Api\AudiencesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$audience_id = 56; // int | Mandatory. The id of the Audience to update.
$authorization = 'Bearer VALID_JWT_TOKEN_BASE64'; // string | JWT Bearer Token
$request = new \Criteo\Marketing\Model\AudiencePutRequest(); // \Criteo\Marketing\Model\AudiencePutRequest | Mandatory. The request to update the Audience metadata.

try {
    $result = $apiInstance->updateAudienceMetadata($audience_id, $authorization, $request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AudiencesApi->updateAudienceMetadata: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **audience_id** | **int**| Mandatory. The id of the Audience to update. |
 **authorization** | **string**| JWT Bearer Token | [default to &#39;Bearer VALID_JWT_TOKEN_BASE64&#39;]
 **request** | [**\Criteo\Marketing\Model\AudiencePutRequest**](../Model/AudiencePutRequest.md)| Mandatory. The request to update the Audience metadata. |

### Return type

**object**

### Authorization

[Authorization](../../README.md#Authorization)

### HTTP request headers

- **Content-Type**: application/json, text/json, application/xml, text/xml, application/x-www-form-urlencoded, text/html
- **Accept**: application/json, text/json, application/xml, text/xml, text/html

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../../README.md#documentation-for-models)
[[Back to README]](../../README.md)

