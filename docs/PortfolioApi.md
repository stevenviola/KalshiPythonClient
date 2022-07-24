# kalshi.PortfolioApi

All URIs are relative to *https://trading-api.kalshi.com/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**deprecated_user_get_portfolio_history**](PortfolioApi.md#deprecated_user_get_portfolio_history) | **GET** /users/{user_id}/portfolio/ | DeprecatedUserGetPortfolioHistory
[**user_get_sampled_portfolio_history**](PortfolioApi.md#user_get_sampled_portfolio_history) | **GET** /users/{user_id}/sampled_portfolio/ | UserGetSampledPortfolioHistory


# **deprecated_user_get_portfolio_history**
> DeprecatedUserGetPortfolioHistoryResponse deprecated_user_get_portfolio_history(user_id)

DeprecatedUserGetPortfolioHistory

End-point for getting the logged in user's portfolio historical track.  The value for the user_id path parameter should match the user_id value returned on the response for the last login request (POST /log_in).

### Example

* Api Key Authentication (cookie):

```python
import time
import kalshi
from kalshi.api import portfolio_api
from kalshi.model.deprecated_user_get_portfolio_history_request import DeprecatedUserGetPortfolioHistoryRequest
from kalshi.model.deprecated_user_get_portfolio_history_response import DeprecatedUserGetPortfolioHistoryResponse
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
    api_instance = portfolio_api.PortfolioApi(api_client)
    user_id = "user_id_example" # str | This parameter should be filled with your user_id provided on log_in
    deprecated_user_get_portfolio_history_request = DeprecatedUserGetPortfolioHistoryRequest(
        max_date=dateutil_parser('1970-01-01T00:00:00.00Z'),
        max_ts=1,
        min_date=dateutil_parser('1970-01-01T00:00:00.00Z'),
        min_ts=1,
        num_buckets=1,
    ) # DeprecatedUserGetPortfolioHistoryRequest | Order create input data (optional)

    # example passing only required values which don't have defaults set
    try:
        # DeprecatedUserGetPortfolioHistory
        api_response = api_instance.deprecated_user_get_portfolio_history(user_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling PortfolioApi->deprecated_user_get_portfolio_history: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # DeprecatedUserGetPortfolioHistory
        api_response = api_instance.deprecated_user_get_portfolio_history(user_id, deprecated_user_get_portfolio_history_request=deprecated_user_get_portfolio_history_request)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling PortfolioApi->deprecated_user_get_portfolio_history: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **str**| This parameter should be filled with your user_id provided on log_in |
 **deprecated_user_get_portfolio_history_request** | [**DeprecatedUserGetPortfolioHistoryRequest**](DeprecatedUserGetPortfolioHistoryRequest.md)| Order create input data | [optional]

### Return type

[**DeprecatedUserGetPortfolioHistoryResponse**](DeprecatedUserGetPortfolioHistoryResponse.md)

### Authorization

[cookie](../README.md#cookie)

### HTTP request headers

 - **Content-Type**: application/json
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

# **user_get_sampled_portfolio_history**
> UserGetSampledPortfolioHistoryResponse user_get_sampled_portfolio_history(user_id)

UserGetSampledPortfolioHistory

End-point for getting the logged in user's portfolio historical track.  The value for the user_id path parameter should match the user_id value returned on the response for the last login request (POST /log_in).

### Example

* Api Key Authentication (cookie):

```python
import time
import kalshi
from kalshi.api import portfolio_api
from kalshi.model.user_get_sampled_portfolio_history_response import UserGetSampledPortfolioHistoryResponse
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
    api_instance = portfolio_api.PortfolioApi(api_client)
    user_id = "user_id_example" # str | Should be filled with your user_id provided on log_in

    # example passing only required values which don't have defaults set
    try:
        # UserGetSampledPortfolioHistory
        api_response = api_instance.user_get_sampled_portfolio_history(user_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling PortfolioApi->user_get_sampled_portfolio_history: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **str**| Should be filled with your user_id provided on log_in |

### Return type

[**UserGetSampledPortfolioHistoryResponse**](UserGetSampledPortfolioHistoryResponse.md)

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

