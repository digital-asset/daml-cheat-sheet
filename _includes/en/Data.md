|                      |                                                       |
| -------------------- | ----------------------------------------------------- |
| Record | `data MyRecord = MyRecord { label1 : Int, label2 : Text}` |
| Product type | `data Product = Product Int Text` |
| Sum type | `data IntOrText = MyInt Int | MyText Text` |
| Record with type parameters | `data MyRecord a b = MyRecord {label1 : a, label2 : b}` |
| Deriving Show/Eq instances | `data MyRecord = MyRecord {label : Int} deriving (Show, Eq)` |
