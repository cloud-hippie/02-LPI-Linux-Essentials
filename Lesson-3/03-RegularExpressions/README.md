# 3.2 - Basic Regular Expressions

Regular expressions are a powerful way to match patterns in text.

Below are examples of `regex` patterns and what they do:



`^Apple` - match the start of a line

`Apple$` - match the end of the line 

`^Apple$` - match the Start AND end of the line

`Apple|Ball` - match either string

`Ap*le` - match `Ap` followed by 0 or more `p`s followed by le`

`Ap+le` - match `A` followed by one or more `p`s followed by `le`

`Ap?le` - match `A` followed by maybe a `p` followed by a `le`

`Ap[p-z]le` - match `Ap` followed by a letter between `p-z` folloed by `le`
