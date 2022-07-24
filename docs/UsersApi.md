# kalshi.UsersApi

All URIs are relative to *https://trading-api.kalshi.com/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_user_immediate_funding**](UsersApi.md#get_user_immediate_funding) | **GET** /users/{user_id}/immediate_funding | GetUserImmediateFunding
[**get_user_withdrawal_available_balance**](UsersApi.md#get_user_withdrawal_available_balance) | **GET** /users/{user_id}/withdrawals/available | GetUserWithdrawalAvailableBalance


# **get_user_immediate_funding**
> GetUserImmediateFundingResponse get_user_immediate_funding(user_id)

GetUserImmediateFunding

End-point for getting immediate funding info for a member.

### Example

* Api Key Authentication (cookie):

```python
import time
import kalshi
from kalshi.api import users_api
from kalshi.model.get_user_immediate_funding_response import GetUserImmediateFundingResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: cookie
configuration.api_key['cookie'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['cookie'] = 'Bearer'

# Enter a context with an instance of the API client
with kalshi.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = users_api.UsersApi(api_client)
    user_id = "user_id_example" # str | This parameter should be filled with your user_id provided on log_in
    deposit_amount_cents = 1 # int | Pass this parameter if you'd like to see how much of a deposit will be funded by immediate funding. If you don't need this information, pass 0 cents. (optional)

    # example passing only required values which don't have defaults set
    try:
        # GetUserImmediateFunding
        api_response = api_instance.get_user_immediate_funding(user_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling UsersApi->get_user_immediate_funding: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # GetUserImmediateFunding
        api_response = api_instance.get_user_immediate_funding(user_id, deposit_amount_cents=deposit_amount_cents)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling UsersApi->get_user_immediate_funding: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **str**| This parameter should be filled with your user_id provided on log_in |
 **deposit_amount_cents** | **int**| Pass this parameter if you&#39;d like to see how much of a deposit will be funded by immediate funding. If you don&#39;t need this information, pass 0 cents. | [optional]

### Return type

[**GetUserImmediateFundingResponse**](GetUserImmediateFundingResponse.md)

### Authorization

[cookie](../README.md#cookie)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetUserImmediateFundingResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_user_withdrawal_available_balance**
> UserWithdrawalAvailableBalanceResponse get_user_withdrawal_available_balance(user_id)

GetUserWithdrawalAvailableBalance

End-point for getting how much money a member is elgible to withdraw

### Example

* Api Key Authentication (cookie):

```python
import time
import kalshi
from kalshi.api import users_api
from kalshi.model.user_withdrawal_available_balance_response import UserWithdrawalAvailableBalanceResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: cookie
configuration.api_key['cookie'] = 'YOUR_API_KEY'

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['cookie'] = 'Bearer'

# Enter a context with an instance of the API client
with kalshi.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = users_api.UsersApi(api_client)
    user_id = "user_id_example" # str | This parameter should be filled with your user_id provided on log_in

    # example passing only required values which don't have defaults set
    try:
        # GetUserWithdrawalAvailableBalance
        api_response = api_instance.get_user_withdrawal_available_balance(user_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling UsersApi->get_user_withdrawal_available_balance: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **str**| This parameter should be filled with your user_id provided on log_in |

### Return type

[**UserWithdrawalAvailableBalanceResponse**](UserWithdrawalAvailableBalanceResponse.md)

### Authorization

[cookie](../README.md#cookie)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

