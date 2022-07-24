# kalshi.MarketApi

All URIs are relative to *https://trading-api.kalshi.com/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_active_markets**](MarketApi.md#get_active_markets) | **GET** /active_markets | GetActiveMarkets
[**get_candlestick_market_history**](MarketApi.md#get_candlestick_market_history) | **GET** /markets/{market_id}/candlestick | GetCandlestickMarketHistory
[**get_candlestick_market_history_cached**](MarketApi.md#get_candlestick_market_history_cached) | **GET** /cached/markets/{market_id}/candlestick | GetCandlestickMarketHistoryCached
[**get_market**](MarketApi.md#get_market) | **GET** /markets/{market_id} | GetMarket
[**get_market_by_ticker**](MarketApi.md#get_market_by_ticker) | **GET** /markets_by_ticker/{ticker_name} | GetMarketByTicker
[**get_market_by_ticker_cached**](MarketApi.md#get_market_by_ticker_cached) | **GET** /cached/markets_by_ticker/{ticker_name} | GetMarketByTickerCached
[**get_market_cached**](MarketApi.md#get_market_cached) | **GET** /cached/markets/{market_id} | GetMarketCached
[**get_market_history**](MarketApi.md#get_market_history) | **GET** /markets/{market_id}/stats_history | GetMarketHistory
[**get_market_history_cached**](MarketApi.md#get_market_history_cached) | **GET** /cached/markets/{market_id}/stats_history | GetMarketHistoryCached
[**get_market_order_book**](MarketApi.md#get_market_order_book) | **GET** /markets/{market_id}/order_book | GetMarketOrderBook
[**get_market_order_book_cached**](MarketApi.md#get_market_order_book_cached) | **GET** /cached/markets/{market_id}/order_book | GetMarketOrderBookCached
[**get_markets**](MarketApi.md#get_markets) | **GET** /markets | GetMarkets
[**get_markets_cached**](MarketApi.md#get_markets_cached) | **GET** /cached/markets | GetMarketsCached


# **get_active_markets**
> GetActiveMarketsResponse get_active_markets()

GetActiveMarkets

End-point for getting highly active markets on the exchange. Currently, gets 3 kinds of activity: Markets opening within the time window provided, markets closing within the time window provided, and markets that have had large price movements or large volumes within the time window provided.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.get_active_markets_response import GetActiveMarketsResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    limit = 1 # int | The maximum number of markets returned, this is capped at 20 (optional)
    min_date = 1 # int | The lower bound on the date searched through when looking for activity (optional)
    max_date = 1 # int | The upper bound on the date searched through when looking for activity (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # GetActiveMarkets
        api_response = api_instance.get_active_markets(limit=limit, min_date=min_date, max_date=max_date)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_active_markets: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| The maximum number of markets returned, this is capped at 20 | [optional]
 **min_date** | **int**| The lower bound on the date searched through when looking for activity | [optional]
 **max_date** | **int**| The upper bound on the date searched through when looking for activity | [optional]

### Return type

[**GetActiveMarketsResponse**](GetActiveMarketsResponse.md)

### Authorization

No authorization required

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

# **get_candlestick_market_history**
> GetCandlestickMarketHistoryResponse get_candlestick_market_history(market_id)

GetCandlestickMarketHistory

End-point for getting open, high, low, close (OHLC) and other data for candlestick plots. See the response body for full information on what is returned.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.get_candlestick_market_history_response import GetCandlestickMarketHistoryResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market
    last_seen_ts = 1 # int | If provided, restricts history to trades starting from lastSeenTs (optional)
    num_buckets = 1 # int | If provided, this field represents the number of buckets used to divide the market history data. Please provide an integer between 1 and 7,200 (inclusive). Defaults to 1,400. We aggregate data in the buckets. (optional)

    # example passing only required values which don't have defaults set
    try:
        # GetCandlestickMarketHistory
        api_response = api_instance.get_candlestick_market_history(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_candlestick_market_history: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # GetCandlestickMarketHistory
        api_response = api_instance.get_candlestick_market_history(market_id, last_seen_ts=last_seen_ts, num_buckets=num_buckets)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_candlestick_market_history: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |
 **last_seen_ts** | **int**| If provided, restricts history to trades starting from lastSeenTs | [optional]
 **num_buckets** | **int**| If provided, this field represents the number of buckets used to divide the market history data. Please provide an integer between 1 and 7,200 (inclusive). Defaults to 1,400. We aggregate data in the buckets. | [optional]

### Return type

[**GetCandlestickMarketHistoryResponse**](GetCandlestickMarketHistoryResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetCandlestickMarketHistoryResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_candlestick_market_history_cached**
> GetCandlestickMarketHistoryResponse get_candlestick_market_history_cached(market_id)

GetCandlestickMarketHistoryCached

End-point for getting open, high, low, close (OHLC) and other data for candlestick plots. See the response body for full information on what is returned. Data is cached and so is slightly lagged.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.get_candlestick_market_history_response import GetCandlestickMarketHistoryResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market
    last_seen_ts = 1 # int | If provided, restricts history to trades starting from lastSeenTs (optional)
    num_buckets = 1 # int | If provided, this field represents the number of buckets used to divide the market history data. Please provide an integer between 1 and 7,200 (inclusive). Defaults to 1,400. We aggregate data in the buckets. (optional)

    # example passing only required values which don't have defaults set
    try:
        # GetCandlestickMarketHistoryCached
        api_response = api_instance.get_candlestick_market_history_cached(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_candlestick_market_history_cached: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # GetCandlestickMarketHistoryCached
        api_response = api_instance.get_candlestick_market_history_cached(market_id, last_seen_ts=last_seen_ts, num_buckets=num_buckets)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_candlestick_market_history_cached: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |
 **last_seen_ts** | **int**| If provided, restricts history to trades starting from lastSeenTs | [optional]
 **num_buckets** | **int**| If provided, this field represents the number of buckets used to divide the market history data. Please provide an integer between 1 and 7,200 (inclusive). Defaults to 1,400. We aggregate data in the buckets. | [optional]

### Return type

[**GetCandlestickMarketHistoryResponse**](GetCandlestickMarketHistoryResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetCandlestickMarketHistoryResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_market**
> UserGetMarketResponse get_market(market_id)

GetMarket

End-point for getting data about a specific market.  The value for the market_id path parameter should match the id value of the target market.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.user_get_market_response import UserGetMarketResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market

    # example passing only required values which don't have defaults set
    try:
        # GetMarket
        api_response = api_instance.get_market(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |

### Return type

[**UserGetMarketResponse**](UserGetMarketResponse.md)

### Authorization

No authorization required

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

# **get_market_by_ticker**
> UserGetMarketResponse get_market_by_ticker(ticker_name)

GetMarketByTicker

End-point for getting data about a specific market based on its ticker.  The value for the ticker_name path parameter should match the ticker_name value of the target market.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.user_get_market_response import UserGetMarketResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    ticker_name = "ticker_name_example" # str | Should be filled with the ticker name of the target market

    # example passing only required values which don't have defaults set
    try:
        # GetMarketByTicker
        api_response = api_instance.get_market_by_ticker(ticker_name)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_by_ticker: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ticker_name** | **str**| Should be filled with the ticker name of the target market |

### Return type

[**UserGetMarketResponse**](UserGetMarketResponse.md)

### Authorization

No authorization required

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

# **get_market_by_ticker_cached**
> UserGetMarketResponse get_market_by_ticker_cached(ticker_name)

GetMarketByTickerCached

End-point for getting data about a specific market with data that is cached and so slightly lagged.  The value for the ticker_name path parameter should match the ticker_name value of the target market.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.user_get_market_response import UserGetMarketResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    ticker_name = "ticker_name_example" # str | Should be filled with the ticker name of the target market

    # example passing only required values which don't have defaults set
    try:
        # GetMarketByTickerCached
        api_response = api_instance.get_market_by_ticker_cached(ticker_name)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_by_ticker_cached: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ticker_name** | **str**| Should be filled with the ticker name of the target market |

### Return type

[**UserGetMarketResponse**](UserGetMarketResponse.md)

### Authorization

No authorization required

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

# **get_market_cached**
> UserGetMarketResponse get_market_cached(market_id)

GetMarketCached

End-point for getting data about a specific market with data that is cached and so slightly lagged.  The value for the market_id path parameter should match the id value of the target market.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.user_get_market_response import UserGetMarketResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market

    # example passing only required values which don't have defaults set
    try:
        # GetMarketCached
        api_response = api_instance.get_market_cached(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_cached: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |

### Return type

[**UserGetMarketResponse**](UserGetMarketResponse.md)

### Authorization

No authorization required

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

# **get_market_history**
> GetMarketHistoryResponse get_market_history(market_id)

GetMarketHistory

End-point for getting the statistics history for a market.  The value for the market_id path parameter should match the id value of the target market. The last_seen_ts parameter is optional, and will restrict statistics to those after provided timestamp. The last_seen_ts is inclusive, which means a market history point at last_seen_ts will be returned

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.get_market_history_response import GetMarketHistoryResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market
    last_seen_ts = 1 # int | If provided, restricts history to trades starting from lastSeenTs (optional)
    num_buckets = 1 # int | If provided, this field represents the number of buckets used to group the market price history data. Please provide an integer between 1 and 7,200 (inclusive). The higher this value, the more points will be returned from this endpoint. Note that the number of points returned may not be equal to the number of buckets because some buckets may not contain any points. Defaults to 1,400. We pick one representative point from each bucket (namely the last point in the bucket) (optional)

    # example passing only required values which don't have defaults set
    try:
        # GetMarketHistory
        api_response = api_instance.get_market_history(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_history: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # GetMarketHistory
        api_response = api_instance.get_market_history(market_id, last_seen_ts=last_seen_ts, num_buckets=num_buckets)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_history: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |
 **last_seen_ts** | **int**| If provided, restricts history to trades starting from lastSeenTs | [optional]
 **num_buckets** | **int**| If provided, this field represents the number of buckets used to group the market price history data. Please provide an integer between 1 and 7,200 (inclusive). The higher this value, the more points will be returned from this endpoint. Note that the number of points returned may not be equal to the number of buckets because some buckets may not contain any points. Defaults to 1,400. We pick one representative point from each bucket (namely the last point in the bucket) | [optional]

### Return type

[**GetMarketHistoryResponse**](GetMarketHistoryResponse.md)

### Authorization

No authorization required

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

# **get_market_history_cached**
> GetMarketHistoryResponse get_market_history_cached(market_id)

GetMarketHistoryCached

End-point for getting the statistics history for a market with data that is cached and so slightly lagged.  The value for the market_id path parameter should match the id value of the target market. The last_seen_ts parameter is optional, and will restrict statistics to those after provided timestamp. The last_seen_ts is inclusive, which means a market history point at last_seen_ts will be returned

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.get_market_history_response import GetMarketHistoryResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market
    last_seen_ts = 1 # int | If provided, restricts history to trades starting from lastSeenTs (optional)
    num_buckets = 1 # int | If provided, this field represents the number of buckets used to group the market price history data. Please provide an integer between 1 and 7,200 (inclusive). The higher this value, the more points will be returned from this endpoint. Note that the number of points returned may not be equal to the number of buckets because some buckets may not contain any points. Defaults to 1,400. We pick one representative point from each bucket (namely the last point in the bucket) (optional)

    # example passing only required values which don't have defaults set
    try:
        # GetMarketHistoryCached
        api_response = api_instance.get_market_history_cached(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_history_cached: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # GetMarketHistoryCached
        api_response = api_instance.get_market_history_cached(market_id, last_seen_ts=last_seen_ts, num_buckets=num_buckets)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_history_cached: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |
 **last_seen_ts** | **int**| If provided, restricts history to trades starting from lastSeenTs | [optional]
 **num_buckets** | **int**| If provided, this field represents the number of buckets used to group the market price history data. Please provide an integer between 1 and 7,200 (inclusive). The higher this value, the more points will be returned from this endpoint. Note that the number of points returned may not be equal to the number of buckets because some buckets may not contain any points. Defaults to 1,400. We pick one representative point from each bucket (namely the last point in the bucket) | [optional]

### Return type

[**GetMarketHistoryResponse**](GetMarketHistoryResponse.md)

### Authorization

No authorization required

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

# **get_market_order_book**
> GetMarketOrderBookResponse get_market_order_book(market_id)

GetMarketOrderBook

End-point for getting the orderbook for a market.  The value for the market_id path parameter should match the id value of the target market.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.get_market_order_book_response import GetMarketOrderBookResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market

    # example passing only required values which don't have defaults set
    try:
        # GetMarketOrderBook
        api_response = api_instance.get_market_order_book(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_order_book: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |

### Return type

[**GetMarketOrderBookResponse**](GetMarketOrderBookResponse.md)

### Authorization

No authorization required

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

# **get_market_order_book_cached**
> GetMarketOrderBookResponse get_market_order_book_cached(market_id)

GetMarketOrderBookCached

End-point for getting the orderbook for a market with data that is cached and so slightly lagged.  The value for the market_id path parameter should match the id value of the target market.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.get_market_order_book_response import GetMarketOrderBookResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)
    market_id = "market_id_example" # str | Should be filled with the id of the target market

    # example passing only required values which don't have defaults set
    try:
        # GetMarketOrderBookCached
        api_response = api_instance.get_market_order_book_cached(market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_market_order_book_cached: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **market_id** | **str**| Should be filled with the id of the target market |

### Return type

[**GetMarketOrderBookResponse**](GetMarketOrderBookResponse.md)

### Authorization

No authorization required

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

# **get_markets**
> UserGetMarketsResponse get_markets()

GetMarkets

End-point for listing / discovering markets on Kalshi.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.user_get_markets_response import UserGetMarketsResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # GetMarkets
        api_response = api_instance.get_markets()
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_markets: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**UserGetMarketsResponse**](UserGetMarketsResponse.md)

### Authorization

No authorization required

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

# **get_markets_cached**
> UserGetMarketsResponse get_markets_cached()

GetMarketsCached

End-point for listing / discovering markets on Kalshi with data that is cached and so slightly lagged.

### Example


```python
import time
import kalshi
from kalshi.api import market_api
from kalshi.model.user_get_markets_response import UserGetMarketsResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = market_api.MarketApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # GetMarketsCached
        api_response = api_instance.get_markets_cached()
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling MarketApi->get_markets_cached: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**UserGetMarketsResponse**](UserGetMarketsResponse.md)

### Authorization

No authorization required

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

