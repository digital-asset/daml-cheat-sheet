Updates specify the transactions that will be committed to the ledger. Updates are described within
a `do` block:

```
do
  cid <- create NewContract with field1 = 1
                                 , field2 = "hello world"
  let answer = 42
  exercise cid SomeChoice with choiceArgument = "123"
  return answer
```


| -------------------- | ----------------------------------------------------- |
| `create` | create an instance of the given template on the ledger <br> `create NameOfTemplate with exampleParameters` |
| `exercise` | exercise a choice on a given contract by contract id <br> `exercise IfOfContract NameOfChoiceContract with choiceArgument1 = value1 `|
| `exerciseByKey` | exercise a choice on a given contract by contract key <br> `exerciseByKey @ContractType contractKey NameOfChoiceOnContract with choiceArgument1 = value1 ` |
| `fetch` | fetch the contract data from the ledger given by contract id <br> `fetchedContract <- fetch IdOfContract `|
| `fetchByKey` | fetch the contract data from the ledger given by contract key <br> `fetchedContract <- fetchByKey @ContractType contractKey` |
| `lookupByKey` | check whether a contract with the given key exists and if yes, return the contract id <br> `fetchedContractId <- lookupByKey @ContractType contractKey` |
| `abort` | abort a transaction with an error message, the transaction will not be committed to the ledger <br> `abort errorMessage` |
| `assert` | assert that a given predicate holds, otherwise fail the transaction <br> `assert (condition == True)` |
| `getTime` | get the ledger effective time <br> `currentTime <- getTime `|
| `return` | return a value from a `do` block <br> `return 42`|
| `let` | bind a local variable or define a local function within the update `do` block <br> `let createContract x = create NameOfContract with issuer = x; owner = x` <br> `let answer = 42 `|
| `this` | refers to the current contract data that contains this update in a choice <br> `create NewContract with owner = this.owner` | 
