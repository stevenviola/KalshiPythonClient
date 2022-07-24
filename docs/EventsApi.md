# kalshi.EventsApi

All URIs are relative to *https://trading-api.kalshi.com/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_event_by_ticker_cached**](EventsApi.md#get_event_by_ticker_cached) | **GET** /events/{ticker} | GetEventByTickerCached


# **get_event_by_ticker_cached**
> GetEventByTickerResponse get_event_by_ticker_cached(ticker)

GetEventByTickerCached

End-point for getting data about an event by its ticker with data that is cached and so slightly lagged.

### Example


```python
import time
import kalshi
from kalshi.api import events_api
from kalshi.model.get_event_by_ticker_response import GetEventByTickerResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = events_api.EventsApi(api_client)
    ticker = "ticker_example" # str | Should be the ticker of the event

    # example passing only required values which don't have defaults set
    try:
        # GetEventByTickerCached
        api_response = api_instance.get_event_by_ticker_cached(ticker)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling EventsApi->get_event_by_ticker_cached: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ticker** | **str**| Should be the ticker of the event |

### Return type

[**GetEventByTickerResponse**](GetEventByTickerResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetEventByTickerResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**404** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

