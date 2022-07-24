# DeprecatedUserGetPortfolioHistoryRequest

Request for fetching user portfolio history

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**max_date** | **datetime** | Restricts the response to orders before a timestamp in: query | [optional] 
**max_ts** | **int** | Restricts the response to orders before a timestamp in unix seconds, overrides max_date, defaults to now. in: query | [optional] 
**min_date** | **datetime** | Restricts the response to orders after a timestamp in: query | [optional] 
**min_ts** | **int** | Restricts the response to orders after a timestamp in unix seconds, overrides min_date, defaults to one hour before now. in: query | [optional] 
**num_buckets** | **int** | Determines the number of buckets to average over when performing subsampling, defaults to 1440. in: query | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


