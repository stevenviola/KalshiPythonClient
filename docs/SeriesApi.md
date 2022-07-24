# kalshi.SeriesApi

All URIs are relative to *https://trading-api.kalshi.com/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_series_by_ticker**](SeriesApi.md#get_series_by_ticker) | **GET** /series/{series_ticker} | GetSeriesByTicker


# **get_series_by_ticker**
> GetSeriesByTickerResponse get_series_by_ticker(series_ticker)

GetSeriesByTicker

End-point for getting data about an event by its ticker

### Example


```python
import time
import kalshi
from kalshi.api import series_api
from kalshi.model.get_series_by_ticker_response import GetSeriesByTickerResponse
from pprint import pprint
# Defining the host is optional and defaults to https://trading-api.kalshi.com/v1
# See configuration.py for a list of all supported configuration parameters.
configuration = kalshi.Configuration(
    host = "https://trading-api.kalshi.com/v1"
)


# Enter a context with an instance of the API client
with kalshi.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = series_api.SeriesApi(api_client)
    series_ticker = "series_ticker_example" # str | Should be the ticker of the series

    # example passing only required values which don't have defaults set
    try:
        # GetSeriesByTicker
        api_response = api_instance.get_series_by_ticker(series_ticker)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling SeriesApi->get_series_by_ticker: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **series_ticker** | **str**| Should be the ticker of the series |

### Return type

[**GetSeriesByTickerResponse**](GetSeriesByTickerResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GetSeriesByTickerResponse |  -  |
**400** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**401** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**403** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**404** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |
**500** | JSONError is a generic structure for API error responses. |  * code -  <br>  * details -  <br>  * message -  <br>  * service -  <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

