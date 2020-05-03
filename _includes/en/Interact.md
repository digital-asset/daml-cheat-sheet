DAML ledgers expose a unified API for interaction.

The following describes how to interact with a ledger using the <a
href="https://www.typescriptlang.org"> TypeScript </a> libraries `@daml/ledger`, `@daml/react` in a
frontend build with <a href="https://reactjs.org"> React </a>.

Import the libraries via:

```
import Ledger from @daml/ledger
import {useParty, ...} from @daml/react
```

React entry point:

```typescript
import DamlLeddger from @daml/react

const App: React.FC = () => {
     <DamlLedger
      token: <your authentication token>
      httpBaseUrl?: <optional http base url>
      wsBaseUrl?: <optional websocket base url>
      party: <the logged in party>
    >
      <MainScreen />
    </DamlLedger>
};
```

| -------------------- | ----------------------------------------------------- |
| Get the logged in party | `const party = useParty();` <br> `...` <br> `<h1> You're logged in as {party} </h1>`|
| Query the ledger | `const {contracts: queryResult, loading: isLoading, } = useQuery(ContractTemplate, () => ({field: value}), [dep1, dep2, ...]) ` |
| Query for contract keys | `const {contracts, loading} = useFetchByKey(ContractTemplate, () => key, [dep1, dep2, ...])` |
| Reload the query results | `reload = useReload();` <br> `...` <br> `onClick={() => reload()}`|
| Query the ledger, returns a refreshing stream | `const {contracts, loading}` = useStreamQuery(ContractTemplate, () => ({field: value}), [dep1, dep2, ...]) ` |
| Query for contract keys, returns a refreshing stream |  `const {contracts, loading} = useStreamFetchByKey(ContractTemplate, () => key, [dep1, dep2, ...])` |
| Create a contract on the ledger | `const ledger = useLedger();` <br> `const newContract = await ledger.create(ContractTemplate, arguments)`|
| Archive a contract on the ledger | `const ledger = useLedger();` <br> `const archiveEvent = await ledger.archive(ContractTemplate, contractId)`|
| Exercise a contract choice on the ledger | `const ledger = useLedger();` <br> `const [choiceReturnValue, events] = await ledger.exercise(ContractChoice, contractId, choiceArguments)`|
