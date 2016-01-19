##**Syntax:**

```java
(String first, String second) -> {
	return 1
}
```

####Without types if can infer:

```java
Comparator<String> comp = 
  (first, second) -> Integer.compare(first.length(), second.length())
```

####Functional interfaces:

Java 8 retains a lot of the flavour of Java 7 and does not go completely functional:

- There are no pure function types
- A lambda can be assigned to functional interfaces instead

For example:

```java
BiFuncion<String, String, Integer> comp = 
  (first, second) -> Integer.compare(first.length(), second.length())
```

BUT, you can't use this in a a method that expects a `Comparator<String>` argument since that's not a `BiFunction<String, String, Integer>`

####Method references:

Can rewrite:

```java
button.setOnAction(event -> Sytem.out.println(event));
```

as 

```java
button.setOnAction(System.out::println);
```

There are three ways to use short method references:

* `object::instanceMethod` -> 

  * `this::equals ~ x` eq to `this.equals(x)`
  * Note: can use `super` there as well

* `Class::staticMethod` -> 

  * `Math::pow` eq to `(x, y) -> Math.pow(x, y)`

* `Class::instanceMethod`

  * `String::compareToIgnoreCase` eq to `(x, y) -> x.compareToIgnoreCase(y)`





