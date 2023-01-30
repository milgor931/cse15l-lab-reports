# CSE 15L Lab 2

*Servers and Bugs*

# Part 1

 ![before](whats poppin mister.png)
 ![after](whats poppin mister result.png)
  
 ![port 5000 working example](Look it works.png)

 ![StringServer.java code](StringServer Code.png)
  
# Part 2

A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
Briefly describe why the fix addresses the issue.

### The (Before) Buggy Method to Test
This method is supposed to take in an integer array as an input and generate a new array and return it with the elements of the original array in reversed order. 

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
```

### Failure-Inducing Input as JUnit Test


```
@Test
public void testReversedNormal() {
    int[] arr = { 1, 2, 3 };
    assertArrayEquals(new int[]{ 3, 2, 1 }, ArrayExamples.reversed(arr));
}
```

### Non-Failure-Inducing Input as JUnit Test

The testReversed() method works on an empty array since it also returns an empty array.

```
@Test
public void testReversedEmpty() {
    int[] input1 = {  };
    assertArrayEquals(new int[]{  }, ArrayExamples.reversed(input1));
}
```

### Symptom of Running Tests
![lab 3 test symptom](test fail and test pass.png)

### Code Fix

#### Before
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
```

#### After
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```

The code fix involved making sure that the new array is updated, not the elements of the old one with the null newArray elements. We also made a fix to make sure that the created newArray is returned, not the original input array.
  
# Part 3
  
In lab 2, I learned how to make a web server with Java which is something that I have never done before. I learned that Java has an interface called *URIHandler*. I also learned that Java has a *Server.start()* method which makes creating the web server easy to do because you just pass on the Handler object you are using and what port to host it on locally. You also have to create a special Handler class which implements the URI interface in order to handle requests. You can handle requests on the website, such as interpreting paths, returning text, or making queries, by overriding the *handleRequest()* method in the Handler class. 
