# kalshi.DefaultApi

All URIs are relative to *https://trading-api.kalshi.com/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_events_cached**](DefaultApi.md#get_events_cached) | **GET** /events/ | GetEventsCached
[**get_series_list**](DefaultApi.md#get_series_list) | **GET** /series/ | GetSeriesList
[**get_series_list_cached**](DefaultApi.md#get_series_list_cached) | **GET** /cached/series | GetSeriesListCached
[**get_trades**](DefaultApi.md#get_trades) | **GET** /trades | GetTrades


# **get_events_cached**
> GetEventsResponse get_events_cached()

GetEventsCached

End-point for getting data about all events with data that is cached and so slightly lagged.

### Example


```python
import time
import kalshi
from kalshi.api import default_api
from kalshi.model.get_events_response import GetEventsResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # GetEventsCached
        api_response = api_instance.get_events_cached()
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling DefaultApi->get_events_cached: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**GetEventsResponse**](GetEventsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetEventsResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**404** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_series_list**
> GetSeriesListResponse get_series_list()

GetSeriesList

End-point for getting data about all series

### Example


```python
import time
import kalshi
from kalshi.api import default_api
from kalshi.model.get_series_list_response import GetSeriesListResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # GetSeriesList
        api_response = api_instance.get_series_list()
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling DefaultApi->get_series_list: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**GetSeriesListResponse**](GetSeriesListResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetSeriesListResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**404** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_series_list_cached**
> GetSeriesListResponse get_series_list_cached()

GetSeriesListCached

End-point for getting data about all series. Endpoint is cached so it is slightly lagged.

### Example


```python
import time
import kalshi
from kalshi.api import default_api
from kalshi.model.get_series_list_response import GetSeriesListResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # GetSeriesListCached
        api_response = api_instance.get_series_list_cached()
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling DefaultApi->get_series_list_cached: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**GetSeriesListResponse**](GetSeriesListResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetSeriesListResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**404** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_trades**
> TradesGetResponse get_trades()

GetTrades

End-point for getting all trades for all markets.

### Example


```python
import time
import kalshi
from kalshi.api import default_api
from kalshi.model.trades_get_response import TradesGetResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = default_api.DefaultApi(api_client)
    trades_date = "trades_date_example" # str | Restricts the response to trades during a certain day (give trades_date in ET with format: YYYY-MM-DD). Dates returned will be UTC (optional)
    page_size = 1 # int | Parameter to specify the number of results per page (optional)
    page_number = 1 # int | Parameter to specify which page of the results should be retrieved (optional)
    market_id = "market_id_example" # str | Parameter to specify a specific marketId to get trades from (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # GetTrades
        api_response = api_instance.get_trades(trades_date=trades_date, page_size=page_size, page_number=page_number, market_id=market_id)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling DefaultApi->get_trades: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **trades_date** | **str**| Restricts the response to trades during a certain day (give trades_date in ET with format: YYYY-MM-DD). Dates returned will be UTC | [optional]
 **page_size** | **int**| Parameter to specify the number of results per page | [optional]
 **page_number** | **int**| Parameter to specify which page of the results should be retrieved | [optional]
 **market_id** | **str**| Parameter to specify a specific marketId to get trades from | [optional]

### Return type

[**TradesGetResponse**](TradesGetResponse.md)

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

