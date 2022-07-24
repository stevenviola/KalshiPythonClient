# kalshi
This documentation describes Kalshi's REST API

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >=3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import kalshi
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import kalshi
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import kalshi
from pprint import pprint
from kalshi.api import account_api
from kalshi.model.change_subscription_request import ChangeSubscriptionRequest
from kalshi.model.change_subscription_response import ChangeSubscriptionResponse
from kalshi.model.get_notification_preferences_response import GetNotificationPreferencesResponse
from kalshi.model.user_get_account_history_response import UserGetAccountHistoryResponse
from kalshi.model.user_get_notifications_response import UserGetNotificationsResponse
from kalshi.model.user_get_profits_and_losses_response import UserGetProfitsAndLossesResponse
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
    api_instance = account_api.AccountApi(api_client)
    user_id = "user_id_example" # str | Should be filled with your user_id provided on log_in
    change_subscription_request = ChangeSubscriptionRequest(
        push_preferences=True,
        subscription_level="subscription_level_example",
    ) # ChangeSubscriptionRequest | Change subscription data (optional)

    try:
        # ChangeSubscription
        api_response = api_instance.change_subscription(user_id, change_subscription_request=change_subscription_request)
        pprint(api_response)
    except kalshi.ApiException as e:
        print("Exception when calling AccountApi->change_subscription: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://trading-api.kalshi.com/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountApi* | [**change_subscription**](docs/AccountApi.md#change_subscription) | **PATCH** /users/{user_id}/subscribe | ChangeSubscription
*AccountApi* | [**get_notification_preferences**](docs/AccountApi.md#get_notification_preferences) | **GET** /users/{user_id}/notifications/preferences | GetNotificationPreferences
*AccountApi* | [**notification_mark_read**](docs/AccountApi.md#notification_mark_read) | **PUT** /users/{user_id}/notifications/{notification_id}/read | NotificationMarkRead
*AccountApi* | [**user_get_account_history**](docs/AccountApi.md#user_get_account_history) | **GET** /users/{user_id}/account/history | UserGetAccountHistory
*AccountApi* | [**user_get_notifications**](docs/AccountApi.md#user_get_notifications) | **GET** /users/{user_id}/notifications | UserGetNotifications
*AccountApi* | [**user_get_profits_and_losses**](docs/AccountApi.md#user_get_profits_and_losses) | **GET** /users/{user_id}/account/pnl | UserGetProfitsAndLosses
*AuthApi* | [**login**](docs/AuthApi.md#login) | **POST** /log_in | Login
*AuthApi* | [**logout**](docs/AuthApi.md#logout) | **POST** /log_out | Logout
*AuthApi* | [**reset_password**](docs/AuthApi.md#reset_password) | **POST** /passwords/reset | ResetPassword
*AuthApi* | [**reset_password_confirm**](docs/AuthApi.md#reset_password_confirm) | **PUT** /passwords/reset/{code}/confirm | ResetPasswordConfirm
*DefaultApi* | [**get_events_cached**](docs/DefaultApi.md#get_events_cached) | **GET** /events/ | GetEventsCached
*DefaultApi* | [**get_series_list**](docs/DefaultApi.md#get_series_list) | **GET** /series/ | GetSeriesList
*DefaultApi* | [**get_series_list_cached**](docs/DefaultApi.md#get_series_list_cached) | **GET** /cached/series | GetSeriesListCached
*DefaultApi* | [**get_trades**](docs/DefaultApi.md#get_trades) | **GET** /trades | GetTrades
*EventsApi* | [**get_event_by_ticker_cached**](docs/EventsApi.md#get_event_by_ticker_cached) | **GET** /events/{ticker} | GetEventByTickerCached
*ExchangeApi* | [**get_exchange_status**](docs/ExchangeApi.md#get_exchange_status) | **GET** /exchange/status | 
*ExchangeApi* | [**get_exchange_status_cached**](docs/ExchangeApi.md#get_exchange_status_cached) | **GET** /cached/exchange/status | End-point for getting the exchange status.
*MarketApi* | [**get_active_markets**](docs/MarketApi.md#get_active_markets) | **GET** /active_markets | GetActiveMarkets
*MarketApi* | [**get_candlestick_market_history**](docs/MarketApi.md#get_candlestick_market_history) | **GET** /markets/{market_id}/candlestick | GetCandlestickMarketHistory
*MarketApi* | [**get_candlestick_market_history_cached**](docs/MarketApi.md#get_candlestick_market_history_cached) | **GET** /cached/markets/{market_id}/candlestick | GetCandlestickMarketHistoryCached
*MarketApi* | [**get_market**](docs/MarketApi.md#get_market) | **GET** /markets/{market_id} | GetMarket
*MarketApi* | [**get_market_by_ticker**](docs/MarketApi.md#get_market_by_ticker) | **GET** /markets_by_ticker/{ticker_name} | GetMarketByTicker
*MarketApi* | [**get_market_by_ticker_cached**](docs/MarketApi.md#get_market_by_ticker_cached) | **GET** /cached/markets_by_ticker/{ticker_name} | GetMarketByTickerCached
*MarketApi* | [**get_market_cached**](docs/MarketApi.md#get_market_cached) | **GET** /cached/markets/{market_id} | GetMarketCached
*MarketApi* | [**get_market_history**](docs/MarketApi.md#get_market_history) | **GET** /markets/{market_id}/stats_history | GetMarketHistory
*MarketApi* | [**get_market_history_cached**](docs/MarketApi.md#get_market_history_cached) | **GET** /cached/markets/{market_id}/stats_history | GetMarketHistoryCached
*MarketApi* | [**get_market_order_book**](docs/MarketApi.md#get_market_order_book) | **GET** /markets/{market_id}/order_book | GetMarketOrderBook
*MarketApi* | [**get_market_order_book_cached**](docs/MarketApi.md#get_market_order_book_cached) | **GET** /cached/markets/{market_id}/order_book | GetMarketOrderBookCached
*MarketApi* | [**get_markets**](docs/MarketApi.md#get_markets) | **GET** /markets | GetMarkets
*MarketApi* | [**get_markets_cached**](docs/MarketApi.md#get_markets_cached) | **GET** /cached/markets | GetMarketsCached
*PortfolioApi* | [**deprecated_user_get_portfolio_history**](docs/PortfolioApi.md#deprecated_user_get_portfolio_history) | **GET** /users/{user_id}/portfolio/ | DeprecatedUserGetPortfolioHistory
*PortfolioApi* | [**user_get_sampled_portfolio_history**](docs/PortfolioApi.md#user_get_sampled_portfolio_history) | **GET** /users/{user_id}/sampled_portfolio/ | UserGetSampledPortfolioHistory
*RangedMarketApi* | [**get_ranged_market**](docs/RangedMarketApi.md#get_ranged_market) | **GET** /ranged_markets/{ranged_market_id} | GetRangedMarket
*RangedMarketsApi* | [**get_ranged_market_by_ticker**](docs/RangedMarketsApi.md#get_ranged_market_by_ticker) | **GET** /ranged_markets_by_ticker/{ticker} | GetRangedMarketByTicker
*RangedMarketsApi* | [**user_get_ranged_market_position**](docs/RangedMarketsApi.md#user_get_ranged_market_position) | **GET** /users/{user_id}/ranged_positions/{ranged_market_id} | UserGetRangedMarketPosition
*SeriesApi* | [**get_series_by_ticker**](docs/SeriesApi.md#get_series_by_ticker) | **GET** /series/{series_ticker} | GetSeriesByTicker
*UserApi* | [**user_add_favorited_series**](docs/UserApi.md#user_add_favorited_series) | **PUT** /users/{user_id}/favorited_series/{series_ticker} | UserAddFavoritedSeries
*UserApi* | [**user_add_watchlist**](docs/UserApi.md#user_add_watchlist) | **PUT** /users/{user_id}/watchlist/{market_id} | UserAddWatchlist
*UserApi* | [**user_batch_orders_cancel**](docs/UserApi.md#user_batch_orders_cancel) | **DELETE** /users/{user_id}/batch_orders | UserBatchOrdersCancel
*UserApi* | [**user_batch_orders_create**](docs/UserApi.md#user_batch_orders_create) | **POST** /users/{user_id}/batch_orders | UserBatchOrdersCreate
*UserApi* | [**user_change_password**](docs/UserApi.md#user_change_password) | **PUT** /users/{user_id}/password | UserChangePassword
*UserApi* | [**user_deactivate**](docs/UserApi.md#user_deactivate) | **DELETE** /users | UserDeactivate
*UserApi* | [**user_get_balance**](docs/UserApi.md#user_get_balance) | **GET** /users/{user_id}/balance | UserGetBalance
*UserApi* | [**user_get_favorited_series**](docs/UserApi.md#user_get_favorited_series) | **GET** /users/{user_id}/favorited_series | UserGetFavoritedSeries
*UserApi* | [**user_get_market_position**](docs/UserApi.md#user_get_market_position) | **GET** /users/{user_id}/positions/{market_id} | UserGetMarketPosition
*UserApi* | [**user_get_market_positions**](docs/UserApi.md#user_get_market_positions) | **GET** /users/{user_id}/positions | UserGetMarketPositions
*UserApi* | [**user_get_profile**](docs/UserApi.md#user_get_profile) | **GET** /users/{user_id} | UserGetProfile
*UserApi* | [**user_get_referral_info**](docs/UserApi.md#user_get_referral_info) | **GET** /users/{user_id}/referrals | UserGetReferralInfo
*UserApi* | [**user_get_watchlist**](docs/UserApi.md#user_get_watchlist) | **GET** /users/{user_id}/watchlist | UserGetWatchlist
*UserApi* | [**user_order_cancel**](docs/UserApi.md#user_order_cancel) | **DELETE** /users/{user_id}/orders/{order_id} | UserOrderCancel
*UserApi* | [**user_order_create**](docs/UserApi.md#user_order_create) | **POST** /users/{user_id}/orders | UserOrderCreate
*UserApi* | [**user_order_decrease**](docs/UserApi.md#user_order_decrease) | **POST** /users/{user_id}/orders/{order_id}/decrease | UserOrderDecrease
*UserApi* | [**user_orders_get**](docs/UserApi.md#user_orders_get) | **GET** /users/{user_id}/orders | UserOrdersGet
*UserApi* | [**user_remove_favorited_series**](docs/UserApi.md#user_remove_favorited_series) | **DELETE** /users/{user_id}/favorited_series/{series_ticker} | UserRemoveFavoritedSeries
*UserApi* | [**user_remove_watchlist**](docs/UserApi.md#user_remove_watchlist) | **DELETE** /users/{user_id}/watchlist/{market_id} | UserRemoveWatchlist
*UserApi* | [**user_trades_get**](docs/UserApi.md#user_trades_get) | **GET** /users/{user_id}/trades | UserTradesGet
*UsersApi* | [**get_user_immediate_funding**](docs/UsersApi.md#get_user_immediate_funding) | **GET** /users/{user_id}/immediate_funding | GetUserImmediateFunding
*UsersApi* | [**get_user_withdrawal_available_balance**](docs/UsersApi.md#get_user_withdrawal_available_balance) | **GET** /users/{user_id}/withdrawals/available | GetUserWithdrawalAvailableBalance


## Documentation For Models

 - [AccountHistoryEntry](docs/AccountHistoryEntry.md)
 - [AccountHistoryEntryData](docs/AccountHistoryEntryData.md)
 - [BankAccountDetails](docs/BankAccountDetails.md)
 - [ChangeSubscriptionRequest](docs/ChangeSubscriptionRequest.md)
 - [ChangeSubscriptionResponse](docs/ChangeSubscriptionResponse.md)
 - [ConfirmPasswordResetRequest](docs/ConfirmPasswordResetRequest.md)
 - [CreateUserRequest](docs/CreateUserRequest.md)
 - [CreateUserResponse](docs/CreateUserResponse.md)
 - [CreditHistory](docs/CreditHistory.md)
 - [Deposit](docs/Deposit.md)
 - [DepositHistory](docs/DepositHistory.md)
 - [DeprecatedPortfolioMeasurement](docs/DeprecatedPortfolioMeasurement.md)
 - [DeprecatedUserGetPortfolioHistoryRequest](docs/DeprecatedUserGetPortfolioHistoryRequest.md)
 - [DeprecatedUserGetPortfolioHistoryResponse](docs/DeprecatedUserGetPortfolioHistoryResponse.md)
 - [EventChildMarket](docs/EventChildMarket.md)
 - [EventData](docs/EventData.md)
 - [FavoritedSeries](docs/FavoritedSeries.md)
 - [GetActiveMarketsResponse](docs/GetActiveMarketsResponse.md)
 - [GetCandlestickMarketHistoryResponse](docs/GetCandlestickMarketHistoryResponse.md)
 - [GetEventByTickerResponse](docs/GetEventByTickerResponse.md)
 - [GetEventsResponse](docs/GetEventsResponse.md)
 - [GetMarketHistoryResponse](docs/GetMarketHistoryResponse.md)
 - [GetMarketOrderBookResponse](docs/GetMarketOrderBookResponse.md)
 - [GetNotificationPreferencesResponse](docs/GetNotificationPreferencesResponse.md)
 - [GetRangedMarketByTickerResponse](docs/GetRangedMarketByTickerResponse.md)
 - [GetRangedMarketResponse](docs/GetRangedMarketResponse.md)
 - [GetRangedMarketsResponse](docs/GetRangedMarketsResponse.md)
 - [GetSeriesByTickerResponse](docs/GetSeriesByTickerResponse.md)
 - [GetSeriesListResponse](docs/GetSeriesListResponse.md)
 - [GetUserDepositsResponse](docs/GetUserDepositsResponse.md)
 - [GetUserImmediateFundingResponse](docs/GetUserImmediateFundingResponse.md)
 - [GetUserWithdrawalsResponse](docs/GetUserWithdrawalsResponse.md)
 - [JSONError](docs/JSONError.md)
 - [LoginRequest](docs/LoginRequest.md)
 - [LoginResponse](docs/LoginResponse.md)
 - [Market](docs/Market.md)
 - [MarketActivity](docs/MarketActivity.md)
 - [MarketHistoryCandleStickInfo](docs/MarketHistoryCandleStickInfo.md)
 - [MarketPosition](docs/MarketPosition.md)
 - [MarketStatsPoint](docs/MarketStatsPoint.md)
 - [MarketTransaction](docs/MarketTransaction.md)
 - [Notification](docs/Notification.md)
 - [NotificationList](docs/NotificationList.md)
 - [OLHCM](docs/OLHCM.md)
 - [Order](docs/Order.md)
 - [OrderBook](docs/OrderBook.md)
 - [OrderHistory](docs/OrderHistory.md)
 - [OrderList](docs/OrderList.md)
 - [PeopleReferred](docs/PeopleReferred.md)
 - [PeopleReferredList](docs/PeopleReferredList.md)
 - [PortfolioMeasurement](docs/PortfolioMeasurement.md)
 - [PriceLevel](docs/PriceLevel.md)
 - [PublicTrade](docs/PublicTrade.md)
 - [PublicTradeList](docs/PublicTradeList.md)
 - [RangedMarket](docs/RangedMarket.md)
 - [RangedMarketPosition](docs/RangedMarketPosition.md)
 - [ResetPasswordRequest](docs/ResetPasswordRequest.md)
 - [Series](docs/Series.md)
 - [SettlementHistory](docs/SettlementHistory.md)
 - [SettlementSource](docs/SettlementSource.md)
 - [SubscriptionPreference](docs/SubscriptionPreference.md)
 - [TradeHistory](docs/TradeHistory.md)
 - [TradesGetResponse](docs/TradesGetResponse.md)
 - [User](docs/User.md)
 - [UserBatchOrdersCancelRequest](docs/UserBatchOrdersCancelRequest.md)
 - [UserBatchOrdersCancelResponse](docs/UserBatchOrdersCancelResponse.md)
 - [UserBatchOrdersCancelSingleOrderResponse](docs/UserBatchOrdersCancelSingleOrderResponse.md)
 - [UserBatchOrdersCreateRequest](docs/UserBatchOrdersCreateRequest.md)
 - [UserBatchOrdersCreateResponse](docs/UserBatchOrdersCreateResponse.md)
 - [UserBatchOrdersCreateSingleOrderResponse](docs/UserBatchOrdersCreateSingleOrderResponse.md)
 - [UserChangePasswordRequest](docs/UserChangePasswordRequest.md)
 - [UserDepositRequest](docs/UserDepositRequest.md)
 - [UserDepositResponse](docs/UserDepositResponse.md)
 - [UserGetAccountHistoryResponse](docs/UserGetAccountHistoryResponse.md)
 - [UserGetBalanceResponse](docs/UserGetBalanceResponse.md)
 - [UserGetCurrentPortfolioValueResponse](docs/UserGetCurrentPortfolioValueResponse.md)
 - [UserGetFavoritedSeriesResponse](docs/UserGetFavoritedSeriesResponse.md)
 - [UserGetMarketPositionResponse](docs/UserGetMarketPositionResponse.md)
 - [UserGetMarketPositionsResponse](docs/UserGetMarketPositionsResponse.md)
 - [UserGetMarketResponse](docs/UserGetMarketResponse.md)
 - [UserGetMarketsResponse](docs/UserGetMarketsResponse.md)
 - [UserGetNotificationsResponse](docs/UserGetNotificationsResponse.md)
 - [UserGetProfileResponse](docs/UserGetProfileResponse.md)
 - [UserGetProfitsAndLossesResponse](docs/UserGetProfitsAndLossesResponse.md)
 - [UserGetRangedMarketPositionResponse](docs/UserGetRangedMarketPositionResponse.md)
 - [UserGetReferralInfoResponse](docs/UserGetReferralInfoResponse.md)
 - [UserGetSampledPortfolioHistoryResponse](docs/UserGetSampledPortfolioHistoryResponse.md)
 - [UserGetWatchlistResponse](docs/UserGetWatchlistResponse.md)
 - [UserListLedgerxBankAccountsResponse](docs/UserListLedgerxBankAccountsResponse.md)
 - [UserOrderCreateRequest](docs/UserOrderCreateRequest.md)
 - [UserOrderCreateResponse](docs/UserOrderCreateResponse.md)
 - [UserOrderDecreaseRequest](docs/UserOrderDecreaseRequest.md)
 - [UserOrderDecreaseResponse](docs/UserOrderDecreaseResponse.md)
 - [UserOrdersGetResponse](docs/UserOrdersGetResponse.md)
 - [UserTrade](docs/UserTrade.md)
 - [UserTradeList](docs/UserTradeList.md)
 - [UserTradesGetResponse](docs/UserTradesGetResponse.md)
 - [UserUpdateProfileRequest](docs/UserUpdateProfileRequest.md)
 - [UserWithdrawalAvailableBalanceResponse](docs/UserWithdrawalAvailableBalanceResponse.md)
 - [UserWithdrawalRequest](docs/UserWithdrawalRequest.md)
 - [UserWithdrawalResponse](docs/UserWithdrawalResponse.md)
 - [Watchlist](docs/Watchlist.md)
 - [Withdrawal](docs/Withdrawal.md)
 - [WithdrawalHistory](docs/WithdrawalHistory.md)


## Documentation For Authorization


## cookie

- **Type**: API key
- **API key parameter name**: Authorization
- **Location**: HTTP header


## Author




## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in kalshi.apis and kalshi.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from kalshi.api.default_api import DefaultApi`
- `from kalshi.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import kalshi
from kalshi.apis import *
from kalshi.models import *
```

