## Primitive to ArrayList

```java
ist<Integer> list = Arrays.stream(number).boxed().collect(Collectors.toList());
```

## Sorting List

```java
Collections.sort(list,(a,b)->a.compareTo(b));

Collections.sort(list,(a,b)->{ return a.length() - b.length();} );


Comparator<Employee> byEmployeeNumber = (e1, e2) -> Integer.compare(e1.getId(), e2.getId());


Collections.sort(
    personList, 
    (p1, p2) -> p1.getFirstName().compareTo(p2.getFirstName())
);

Collections.sort(
    personList,
    Comparator.comparing(Person::getFirstName)
);


Collections.sort(
    personList, 
    comparing(Person::getFirstName).thenComparing(Person::getLastName)
);

```