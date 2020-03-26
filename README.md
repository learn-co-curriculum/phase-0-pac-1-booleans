# Boolean Expressions

## Learning Goals

* Use Equality Comparison
* Use Inequality Comparison
* Use Greater-Than Comparison `>`
* Use Less-Than Comparison `<`
* Use Greater-Than-or-Equal-To Comparison `>=`
* Use Less-Than-or-Equal-To Comparison `<=`
* Invert Truth Value with "Bang" (`!`)
* Invert Truth Value with "Double-Bang" (`!!`)
* Identify Truthy and Falsey Values in Ruby
* Join Boolean Expressions with AND
* Join Boolean Expressions with OR

## Introduction

As we saw in the ternary expression, sometimes we need to _get_ a Boolean value
(`true` or `false`) _from another_ expression to use it _in another
expression_.  In the previous lesson, we showed that we can use the
greater-than operator (`>`) and less-than operator (`<`) to perform comparisons
that produce or _calculate_ `true` or `false`. Let's learn some more operators
so we can have more tests that return `true` or `false`.

## Arithmetic Comparisons

### Use Equality Comparison

To check whether two values are equal, we use the *equality operator* represented
with `==` ("double-equal-sign"). If two values are equal, then the statement
will return `true`. If they are not equal, then it will return `false`. For
example:

```ruby
1 == 1 #=> true
1 == 7 #=> false
```

**IMPORTANT**: The comparison operator `==` _is not the same as the assignment
operator_ `=`, which is used to assign values to variables.

_In Ruby, we also compare `String`s (case sensitive!_):

```ruby
"Razz" == "Matazz" #=> false
"Poodle" == "Poodle" #=> true
"Poodle" == "poodle" #=> false
```

### Use Inequality Comparison

To check whether two values **are not** equal, we use the *inequality operator*
represented with `!=` (which programmers pronounce as "bang-equals"). If two
values are _not_ equal, then the statement will return `true`. If they are
equal, then it will return `false`. For example:

```ruby
1 != 1 #=> false
1 != 7 #=> true
"Poodle" != "Lord of the Manor" #=> true
```

## Quantity Comparisons

You might recall these from school: comparisons of greater-than versus
greater-than-or-equal-to.

### Use Greater-Than Comparison `>`

If the value on the left of the operator is *greater than* the value on the
right, then the evaluation is `true`; `false` otherwise.

### Use Less-Than Comparison `<`

If the value on the left of the operator is *less than* the value on the
right, then the evaluation is `true`; `false` otherwise.

### Use Greater-Than-or-Equal-To Comparison `>=`

If the value on the left of the operator is *greater than or equal to* the
value on the right, then the evaluation is `true`; `false` otherwise.

### Use Less-Than-or-Equal-To Comparison `<=`

If the value on the left of the operator is *less than or equal to* the
value on the right, then the evaluation is `true`; `false` otherwise.

## Invert Truth Value with "Bang" (`!`)

The `!` operator inverts a truth value. Here's the most simple version:

```ruby
!true #=> false
!false #=> true
```

We can also invert the truth value of an expression:

```ruby
( 1 + 1 == 2 ) #=> true
!( 1 + 1 == 2 ) #=> false
```

Since `1 + 1` evaluates to `2`; and since `2 == 2` the return value is `true`.

## Invert Truth Value _Twice_ with "Double-Bang" (`!!`) Part 1

The `!!` operator inverts a truth value, _then inverts it once more_. Here's the
most simple version:

```ruby
!!true #=> true
!!false #=> false
```

We can also apply this to an expression:

```ruby
!!( 1 + 1 == 2 ) #=> true
```

Now, why would this ever be useful? Great question. To address this we need to
take a slight tangent to discuss what counts as `true` and `false` in Ruby.

## Truthiness in Ruby 

Ruby will treat a whole bunch of values as `true` that aren't the literal
`true`. We call those values "truthy." Similarly, there are values that, even
if they aren't the literal `false`, Ruby treats as false. We call those values
"falsey."

This next statement is ***very important***:

> **IMPORTANT**: Ruby will treat anything that is `false` or `nil` as `false`,
> but ***everything*** else as `true`.

So:

```ruby
false ? true : false  #=> false
nil   ? true : false  #=> false

6.7   ? true : false  #=> true
1 + 1 ? true : false  #=> true
0 ? true : false #=> true (!)
:i_once_saw_a_poodle_play_racquetball ? true  : false  #=> true
```

The ternary expressions here show us that numbers (even zero) evaluate
to `true`.

## Invert Truth Value with "Double-Bang" (`!!`) Part 2

It is common to use the _truthiness_ of a value to do something conditionally
in code. In these cases, programmers will sometimes use the double-bang to
explicitly return a `true` or `false` value. 


```ruby
!!false #=> false
!!nil   #=> false
!!6.7   #=> true
!!(1 + 1) #=> true
!!:i_once_saw_a_poodle_play_racquetball #=> true
```

This is a way for programmers to say to other programmers "Hey, I'm being
clever here and am using a truthy value but I _really_ intend to derive a
`true` / `false` value from it."

> **What's with "Bang?"** Programmers, being lazy people, thought that
> "exclamation point" was too long to say, so it became "bang".

## Identify Truthy and Falsey Values in Ruby

This concept is ***so*** important we're going to repeat it:

> **IMPORTANT**: Ruby will treat anything that is `false` or `nil` as falsey;
> all other things, even things you've not heard of yet, are treated as truthy

## Join Boolean Expressions with AND

In Ruby `&&` ("double-ampersand") represents "AND." For an `&&` ("and") to
evaluate to `true`, both values on either side of the symbol must evaluate to
`true`. For example:

```ruby
true && true #=> true
true && false #=> false
```

It's common to say things like:

"IF it's Thursday AND my Mom is not home THEN I will play scary video games all
night on the living-room TV."

In Ruby, we would express this "double-conditional" like so.

```ruby
day_is_thursday = true
mom_is_not_home = true
# Ternary
# Position 1                         # Position 2               # Position 3
day_is_thursday && mom_is_not_home ? "play scary video games" : "do homework"
```

## Join Boolean Expressions with OR

In Ruby `||` ("double-pipe") represents "OR." For an `||` ("or") to evaluate to
`true`, _only one_ value on either side of the symbol must evaluate to `true`.
For example:

```ruby
false || true #=> true
```

Of course, keep in mind, these Boolean values can, themselves, be expressions
that return a Boolean value!  Instead of `false && true` it could another
expression that results in `true` or `false` like `(poodle_count > 12) &&
(owner == "Lorlei Gilmore")`

## Longer Expressions

Because of the ability to use parentheses `()`, "and" (`&&`), "or" (`||`), and
the ternary expression, we can create surprisingly rich tiny programs.

```ruby
chance_of_precipitation = 1000
temperature = -1000
it_is_wet = ( chance_of_precipitation > 0.5 )
it_is_cold = ( temperature <= 5 )
it_is_wet && it_is_cold ? "snow-suit" : "something less bulky" #=> "snow-suit"
it_is_wet && !it_is_cold ? "umbrella" : "light fabric"
```

## Conclusion

Learning how to join logical Boolean expressions allows us to make expressions
that are surprisingly rich!

With this collection of comparison operators, you're able to express a
surprisingly complex series of desires to Ruby!

From a "programming as conversation" perspective, you're now communicating at the
sophistication level of most early teens!
