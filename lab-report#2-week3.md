
# PART 1: SEARCH ENGINE #

## **CODE FOR SEARCH ENGINE** ##

'
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList; // import the ArrayList class

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> stringsAdded = new ArrayList<String>(); // Create an ArrayList object
    ArrayList<String> stringsFound = new ArrayList<String>();

    public String handleRequest(URI url) {
        System.out.println("Path: " + url.getPath());
        if (url.getPath().contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                stringsAdded.add(parameters[1]);
                return String.format("String is added to list!");
            }
            else {
                return String.format("Please input correctly");
            }
        }
        
        if (url.getPath().contains("/search")) {
            String[] parameters = url.getQuery().split("=");
            if (stringsAdded.size()==0){
                return String.format("You must add a string first!!!");
            }
            else{
                for(int i=0; i<stringsAdded.size(); i++) {
                    if ((stringsAdded.get(i)).contains(parameters[1])){
                        stringsFound.add(stringsAdded.get(i));
                    }
                }
                return String.format("Strings Found" + stringsFound);
            }
        }
        else {
            return "error";
        }
}
}



class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
'
# **REFLECTION AND SCREENSHOTS FOR SEARCH ENGINE** #

##ADDING PINEAPPLE SCREENSHOT##
![](week%203%20pictures/2022-10-14%20(2).png)
**Description:**
In the screenshot above, the word pineapple is added to my array list. In this process a few methods are called including getPath to get the path in the URL, getQuery and contains to see if the path contains the word add. After that, the method getQuery is called again paired with split, to create two different elements in the array parameters (one element that contains the word add etc and the other element which contains the word we want to add). We use another built in method called equals to ensure that the input is correctly formatted to have "s"(expecting a string). After this we use the built in method "add" to add the string into the arrayList with all the added strings. Throughout this process we have a few values changing. We have two ArrayLists and one array. I made an array called stringsAdded, which starts off empty but then later contains the added string (the one we get after splitting after the equal sign). stringsFound arrayList should remain empty as we have not used it in this process. Further, parameters is an array of the path input that we time in the URL, this is used to just split the add portion with the actual word we want to add and the values in this are changed everytime the URL path is changed. 

## ADDING APPLE SCREENSHOT
![](week%203%20pictures/2022-10-14%20(4).png)

**Description:**
This is the exact example as above, just the word is apple in this case instead of pineapple. For a detailed description of the screenshot refer to the previous explanation


## SEARCHING FOR "APP" SCREENSHOT##
![](week%203%20pictures/2022-10-14%20(3).png)
In the screenshot above, the string "app" is searched for through the array lis, stringsAdded to form the stringsFound arrayList and ultimately printed for the user to see. In this process a few methods are called including getPath to get the path in the URL, and contains to see if the string "Search" is in the url (which would indicate that the user wants to search something. Once again, the method getQuery is called paired with split, to create two different elements in the array parameters (one element that contains the word search etc and the other element which contains the word we want to search for). Once we have split the input into two parts (the first and second element of the array called parameters), we loop through the array of the stringsAdded and see if each element of that array contains the second element of parameters. In these stpes we use the inbuilt method size() to contrain our for loop. Since now we are working with an array we use the inbuilt methods called add and get inside to the for loop to access each element of the arrayList. Finally we use the in built method format to return the strings and objects that we want ot show on the screen. In this aspect we start with an already created stringAdded arraylist and do not alter it (only access it).On the other hand, we start off with an empty stringFound arraylist and add all the words that contain the queried string. 

## INCORRECT PATHWAY ERROR SCREENSHOT
![](week%203%20pictures/2022-10-14%20(5).png)

**Description:**
There are no new methods called or values created, however, if a user does not add a URL with the appropriate add or search keywords and format, the "error" message will be printed on the screen. This is done through the else format in terms of coding. 

# PART TWO: BUGS & SYSTEMS

## EXAMPLE 1

**Failure Inducing Input**
Input: {5, 4, 3, 2, 1};
Code: 
'
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  '
**Symptom**
![](week%203%20pictures/2022-10-14%20(6).png)

**Fixed Bug + Description**
![](week%203%20pictures/2022-10-14%20(7).png)
In this example the bug itself was quite simple. The programmer had switched the new array and the array multiple times. It should be the new arrays values being set in the for loop and the new array being printed in the end. In this case no new values were added into the new array so that is why the error said the array length differed. 

##EXAMPLE 2##
**Failure Inducing Input**
Input: Following is the picture of the test/input for the method
![](pictures%20for%20lab%20report%202/listtest.png)

Code: 

'   static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index2 += 1;
    }
    return result;
  }
'

**Symptom**
The test did not run for a while and when it did it produced the following output
![](pictures%20for%20lab%20report%202/erroroutput2pic.png)

**Fixed Bug + Description**
Fixed Bug: ![](pictures%20for%20lab%20report%202/fixed%20code.png)
Fixed Output: ![](pictures%20for%20lab%20report%202/correctOutput.png)
In this example the bug itself was quite simple. Instead of aggregating the index2 in the while loop for index 2 after both lists have been merged (and then there are a few extra as length might not be exactly even). In this case index 2 would stay the same and new objects would continually be created while index 1 continues to +=1, this is essentially an infinite loop as index 2 will always stay less than list2size if it was less initially. Further, as there is no limit on index1 it will continue growing forever, making this an infinite loop.
