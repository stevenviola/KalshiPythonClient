# Market

Market Contains information about a market. Note: for some fields, you should not assume a fixed structure.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**can_close_early** | **bool** |  | [optional] 
**category** | **str** |  | [optional] 
**close_date** | **datetime** |  | [optional] 
**close_unconfirmed** | **bool** |  | [optional] 
**create_date** | **datetime** |  | [optional] 
**description_case_no** | **str** |  | [optional] 
**description_case_yes** | **str** |  | [optional] 
**description_context** | **str** |  | [optional] 
**dollar_open_interest** | **int** |  | [optional] 
**dollar_recent_volume** | **int** |  | [optional] 
**dollar_volume** | **int** |  | [optional] 
**expiration_date** | **datetime** |  | [optional] 
**expiration_value** | **str** |  | [optional] 
**frequency_in_days** | **int** |  | [optional] 
**id** | **str** |  | [optional] 
**image_url** | **str** |  | [optional] 
**last_price** | **int** |  | [optional] 
**liquidity** | **int** |  | [optional] 
**list_date** | **datetime** |  | [optional] 
**metrics_tags** | **[str]** |  | [optional] 
**min_tick_size** | **str** |  | [optional] 
**mini_title** | **str** |  | [optional] 
**name** | **str** |  | [optional] 
**open_date** | **datetime** |  | [optional] 
**open_interest** | **int** |  | [optional] 
**option_type** | **str** |  | [optional] 
**original_expiration_date** | **datetime** |  | [optional] 
**previous_price** | **int** |  | [optional] 
**previous_yes_ask** | **int** |  | [optional] 
**previous_yes_bid** | **int** |  | [optional] 
**ranged_group_name** | **str** |  | [optional] 
**ranged_group_ticker** | **str** |  | [optional] 
**recent_volume** | **int** |  | [optional] 
**result** | **str** |  | [optional] 
**rulebook_variables** | **{str: (str,)}, none_type** | You should not assume a fixed structure for this field. It is subject to change from market to market. | [optional] 
**settle_details** | **str** |  | [optional] 
**settlement_sources** | [**[SettlementSource]**](SettlementSource.md) |  | [optional] 
**status** | **str** |  | [optional] 
**strike_price** | **float** |  | [optional] 
**sub_title** | **str** |  | [optional] 
**tags** | **[str]** |  | [optional] 
**ticker_name** | **str** |  | [optional] 
**title** | **str** |  | [optional] 
**underlying** | **str** |  | [optional] 
**volume** | **int** |  | [optional] 
**yes_ask** | **int** |  | [optional] 
**yes_bid** | **int** |  | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


