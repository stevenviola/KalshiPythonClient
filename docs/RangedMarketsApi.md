# kalshi.RangedMarketsApi

All URIs are relative to *https://trading-api.kalshi.com/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_ranged_market_by_ticker**](RangedMarketsApi.md#get_ranged_market_by_ticker) | **GET** /ranged_markets_by_ticker/{ticker} | GetRangedMarketByTicker
[**user_get_ranged_market_position**](RangedMarketsApi.md#user_get_ranged_market_position) | **GET** /users/{user_id}/ranged_positions/{ranged_market_id} | UserGetRangedMarketPosition


# **get_ranged_market_by_ticker**
> GetRangedMarketByTickerResponse get_ranged_market_by_ticker(ticker)

GetRangedMarketByTicker

End-point for getting data about a ranged market by its ticker

### Example


```python
import time
import kalshi
from kalshi.api import ranged_markets_api
from kalshi.model.get_ranged_market_by_ticker_response import GetRangedMarketByTickerResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = ranged_markets_api.RangedMarketsApi(api_client)
    ticker = "ticker_example" # str | Should be the ticker of the ranged market

    # example passing only required values which don't have defaults set
    try:
        # GetRangedMarketByTicker
        api_response = api_instance.get_ranged_market_by_ticker(ticker)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling RangedMarketsApi->get_ranged_market_by_ticker: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ticker** | **str**| Should be the ticker of the ranged market |

### Return type

[**GetRangedMarketByTickerResponse**](GetRangedMarketByTickerResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetRangedMarketByTickerResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**404** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **user_get_ranged_market_position**
> UserGetRangedMarketPositionResponse user_get_ranged_market_position(user_id, ranged_market_id)

UserGetRangedMarketPosition

End-point for getting the market positions and additional data for the logged in user for all markets whose results linked by a single outcome. These markets share a parameter ranged_market_id, which indicates their relationship with each other.  The value for the user_id path parameter should match the user_id value returned on the response for the last login request (POST /log_in).  The value for the ranged_market_id path parameter should match the id value of the target market.

### Example

* Api Key Authentication (cookie):

```python
import time
import kalshi
from kalshi.api import ranged_markets_api
from kalshi.model.user_get_ranged_market_position_response import UserGetRangedMarketPositionResponse
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
    api_instance = ranged_markets_api.RangedMarketsApi(api_client)
    user_id = "user_id_example" # str | Should be filled in with your user_id provided on log_in
    ranged_market_id = "ranged_market_id_example" # str | Should be filled with the id of the target ranged market

    # example passing only required values which don't have defaults set
    try:
        # UserGetRangedMarketPosition
        api_response = api_instance.user_get_ranged_market_position(user_id, ranged_market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling RangedMarketsApi->user_get_ranged_market_position: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **user_id** | **str**| Should be filled in with your user_id provided on log_in |
 **ranged_market_id** | **str**| Should be filled with the id of the target ranged market |

### Return type

[**UserGetRangedMarketPositionResponse**](UserGetRangedMarketPositionResponse.md)

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
**404** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

