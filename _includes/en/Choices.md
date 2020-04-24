The choices of a contract template specify the rules on how and by whom contract data can be
changed.

```
(nonconsuming) choice NameOfChoice : () 
-- optional nonconsuming annotation, name and return type of the choice
  with
    party1 : Party          -- choice arguments
    party2 : Party
    i : Int
  controller party1, party2 -- parties that can execute this choice
    do                      -- the update that will 
                            -- be executed 
      assert (i == 42)
      create ...
      exercise ...
      return ()
```

Choices can be `consuming` or `nonconsuming`.

| -------------------- | ----------------------------------------------------- |
|`consuming`| The default. The contract is consumed by this choice. Trying to exercise another choice on the same contract id will fail.|
|`nonconsuming`| The contract is not consumed by this choice and more choices can be exercised. |
