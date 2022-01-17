# Standard queries

While adapters may define any queries that they would like, it is important that adapter collections use the same
query names.

It is best practice to chose existing, standard queries when possible:

## Fees & revenue

|Query                |Description                                                                  |Parameters          |
|---------------------|-----------------------------------------------------------------------------|--------------------|
|oneDayTotalFees      |Query the USD value of all fees paid to a protocol on a given calendar date. |Date                |
|oneDayProtocolFees   |Query the USD value of fees collected by a protocol on a given calendar date.|Date                |
|dateRangeTotalFees   |Query the USD value of all fees paid between two dates                       |Start date, end date|
|dateRangeProtocolFees|Query the USD value of fees fees collected by a protocol between two dates   |Start date, end date|

## Issuance

|Query                |Description                                                                  |Parameters|
|---------------------|-----------------------------------------------------------------------------|----------|
|issuance7DayAvgUSD   |USD value of assets issued per day (averaged over the previous 7 days)       |          |
|issuanceRateCurrent  |The annualized issuance rate percentage (in decimal form)                    |          |


## Transaction fees

|Query                |Description                                                                  |Parameters|
|---------------------|-----------------------------------------------------------------------------|----------|
|feeTransferEth       |Standard fee to transfer ETH                                                 |          |
|feeTransferERC20     |Standard fee to transfer an arbitrary token                                  |          |
|feeSwap              |Standard fee to swap 2 assets                                                |          |
