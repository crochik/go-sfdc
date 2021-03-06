___
*THIS IS A FORK only for testing. You should use one of the upstream repos instead.*
___
# go-sfdc

[![Godoc Reference][godoc-img]][godoc-url] [![CI][ci-img]][ci-url] [![codecov][codecov-img]][codecov-url]

This is a `golang` library for interfacing with `Salesforce` APIs.

## Getting Started
### Installing
To start using go-sfdc, install GO and run `go get`
```
go get github.com/crochik/go-sfdc
```
This will retrieve the library.

## Usage
To use this library, the following will need to be done.
* Create `Salesforce` [credentials](./credentials/README.md) to properly authenticate with the `Salesforce org`
* Configure
* Open a [session](./session/README.md)
* Use the `APIs`
  - [SObject APIs](./sobject/README.md)
  - [SObject Collection APIs](./sobject/collections/README.md)
  - [SObject Tree API](./sobject/tree/README.md)
  - [SOQL APIs](./soql/README.md)
  - [Composite](./composite/README.md)
  - [Composite Batch](./composite/batch/README.md)
  - [Bulk 2.0](./bulk/README.md)

## Configuration
The configuration defines several parameters that can be used by the library.  The configuration is used per [session](./session/README.md).
* `Credentials` - this is an implementation of the `credentials.Provider` interface
* `Client` - the HTTP client used by the `APIs`
* `Version` - is the `Salesforce` version.  Please refer to [`Salesforce` documentation](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/intro_what_is_rest_api.htm) to make sure that `APIs` are supported in the version that is specified.
### Example
```go
package main

import (
	"github.com/crochik/go-sfdc"
	"github.com/crochik/go-sfdc/credentials"
)

var config = sfdc.Configuration{
	Credentials: credentials.NewPasswordCredentials(creds),
	Client:      salesforceHTTPClient,
	Version:     44,
}
```

## License
GO-SFDC source code is available under the [MIT License](LICENSE.txt)

[godoc-img]: https://godoc.org/github.com/crochik/go-sfdc?status.svg
[godoc-url]: https://godoc.org/github.com/crochik/go-sfdc

[ci-img]: https://github.com/crochik/go-sfdc/workflows/CI/badge.svg
[ci-url]: https://github.com/crochik/go-sfdc/actions?query=workflow%3A%22CI%22

[codecov-img]: https://codecov.io/gh/crochik/go-sfdc/branch/master/graph/badge.svg
[codecov-url]: https://codecov.io/gh/crochik/go-sfdc
