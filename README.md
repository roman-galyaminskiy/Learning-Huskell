# Table of contents
1. [Defining Datatypes](#Defining-Datatypes)

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

Record syntax

``` haskell
data Point = Pt {pointx, pointy :: Float}
-- Selector functions
pointx :: Point -> Float 
pointy :: Point -> Float 
```

Rarameterized types

``` haskell
data Vector a = Vector a a a deriving (Show) 
-- Vector a - type constructor
-- Vector a a a - value constructor

Prelude> :t Vector
Vector :: a -> a -> a -> Vector a

Prelude> Vector 1 2 3
Vector 1 2 3

```

## newtype

Generaly could be replaced by **data** with following constraints:
* exactly one constructor
* exactly one field


``` haskell
newtype Natural = MakeNatural Integer deriving (Show)

a = MakeNatural 1
b = MakeNatural 2
a + b -- Doesn't work. It's not inheritance!

<interactive>:44:1: error:
    • No instance for (Num Natural) arising from a use of ‘+’
      There are instances for similar types:
        instance Num GHC.Natural.Natural -- Defined in ‘GHC.Num’
    • In the expression: a + b
      In an equation for ‘it’: it = a + b
```

## type
Synonym for a type and uses the same data constructors

``` haskell
type Natural = Int

(1::Natural) + (2::Natural) = 3 -- works!
```
Rarameterized synonims

``` haskell
type AssocList k v = [(k,v)]
```


Links:
1. [Algebraic data type](https://wiki.haskell.org/Algebraic_data_type)
2. [Newtype](https://wiki.haskell.org/Newtype)
3. [Type](https://wiki.haskell.org/Type)