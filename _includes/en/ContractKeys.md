Contract keys are unique and stable references to a contract that won't change even if the contract
id of that contract changes due to an update.

Contract keys are optional.

Contract keys have an associated set of key maintainer parties. These parties guarantee the uniquess
of their maintained keys.

Contract keys are specified on a contract template with the `key` and `maintainer` keywords. If you
specify a `key` you also have to specify its `maintainers`.

| -------------------- | ----------------------------------------------------- |
| `key` | Can be any expression of the contract arguments that does _not_ contain a contract id. It _must_ include all maintainer parties specified in the `maintainer` field. |
|`maintainer` | Keys are unique for all specified maintainers. The maintainers need to be a projection of the expression specified with `key`.|
