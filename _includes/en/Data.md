|                             |                                                                          |
|-----------------------------|--------------------------------------------------------------------------|
| Record                      | `data MyRecord = MyRecord { label1 : Int, label2 : Text}`                |
| Record (`with` syntax)      | `data MyRecord = MyRecord with`<br>`  label1 : Int`<br>`  label2 : Text` |
| Sum type                    | `data IntOrText = MyInt Int | MyText Text`                               |
| Record with type parameters | `data MyRecord a b = MyRecord {label1 : a, label2 : b}`                  |
| Deriving instances          | `data MyRecord = MyRecord {label : Int} deriving (Show, Eq)`             |
