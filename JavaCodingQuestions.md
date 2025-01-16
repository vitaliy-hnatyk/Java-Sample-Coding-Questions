# Java Interview Coding Questions [Solution Improvement in progress]

This repository contains sample Java coding questions that can be used for interview preparation. Each question focuses on a specific programming concept or problem-solving technique using Java 8 features.
## List of Questions

1. **Separate odd and even numbers in a list of integers**

    Given a list of integers, write a Java 8 program to separate the odd and even numbers into two separate lists.

```java
	List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
        
        // Partition the list into two groups: even (true) and odd (false)
        Map<Boolean, List<Integer>> partitionedMap = 
            numbers.stream()
                   .collect(Collectors.partitioningBy(num -> num % 2 == 0));
        
        List<Integer> evenNumbers = partitionedMap.get(true);
        List<Integer> oddNumbers = partitionedMap.get(false);

        System.out.println("Even numbers: " + evenNumbers);
        System.out.println("Odd numbers: " + oddNumbers);

```

2. **Remove duplicate elements from a list using Java 8 streams**

    Write a Java 8 program to remove duplicate elements from a list using the stream API and lambda expressions.
```java
	List<Integer> numbers = Arrays.asList(1, 2, 3, 2, 4, 5, 3, 6, 7, 7, 8);

        List<Integer> uniqueNumbers = numbers.stream()
                                             .distinct()
                                             .collect(Collectors.toList());
        
        System.out.println("Original list: " + numbers);
        System.out.println("List without duplicates: " + uniqueNumbers);

```

3. **Find the frequency of each character in a string using Java 8 streams**

    Write a Java 8 program to find the frequency of each character in a given string using the stream API and collectors.
```java
	String str = "Hello World";

        // Convert string to a stream of characters and group by the character itself
        Map<Character, Long> frequencyMap = str.chars() 
            .mapToObj(c -> (char) c) 
            .collect(Collectors.groupingBy(
                Function.identity(),
                Collectors.counting()
            ));

        // Print the result
        frequencyMap.forEach((ch, count) -> {
            System.out.println(ch + " -> " + count);
        });

```