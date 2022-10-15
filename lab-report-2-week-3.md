# **Week 3 Lab Report**

## **Part 1**

Below is the code for the Simplest Search Engine:

```
# code block
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String str = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("String: %d", str);
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                str += parameters[1];
                return String.format("The string is now %d", parameters[1], str);
            }
            return "404 Not Found!";
        }
    }
}

public class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```

Unfortunately, my code was not working, so there are no screenshots for this part.

## **Part 2**

The first bug I will be going over is the reversed array method below:

```
# code block

static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length];
    }
    return arr;
  }
}

```
I wrote the following to test the method above. It should've returned {1, 0}, but it returned {0,0}.

```
# code block
@Test
public void testReversed2() {
    int[] input1 = {0, 1};
    assertArrayEquals(new int[]{1, 0}, ArrayExamples.reversed(input1));
}
```

The method was supposed to return a new array with the elements in reverse. However, the method returns the origial array. It also got rid of the old values, so it wasn't able to reverse the elements. To fix this, I did the below:

```
# code block
int[] newArray = new int[arr.length];
int j = arr.length; 
for(int i = 0; i < arr.length; i += 1) {
    newArray[j - 1] = arr[i]; 
    j = j - 1; 
}
return newArray; 
```

The second bug I will be going over is the reverseInPlace array method below:

```
# code block
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```

I wrote the following to test the method. It should have returned {0, 1}, but it printed {1, 0}.

```
# code block
@Test 
public void testReverseInPlace2() {
    int[] input1 = {0, 1};
    ArrayExamples.reverseInPlace(input1);
     assertArrayEquals(new int[]{1, 0}, input1);
}
```
I wasn't sure how to fix it, so I wrote the following since doing arr[i] = arr[arr.length - i - 1]; erases the old value, removing the ability to reverse the inputted value.

```
# code block
static void reverseInPlace(int[] arr) {
    int[] newArray = new int[arr.length];
    int j = arr.length; 
    for(int i = 0; i < arr.length; i += 1) {
      newArray[j - 1] = arr[i]; 
      j = j - 1; 
    }
    System.out.print(newArray); 
  }
```

