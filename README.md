# Defining Datatypes

## data

Algebraic Datatypes

``` haskell
data Point = Pt Float Float
-- Pt - constructor
-- Float Float - fields
```
Sum types

``` haskell
data Bool = True | False deriving (Show)
```

Product types

``` haskell
data Point = Point Float Float deriving (Show)
```

Sum and product combined

``` haskell
data Shape = Circle Point Float | Rectangle Point Point deriving (Show) 
```

Links:
<ol>
    <li>[Algebraic data type](https://wiki.haskell.org/Algebraic_data_type)</li>
</ol>
