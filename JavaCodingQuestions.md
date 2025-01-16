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