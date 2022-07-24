# UserOrderCreateRequest

Request for submitting an order

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** | Specifies how many contracts should be bought | 
**market_id** | **str** | Specifies the id of the market for this order | 
**price** | **int** |  | 
**side** | **str** | Specifies if this is a &#39;yes&#39; or &#39;no&#39; order | 
**expiration_unix_ts** | **int** | Specifies the expiration time of the order, in unix seconds.  If this is not supplied, or is 0, the order won&#39;t expire. | [optional] 
**max_cost_cents** | **int** |  | [optional] 
**order_action** | **str** | OrderAction specifies whether the user intends to buy or sell their position when placing this order. | [optional] 
**order_type** | **str** | Metadata fields for the frontend to record the context of the order. These fields DO NOT impact order placement. The non-metadata params above are used instead. OrderType specifies which order type the user placed. | [optional] 
**sell_position_capped** | **bool** | Specifies whether the order place count should be capped by the members current position. | [optional] 
**user_side** | **str** | UserSide specifies the side the user is working with when placing this order. This field does NOT impact the exchange&#39;s view of the order. For example, if a member is trying to sell a No position, the frontend would actually send a Yes order to the exchange. That order would have Side &#x3D;&#x3D; \&quot;Yes\&quot;, UserSide &#x3D;&#x3D; \&quot;No\&quot; and OrderAction &#x3D;&#x3D; \&quot;Sell\&quot;. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


