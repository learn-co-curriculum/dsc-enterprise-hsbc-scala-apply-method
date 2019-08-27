
# The Magical `apply` method

## About `apply`
Considering the following code once again:


```scala
class Foo(x:Int) {
   def bar(y:Int) = x + y
}
```




    defined class Foo
    



If we run it, it would like this and return `50`


```scala
val foo = new Foo(40)
foo.bar(10)
```




    foo: Foo = Foo@52220d9b
    res51: Int = 50
    



## Replacing `bar` with `apply`
Let’s take the previous code and use apply instead of bar:


```scala
class Foo(x:Int) {
   def apply(y:Int) = x + y
}
```




    defined class Foo
    



If we run it, it would like this and return `50`


```scala
val foo = new Foo(40)
foo.apply(10)
```




    foo: Foo = Foo@783d1bad
    res53: Int = 50
    



Where thing are different, is that `apply` is not a required method call and you can leave the word `apply` out!

Therefore…​since we used apply it looks like this:


```scala
val foo = new Foo(40)
foo(10)
```




    foo: Foo = Foo@22c91f2c
    res54: Int = 50
    



## `apply` Conclusion

* If the method is called apply, no matter where it was defined, you can leave the explict call out!
* This is probably one of the most important aspects to the language that few know about since it too many it is too obvious too mention
