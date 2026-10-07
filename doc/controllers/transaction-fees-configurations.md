# Transaction Fees Configurations

```csharp
TransactionFeesConfigurationsApi transactionFeesConfigurationsApi = client.TransactionFeesConfigurationsApi;
```

## Class Name

`TransactionFeesConfigurationsApi`

## Methods

* [Create Transaction Fee Account Group Configuration](../../doc/controllers/transaction-fees-configurations.md#create-transaction-fee-account-group-configuration)
* [Update Transaction Fee Account Group Configuration](../../doc/controllers/transaction-fees-configurations.md#update-transaction-fee-account-group-configuration)


# Create Transaction Fee Account Group Configuration

Assigns a transaction fee model to an account group for a transaction category.

```csharp
CreateTransactionFeeAccountGroupConfigurationAsync(
    Guid upvestClientId,
    string authorization,
    string signature,
    string signatureInput,
    Models.UpvestApiVersion? upvestApiVersion = Models.UpvestApiVersion.Enum1,
    Models.TransactionFeeAccountGroupConfigurationCreateRequest body = null)
```

## Authentication

This endpoint requires [oauth-client-credentials](../../doc/auth/oauth-2-client-credentials-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `upvestClientId` | `Guid` | Header, Required | Your client ID, issued by Upvest. Identifies the client making the request. Universally Unique Identifier (UUID). |
| `authorization` | `string` | Header, Required | Bearer (access) token from the OAuth flow with correct scopes.<br>https://datatracker.ietf.org/doc/html/rfc6750<br><br>**Constraints**: *Pattern*: `^Bearer [a-zA-Z0-9\-\._~+/]*=*` |
| `signature` | `string` | Header, Required | https://tools.ietf.org/id/draft-ietf-httpbis-message-signatures-01.html#name-the-signature-http-header |
| `signatureInput` | `string` | Header, Required | https://tools.ietf.org/id/draft-ietf-httpbis-message-signatures-01.html#name-the-signature-input-http-he |
| `upvestApiVersion` | [`UpvestApiVersion?`](../../doc/models/upvest-api-version.md) | Header, Optional | Upvest API version (Note: Do not include quotation marks)<br><br>**Default**: `UpvestApiVersion.Enum_1` |
| `body` | [`TransactionFeeAccountGroupConfigurationCreateRequest`](../../doc/models/transaction-fee-account-group-configuration-create-request.md) | Body, Optional | - |

## Requires scope

### oauth-client-credentials

`transaction_fees:admin`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.TransactionFeeAccountGroupConfiguration](../../doc/models/transaction-fee-account-group-configuration.md).

## Example Usage

```csharp
Guid upvestClientId = new Guid("363f3305-7ab0-4e82-a158-f9d382ad08b6");
string authorization = "Bearer c2VjcmV0Cg==";
string signature = "signature8";
string signatureInput = "signature-input2";
UpvestApiVersion? upvestApiVersion = UpvestApiVersion.Enum1;
TransactionFeeAccountGroupConfigurationCreateRequest body = new TransactionFeeAccountGroupConfigurationCreateRequest
{
    FeeModelId = new Guid("eb5ba93f-5dfe-4bf1-8571-4da0caacc80c"),
    AccountGroupId = new Guid("7524949b-31fd-497e-ad92-f52de45341d1"),
    TransactionCategory = TransactionCategory.PensionDeContribution,
};

try
{
    ApiResponse<TransactionFeeAccountGroupConfiguration> result = await transactionFeesConfigurationsApi.CreateTransactionFeeAccountGroupConfigurationAsync(
        upvestClientId,
        authorization,
        signature,
        signatureInput,
        upvestApiVersion,
        body
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ErrorException)
    {
       // TODO: Handle ErrorException exception here
    }
}
```

## Example Response *(as JSON)*

```json
{
  "id": "3c9a1f2e-6b4d-4a1a-9c3e-8f2b1d4e6a7c",
  "created_at": "2021-07-21T14:10:00.00Z",
  "updated_at": "2021-07-21T14:10:00.00Z",
  "fee_model_id": "eb5ba93f-5dfe-4bf1-8571-4da0caacc80c",
  "account_group_id": "7524949b-31fd-497e-ad92-f52de45341d1",
  "transaction_category": "PENSION_DE_CONTRIBUTION"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request. The incoming request had a malformed parameter/object. | [`ErrorException`](../../doc/models/error-exception.md) |
| 401 | Unauthorized. The caller has not been authenticated. | [`ErrorException`](../../doc/models/error-exception.md) |
| 403 | Forbidden. The caller has been authenticated but is not allowed to take the requested action. | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found. The requested resource could not be found. | [`ErrorException`](../../doc/models/error-exception.md) |
| 406 | Not Acceptable. The resource does not have a current representation that would be acceptable to the user agent. "Accept" header defined unsupported value. | [`ErrorException`](../../doc/models/error-exception.md) |
| 409 | Conflict. An operation is not available for the current state of the resource. | [`ErrorException`](../../doc/models/error-exception.md) |
| 429 | Too Many Requests. The caller has exceeded their quota for the time period and has been throttled. | [`ErrorException`](../../doc/models/error-exception.md) |
| 500 | Internal Server Error. The service encountered an unexpected error. | [`ErrorException`](../../doc/models/error-exception.md) |
| 503 | Service Unavailable. The service handling for this request cannot be reached at this time. | [`ErrorException`](../../doc/models/error-exception.md) |
| 504 | Gateway Timeout. The service gateway has reached its internal timeout. | [`ErrorException`](../../doc/models/error-exception.md) |


# Update Transaction Fee Account Group Configuration

Update the fee model assigned by an existing transaction fee account group configuration.

```csharp
UpdateTransactionFeeAccountGroupConfigurationAsync(
    Guid transactionFeeAccountGroupConfigurationId,
    Guid upvestClientId,
    string authorization,
    string signature,
    string signatureInput,
    Models.UpvestApiVersion? upvestApiVersion = Models.UpvestApiVersion.Enum1,
    Models.TransactionFeeAccountGroupConfigurationUpdateRequest body = null)
```

## Authentication

This endpoint requires [oauth-client-credentials](../../doc/auth/oauth-2-client-credentials-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionFeeAccountGroupConfigurationId` | `Guid` | Template, Required | The unique identifier of the transaction fee account group configuration. Universally Unique Identifier (UUID). |
| `upvestClientId` | `Guid` | Header, Required | Your client ID, issued by Upvest. Identifies the client making the request. Universally Unique Identifier (UUID). |
| `authorization` | `string` | Header, Required | Bearer (access) token from the OAuth flow with correct scopes.<br>https://datatracker.ietf.org/doc/html/rfc6750<br><br>**Constraints**: *Pattern*: `^Bearer [a-zA-Z0-9\-\._~+/]*=*` |
| `signature` | `string` | Header, Required | https://tools.ietf.org/id/draft-ietf-httpbis-message-signatures-01.html#name-the-signature-http-header |
| `signatureInput` | `string` | Header, Required | https://tools.ietf.org/id/draft-ietf-httpbis-message-signatures-01.html#name-the-signature-input-http-he |
| `upvestApiVersion` | [`UpvestApiVersion?`](../../doc/models/upvest-api-version.md) | Header, Optional | Upvest API version (Note: Do not include quotation marks)<br><br>**Default**: `UpvestApiVersion.Enum_1` |
| `body` | [`TransactionFeeAccountGroupConfigurationUpdateRequest`](../../doc/models/transaction-fee-account-group-configuration-update-request.md) | Body, Optional | - |

## Requires scope

### oauth-client-credentials

`transaction_fees:admin`

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `Data` property of this instance returns the response data which is of type [Models.TransactionFeeAccountGroupConfiguration](../../doc/models/transaction-fee-account-group-configuration.md).

## Example Usage

```csharp
Guid transactionFeeAccountGroupConfigurationId = new Guid("00001c54-0000-0000-0000-000000000000");
Guid upvestClientId = new Guid("363f3305-7ab0-4e82-a158-f9d382ad08b6");
string authorization = "Bearer c2VjcmV0Cg==";
string signature = "signature8";
string signatureInput = "signature-input2";
UpvestApiVersion? upvestApiVersion = UpvestApiVersion.Enum1;
TransactionFeeAccountGroupConfigurationUpdateRequest body = new TransactionFeeAccountGroupConfigurationUpdateRequest
{
    FeeModelId = new Guid("eb5ba93f-5dfe-4bf1-8571-4da0caacc80c"),
};

try
{
    ApiResponse<TransactionFeeAccountGroupConfiguration> result = await transactionFeesConfigurationsApi.UpdateTransactionFeeAccountGroupConfigurationAsync(
        transactionFeeAccountGroupConfigurationId,
        upvestClientId,
        authorization,
        signature,
        signatureInput,
        upvestApiVersion,
        body
    );
}
catch (ApiException e)
{
    Console.WriteLine(e.Message);
    if (e is ErrorException)
    {
       // TODO: Handle ErrorException exception here
    }
}
```

## Example Response *(as JSON)*

```json
{
  "id": "3c9a1f2e-6b4d-4a1a-9c3e-8f2b1d4e6a7c",
  "created_at": "2021-07-21T14:10:00.00Z",
  "updated_at": "2021-07-21T15:20:00.00Z",
  "fee_model_id": "eb5ba93f-5dfe-4bf1-8571-4da0caacc80c",
  "account_group_id": "7524949b-31fd-497e-ad92-f52de45341d1",
  "transaction_category": "PENSION_DE_CONTRIBUTION"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request. The incoming request had a malformed parameter/object. | [`ErrorException`](../../doc/models/error-exception.md) |
| 401 | Unauthorized. The caller has not been authenticated. | [`ErrorException`](../../doc/models/error-exception.md) |
| 403 | Forbidden. The caller has been authenticated but is not allowed to take the requested action. | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found. The requested resource could not be found. | [`ErrorException`](../../doc/models/error-exception.md) |
| 406 | Not Acceptable. The resource does not have a current representation that would be acceptable to the user agent. "Accept" header defined unsupported value. | [`ErrorException`](../../doc/models/error-exception.md) |
| 409 | Conflict. An operation is not available for the current state of the resource. | [`ErrorException`](../../doc/models/error-exception.md) |
| 429 | Too Many Requests. The caller has exceeded their quota for the time period and has been throttled. | [`ErrorException`](../../doc/models/error-exception.md) |
| 500 | Internal Server Error. The service encountered an unexpected error. | [`ErrorException`](../../doc/models/error-exception.md) |
| 503 | Service Unavailable. The service handling for this request cannot be reached at this time. | [`ErrorException`](../../doc/models/error-exception.md) |
| 504 | Gateway Timeout. The service gateway has reached its internal timeout. | [`ErrorException`](../../doc/models/error-exception.md) |

