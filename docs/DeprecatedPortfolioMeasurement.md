# DeprecatedPortfolioMeasurement

Deprecated Portfolio measurement is simply a snapshot of the portfolio of a user on a timestamp.  This is going to get deprecated soon.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**a** | **int** |  | 
**cumulative_deposits** | **int** |  | 
**cumulative_number_settlements** | **int** | Count of settlements member has had from account creation to timestamp (inclusive) | 
**cumulative_withdrawals** | **int** |  | 
**ts** | **int** | Timestamp of the read in UNIX timestamp. (https://www.unixtimestamp.com/) | 
**v** | **int** |  | 
**balance_change** | **int** |  | [optional] 
**reason** | **str** | Reasons for the portfolio value change, if applicable | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


