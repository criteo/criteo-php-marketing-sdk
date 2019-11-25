# # CatalogProduct

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**batch_id** | **int** | Mandatory. batch Id, set by the partner. Use to future deduplication | [optional] 
**catalog_id** | **int** | Mandatory. The criteo catalog (partner) Id | [optional] 
**method** | **string** | Mandatory. Method type, the acceptable values are insert and delete | [optional] 
**product_id** | **string** | Mandatory if the method is delete. This is the id of the product to delete in the partner catalog | [optional] 
**item_group_id** | **string** | Mandatory if the method is delete and the product is a variant. This id is the grouping key (parent id) for variants | [optional] 
**product** | [**\Criteo\Marketing\Model\GoogleProduct**](GoogleProduct.md) |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)


