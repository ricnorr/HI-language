# HI language
## Features
### Arithmetics
hi> **mul(2, 10)**

20

hi> **sub(1000, 7)**

993

hi> **div(3, 5)**

0.6

hi> **div(add(mul(2, 5), 1), sub(11,6))**

2.2
### Boolean algebra

hi> **not(true)**

false

hi> **and(true, false)**

false

hi> **or(true, false)**

true

hi> **if(greater-than(div(2, 5), div(3, 7)), 1, -1)**

-1

### Operators

hi> **2 + 2**

4

hi> **2 + 2 * 3**

8

hi> **(2 + 2) * 3**

12

hi> **2 + 2 * 3 == (2 + 2) * 3**

false

hi> **10 == 2*5 && 143 == 11*13**

true

### Strings and slices

hi> **to-upper("what a nice language")(7, 11)**

"NICE"

hi> **"Hello" == "World"**

false

hi> **length("Hello" + "World")**

10

hi> **length("hehe" * 5) / 3**

6 + 2/3

### Lists and folds

hi> **list(1, 2, 3, 4, 5)**

[ 1, 2, 3, 4, 5 ]

hi> **fold(add, [2, 5] * 3)**

21

hi> **fold(mul, range(1, 10))**

3628800

hi> **[0, true, false, "hello", "world"](2, 4)**

[ false, "hello" ]

hi> **reverse(range(0.5, 70/8))**

[ 8.5, 7.5, 6.5, 5.5, 4.5, 3.5, 2.5, 1.5, 0.5 ]

### Bytes and serialisation

hi> **pack-bytes(range(30, 40))**

[# 1e 1f 20 21 22 23 24 25 26 27 28 #]

hi> **zip(encode-utf8("Hello, World!" * 1000))**

[# 78 da ed c7 31 0d 00 20 0c 00 30 2b f0 23 64 0e 30 00 df 92 25 f3 7f a0 82 af
   fd 1a 37 b3 d6 d8 d5 79 66 88 88 88 88 88 88 88 88 88 88 88 88 88 88 88 88 88
   88 88 88 88 88 88 88 88 fc c9 03 ca 0f 3b 28 #]

hi> **decode-utf8([# 68 69 #] * 5)**

"hihihihihi"

hi> **unzip([# 78 da 63 64 62 06 00 00 0d 00 07 #])**

[# 01 02 03 #]

### File I/O

hi> **mkdir("tmp")!**

null

hi> **read("tmp")!**

[]

hi> **mkdir("tmp/a")!**

null

hi> **mkdir("tmp/b")!**

null

hi> **read("tmp")!**

[ "a", "b" ]

hi> **write("tmp/hi.txt", "Hello")!**

null

hi> **cd("tmp")!**

null

hi> **read("hi.txt")!**

"Hello"

### Date and time

hi> **now!**

parse-time("2021-12-15 00:42:33.02949461 UTC")


hi> **parse-time("2021-01-01 00:00:00 UTC") + 365 * 24 * 60 * 60**

parse-time("2022-01-01 00:00:00 UTC")

### Random numbers

hi> **rand**

rand

hi> **rand(0, 10)**

rand( 0, 10 )

hi> **rand(0, 10)!**

8

hi> **rand(0, 10)!**

3

### Short-circuit evaluation

hi> **echo**

echo

hi> **echo("Hello")**

echo("Hello")

hi> **echo("Hello")!**

Hello

null

hi> **"Hello"(0) || "Z"**

"H"

hi> **"Hello"(99) || "Z"**

"Z"

hi> **if(2 == 2, echo("OK")!, echo("WTF")!)**

OK

null

hi> **true || echo("Don't do this")!**

true

hi> **false && echo("Don't do this")!**

false

hi> **[# 00 ff #] && echo("Just do it")!**

Just do it

null

### Dictionaries

hi> **count("Hello World").o**

2

hi> **invert(count("big blue bag"))**

{ 1: [ "u", "l", "i", "e", "a" ], 2: [ "g", " " ], 3: ["b"] }

hi> **fold(add, values(count("Hello, World!")))**

13





