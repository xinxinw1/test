# test

Testing Github Features

# Header 1

## Hea Add a bit der 2

Testing detatch

Hey
---

What
====

What
----


What
----

What
====

Test
++++

## How to use in HTML

1. Go to https://github.com/xinxinw1/tools/releases and download the latest release.
2. Go to https://github.com/xinxinw1/prec-math/releases and download the latest release.
3. Optionally, if you want complex number functions, go to https://github.com/xinxinw1/cmpl-math/releases and download the latest release.
4. Go to https://github.com/xinxinw1/math-check/releases and download the latest release.
5. Extract `tools.js` from the first download, `prec-math.js` from the second, and `cmpl-math.js` from the third, and `math-check.js` from the fourth into your project directory.
6. Add
   
   ```html
   <script src="tools.js"></script>
   <script src="prec-math.js"></script>
   <script src="cmpl-math.js"></script> <!-- if you want complex numbers -->
   <script src="math-check.js"></script>
   ```
   
   to your html file.
7. Run `$.al(Checker.proc(R.mul)(2534, 5253))` to make sure it works.  
   (Should output `13311102`)
8. If you are using complex numbers, run `$.al(Checker.proc(C.mul)(2534, "5253"))` to make sure it works.  
   (Should output `["13311102", "0"]`)

See http://xinxinw1.github.io/math-check/ for a demo.

## How to use in Node.js

1. Go to https://github.com/xinxinw1/tools/releases and download the latest release.
2. Go to https://github.com/xinxinw1/prec-math/releases and download the latest release.
3. Optionally, if you want complex number functions, go to https://github.com/xinxinw1/cmpl-math/releases and download the latest release.
4. Go to https://github.com/xinxinw1/math-check/releases and download the latest release.
5. Extract `tools.js` from the first download, `prec-math.js` from the second, and `cmpl-math.js` from the third, and `math-check.js` from the fourth into your project directory.
6. Run `$ = require("./tools.js")` in node.
7. Run `R = require("./prec-math.js")` in node
8. If you want complex numbers, run `C = require("./cmpl-math.js")` in node
9. Run `Checker = require("./math-check.js")` in node.
10. Run `$.prn(Checker.proc(R.mul)(2534, 5253))` to make sure it works.  
    (Should output `13311102` and return `undefined`)
11. If you are using complex numbers, run `$.prn(Checker.proc(C.mul)(2534, "5253"))` to make sure it works.  
    (Should output `["13311102", "0"]` and return `undefined`)

## How to use in HTML

1. Go to https://github.com/xinxinw1/tools/releases and download the latest release.
2. Go to https://github.com/xinxinw1/ajax/releases and download the latest release.
3. Extract `tools.js` from the first download and `ajax.js` from the second download into your project directory.
4. Add

   ```html
   <script src="tools.js"></script>
   <script src="ajax.js"></script>
   ```
   
   to your html file.
5. Run `$.al($.get("ajax.js"))` to make sure it works.

See http://xinxinw1.github.io/ajax/ for a demo.


# Javascript Tools

This is a huge set of tools functions for doing common tasks like getting the length of an item, getting a slice of an item, replacing x with y in a, etc. This module works in both web js and Node.js.

## How to use in HTML

1. Go to https://github.com/xinxinw1/tools/releases and download the zip of the latest release.
2. Extract `tools.js` to your project directory.
3. Add `<script src="tools.js"></script>` to your html file.
4. Run `$.al("Hello World! | Array: $1 | String: $2 | Object: $3", [1, 2, 3], "hey", {a: 3, b: "test", c: [3, 4, 5]});` to make sure it works.

See http://xinxinw1.github.io/tools/ for an example.

## How to use in Node.js

1. Go to https://github.com/xinxinw1/tools/releases and download the zip of the latest release.
2. Extract `tools.js` to your project directory.
3. Run `$ = require("./tools.js")` in node
4. Run `$.prn("Hello World! | Array: $1 | String: $2 | Object: $3", [1, 2, 3], "hey", {a: 3, b: "test", c: [3, 4, 5]});` to make sure it works.

## Function reference

```
Note: This is an incomplete reference, so some functions exist, but aren't documented yet

Note 2: These are all accessed by $.<insert name>

win               window
doc               window.document
inf               Infinity

### Type

cls(a)            Object.prototype.toString.call(a);
typ(a)            a short type name for a

### Predicates

nump(a)           is a a number, 
strp(a)             string,
arrp(a)             array,
irrp(a)             immutable array,
fnp(a)              function,
objp(a)             object,
rgxp(a)             regex,
bolp(a)             boolean,
trup(a)             true,
falp(a)             false,
htmp(a)             an html element,
docp(a)             an html document,
winp(a)             an html window,
txtp(a)             an html text node,
errp(a)             a $.Err object
udfp(a)             undefined,
nulp(a)             or null

### Comparison

is(a, b)          a === b;
iso(a, b)         is(a, b) or a and b have the same elements
inp(a, ...x)      is a one of x

### Dynamic vars

sta(a, x, f)      a = [x, a]; f(); a = a[1]; dynamically stack x onto a

### Display

dsp(a)            formats a for printing

### Output

out(a)            console.log(a);
prn(a, ...args)   out(apl(stf, arguments)); (see below for apl and stf)
alr(a)            win.alert(a);
al(a, ...args)    alr(apl(stf, arguments));

### Converters

num(a)            Number(a)
tint(a, rdx)      converts a to an int using radix rdx (default 10)
tflt(a)           parseFloat(a)
str(...a)         joins arguments into a string
tarr(a)           converts a to an array
tfn(a)            makes a function that tests whether the input is === a
tobj(a)           converts a to an object
htm(a)            converts a to an html element

### Sequence

#### Items

ref(a, i)         get the ith element of a
ref(a, ...args)   run ref(a, i) on each element of args
fst(a)            get first element of a
las(a)            get last element of a

#### Apply

apl(f, a)         f.apply(this, a);
map(x, a)         map function x over a
pos(x, a, n)      get the position of x in a starting at n (n = 0 by default)
pol(x, a, n)      pos starting from end of a
has(x, a)         does a have x in it?
mny(x, a)         does a have more than 1 x in it?
all(x, a)         each item in a is x?
keep(x, a)        copy a with non x's removed
rem(x, a)         copy a with x removed (cut)
remf(x, a)        copy a with x removed from front of a
rpl(x, y, a)      copy a with x replaced with y
mat(x, a)         get the first match of function or regex x in a
mats(x, a)        get all the matches of function or regex x in a
cnt(x, a)         count the number of times x occurs in a

#### Whole

len(a)            get length of a
emp(a)            is a empty
cpy(a)            copy a
cln(a)            deep copy
rev(a)            copy a with items reversed

#### Parts

sli(a, n, m)      get slice of a from n (inclusive)
                    to m (not inclusive)
fstn(n, a)        first n items in a
lasn(n, a)        last n
rstn(n, a)        sli(a, n)
rst(a)            sli(a, 1)
butn(n, a)        get all except for the last n items
but(a)            butn(1, a)

#### Group

spl(a, x)         split a by x
grp(a, n)         group a into groups of n
tup(...a)         generalized pair

#### Join

joi(a, x)         join array a into a string with x between 
                    every two elements (default x = "")
fla(a, x)         flattens the 2 (or more) d array a with x
                    between every two elements
fla(a)            flattens the 2 (or more) d array
app(...a)         appends all its arguments together
nof(n, a)         append a to itself n times

#### Fold / Reduce

fold(f, x, a)     fold(function (a, x){return a+x;}, 0, [1, 2, 3])
                  -> (((0+1)+2)+3)
fold(f, a)        fold(function (a, x){return a+x;}, [1, 2, 3])
                  -> ((1+2)+3)
foldr(f, x, a)    foldr(function (x, a){return x+a;}, 0, [1, 2, 3])
                  -> (1+(2+(3+0)))
foldr(f, a)       analogous to fold(f, a)

#### Array

hea(a, x)         copy array a with length+1 and make the first
                    element x
tai(a, x)         copy with length+1 and set last element to x

### Imperative

A number of modifying versions of the functional functions earlier
See source code for details

#### Array

psh(x, a)         a.push(x)
pop(a)            a.pop()
ush(x, a)         a.unshift(x)
shf(a)            a.shift()

#### Other

att(x, a)         attach x to a; add elements of x to end of a

### Object and alist

keys(a)           get keys of object a
vals(a)           get vals of object a
okey(a)           Object.getOwnPropertyNames(a)
oval(a)           get values using okey(a)

aref(a, x)        get item x from association list a
aset(a, x, y)     set x to y in alist a
adel(a, x)        delete x from alist a

ohas(a, x)        a.hasOwnProperty(x)
oput(a, x, y)     a[x] = y
orem(a, x)        delete a[x] and return old a[x]

oref(a, x)        get x in a; if a[0] is an object, looks there recursively
oset(a, x, y)     set x to y in a; if x isn't in a, recursively set x in a[0]
osetp(a, x)       oref(a, x) !== udf
odel(a, x)        shadow a[x] with undefined; return old a[x]
oren(a, x, y)     rename x to y in a

### String

low(a)            a.toLowerCase()
upp(a)            a.toUpperCase()
stf(a, ...args)   string fill; replaces every occurence of "$1" with 
                    dsp() of the 1st item in args and similarly for 
                    the rest of the args

### Function

sig(a)            get the "signature" of function a; $.sig($.sig) -> "sig(a)"
prms(a)           get parameters of function a; $.prms($.map) -> ["x", "a"]

### List

A few simple Lisp functions to implement $.sta()
See source code for details

### DOM

$(a)              doc.getElementById(a)
elm(a, o, ...c)   make html element with tag name a, attributes o, and
                    children c
txt(a)            doc.createTextNode(a)
top(a)            scroll to the top of a
bot(a)            scroll to the bottom of a

### File

rea(a)            gets the contents of the file a as a string
lns(a)            gets the lines of the file a as an array
wri(x, a)         writes x to a

### Regex

cap(x, a)         return first capturing group from finding x in a
caps(x, a)        return all capturing groups

### Time

tim()             get current time in milliseconds after unix epoch

### Speed tests

spd(a, b, n)      alert the time it takes to run a n times and to run b n times

### Debug

cnts(a)           count the number of times each element in a occurs

### Error

err(f, a, ...x)   returns an error formatted with stf(a, ...x)

### Other

rnd(min, max)     random number from min to max inclusive

```

# Number Factoring Script

Uses GNU coreutils factor and readline to quickly and easily factor large numbers.

## How to run

1. Go to https://github.com/xinxinw1/ruby-factor/releases and download the latest release.
2. Extract `factor.rb` to any directory.
3. Open a shell and cd to that directory.
4. Run `$ ruby factor.rb`

## Instructions

If you type in any positive integer (ex. 10276938564540) and press enter, you'll get a readable version of its factors. The factors will be separated by "*" which represents multiplication and "^" which means exponentiation.

If the number is prime, you will just get the original number back.

If you type in many positive integers separated by "+" (ex. 190890 + 63252 + 44226) and press enter, you'll get two lines: The first one factors out the greatest common divisor (gcd) from the numbers, and the second line factors all of the numbers.

All spaces in the input are ignored.

You can press the up and down keys to go to previous inputs.

Press Ctrl+C during a calculation to cancel it without exiting.

Type "exit" or "quit" or press Ctrl+C at ">" to exit.

## Examples

A huge number (2^200 - 1)

`1606938044258990275541962092341162602522202993782792835301375`

Powers of 2

`2 + 4 + 8 + 16 + 32 + 64 + 128 + 256 + 512`

[Frank Nelson Cole's famous number](http://en.wikipedia.org/wiki/Frank_Nelson_Cole)

`147573952589676412927`

2^2048 (Watch this calculate instantly)

`32317006071311007300714876688669951960444102669715484032130345427524655138867890893197201411522913463688717960921898019494119559150490921095088152386448283120630877367300996091750197750389652106796057638384067568276792218642619756161838094338476170470581645852036305042887575891541065808607552399123930385521914333389668342420684974786564569494856176035326322058077805659331026192708460314150258592864177116725943603718461857357598351152301645904403697613233287231227125684710820209725157101726931323469678542580656697935045997268352998638215525166389437335543602135433229604645318478604952148193555853611059596230656`
