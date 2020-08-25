# Frequently Asked Questions: {-}

1. Where can I find due dates for assignments?

*BBLearn*

2. How do I submit assignments?

*All assignments (except the very first git assignment) are submitted via BBLearn as both .Rmds and .pdfs*

3.  Do I still have to submit written exercises as .Rmd and .pdf?

*Yes.*

4. What's better for code, conciseness or readability?

`Readability>Conciseness`

*I personally almost always use dplyr, my thoughts, pulled largely from Dr. Derek Sonderegger's Statistical Computing Course are below:*

The pipe command in `dplyr` `%>%` allows for very readable code. The idea is that the `%>%` operator works by translating the command *a* `%>%` *f(b)* to the expression *f(a,b)*. This operator works on **any function** and was introduced in the `magrittr` package. The beauty of this comes when you have a suite of functions that take input arguments of the same type as their output.  They are human readable!

For example if we wanted to start with *x*, and first apply function *f()*, then *g()*, and then *h()*, the usual R command would be *h(g(f(x)))* which is hard to read because you have to start reading at the innermost set of parentheses. Using the pipe command `%>%`, this sequence of operations becomes *x* `%>%` *f()* `%>%` *g()* `%>%` *h()*.

Dr. Hadley Wickham (aka R genius) gave the following example of readability:
```
bopping(
  scooping_up(
    hopping_through(foo_foo),
    field_mice),
  head)
```
is more readably written:

```
foo_foo %>% 
  hopping_through(forest) %>%
  scooping_up( field_mice) %>%
  bopping( head )
```

In dplyr, all the functions take a data set as its first argument and outputs an appropriately modified data set. This allows me to chain together commands in a readable fashion.  Then in 3 months I don't have to wonder what on earth I was doing last time I opened this project, if I filtered the data, etc etc.  Your future self will sincerely thank your past self.