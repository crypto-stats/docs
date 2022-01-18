# Log

The standard `console.log` is unavailable inside CryptoStats adapters. Instead, use the Log library to log messages.

## `sdk.log(...args: any[])`

Logs a message at the "info" severity, so identical to `sdk.log.info`.

## `sdk.log.debug((...args: any[])`, `sdk.log.info((...args: any[])`, `sdk.log.warn((...args: any[])`, `sdk.log.error((...args: any[])`

Log messages at varying levels of severity.
