# DailyCoding

 1 ANAGRAMS
 import java.util.Arrays;
class anagram{
    public static void main(String args[])
    {
        String str="listen";
        String str1="silent";
        
        str=str.replaceAll("//s","").toLowerCase();
        str1=str1.replaceAll("//s","").toLowerCase();
        
        if(str.length()!=str1.length())
        {
            System.out.println("not anagrams");
        }
        char a[]=str.toCharArray();
        char b[]=str.toCharArray();
        
        Arrays.sort(a);
        Arrays.sort(b);
        if(Arrays.equals(a,b))
        {
            System.out.println("anagrams");
            
        }
        else{
            System.out.println("not anagrms");
        }
        }
    }
## Remove Duplicate from String
class DuplicateRemove {
    public static void main(String args[]) {
        String str = "programming";
        String result = "";

        for (int i = 0; i < str.length(); i++) {
            char currentChar = str.charAt(i);
            boolean found = false;

            // check if character already exists in result
            for (int j = 0; j < result.length(); j++) {
                if (result.charAt(j) == currentChar) {
                    found = true;
                    break;
                }
            }

            // if not found, add to result
            if (!found) {
                result += currentChar;
            }
        }

        System.out.println("Original: " + str);
        System.out.println("Without Duplicates: " + result);
    }
}



## Count frequency of character in given string 
import java.util.*;
class CountFrequency
{
    public static void main(String args[]){
        String str="hello";
        int freq[]=new int[256];
        for(char c:str.toCharArray())
        {
            if(c != ' ')
            {
                freq[c]++;
            }
            
        }
        for(int i=0;i<freq.length;i++)
        {
            if(freq[i]>0)
            System.out.println( (char)i+";"+freq[i]);
        }
    }
}

## String rotation

public class StringRotationManual {
    public static void main(String[] args) {
        String s1 = "abcde";
        String s2 = "cdeab";

        if (s1.length() != s2.length()) {
            System.out.println("Not rotation");
            return;
        }

        boolean isRotation = false;

        for (int i = 0; i < s1.length(); i++) {
            // left rotation: move substring(0,i) to the end
            String rotated = s1.substring(i) + s1.substring(0, i);

            if (rotated.equals(s2)) {
                isRotation = true;
                break;
            }
        }

        if (isRotation) {
            System.out.println("Yes, rotation");
        } else {
            System.out.println("No, not rotation");
        }
    }
}

s1.substring(i) + s1.substring(0, i)
👉 This is the key trick for simulating a rotation.
s1.substring(i) → gives the part of the string from index i to the end.
s1.substring(0, i) → gives the part of the string from the beginning to index i-1.
Concatenating them (+) means we are cutting the string at position i and flipping the two parts.
Example: s1 = "abcde"
i = 0 → "abcde" + "" → "abcde"
i = 1 → "bcde" + "a" → "bcdea"
i = 2 → "cde" + "ab" → "cdeab" ✅ rotation of "abcde"
i = 3 → "de" + "abc" → "deabc"
i = 4 → "e" + "abcd" → "eabcd"
**A rotation is like taking the end part of a string and bringing it to the front.
When you do s1+s1, you basically cover all possible end+front combinatio.**

## method 2
public class StringRotation {
    public static void main(String[] args) {
        String s1 = "abcde";
        String s2 = "cdeab";

        if (s1.length() == s2.length() && (s1 + s1).contains(s2)) {
            System.out.println("Yes, rotation");
        } else {
            System.out.println("No, not rotation");
        }
    }
}

**( "abcdeabcde".contains("cdeab") ) 
.contains(CharSequence s)
This is a method of the String class in Java.
What does .contains() do?**
**It checks if one string exists inside another string (as a substring).
Returns:
true → if the substring is found
false → if not found**



## check substiring 
public class SubstringCheck {
    public static void main(String[] args) {
        String s1 = "hello world";
        String s2 = "world";
        boolean found = false;

        // loop through s1
        for (int i = 0; i <= s1.length() - s2.length(); i++) {
            int j;
            // check characters one by one
            for (j = 0; j < s2.length(); j++) {
                if (s1.charAt(i + j) != s2.charAt(j)) {
                    break; // mismatch → break inner loop
                }
            }
            if (j == s2.length()) { // matched all chars
                found = true;
                break;
            }
        }

        if (found) {
            System.out.println("Yes, substring");
        } else {
            System.out.println("No, not substring");
        }
    }
}


## method 2
if (s1.contains(s2)) {
    System.out.println("Yes, substring");
} else {
    System.out.println("No, not substring");
}

if (s1.indexOf(s2) != -1) {
    System.out.println("Yes, substring");
} else {
    System.out.println("No, not substring");
}
**indexOf gives starting position; -1 means not found**


## CHECK IF GIVEN CHARACTER IS SPECIAL SYM ,LETTER ,DIGIT 
import java.util.*;
class Check {
    public static void main(String args[]){
        
     Scanner sc=new Scanner (System.in);  
    System.out.println("enter any char");
    char c=sc.next().charAt(0);

    
    if(Character.isLetter(c))
    {
        System.out.println("is a letter");
    }
    else if(Character.isDigit(c))
    {
        System.out.println("is a digit");
    }
    else
    {
        System.out.println("is a Special Symbol");
    }
    
    
}
}

## Shopping Calculator
import java.util.*;
class Check {
    public static void main(String args[]){
        
        Scanner sc=new Scanner(System.in);
        System.out.println("enter your shopping amount");
        double amount =sc.nextDouble();
        double disc;
        
        
        if(amount>=5000)
        {
        disc=amount*0.20;
     System.out.println("you final amount is " + (amount - disc));
        }
        else if(amount>=2000)
        { 
             disc=amount*0.10;
         System.out.println("you final amount is " + (amount - disc));
        }
        else
        {
            System.out.println("you final amount is" +amount);
            
        }
    }
}


## CALCULATE AVG OF ARRAY ELEMENT

public class ArrayAverageCalculator {
    public static void main(String args[]) {
        
        int[] numbers = {22, 2, 34, 5, 6};
        int sum = 0;
        
    
        if (numbers.length == 0) {
            System.out.println("The array is empty. Cannot calculate average.");
           
            return;
        }

        
        for (int element : numbers) {
            sum = sum + element; 
        double average = (double) sum / numbers.length; 
        
    
        System.out.println("The array elements' average is: " + average);
    }
}




## CHECK BALANCED PARENTHESIS
class BalancedParenthesis{
    public static void main(String args[])
    {int count=0;
        String str="()()))";
        boolean balanced=false;
        for(int i=0;i<str.length();i++)
        {
            char c=str.charAt(i);
            if(c=='(')
            {
                count++;
            }
            else if(c==')')
            {
                count--;
            }
            if(c<0)
            {System.out.println("invalid");
                break;
            }
            
            
        }
        
            if(balanced && count==0)
            {
                System.out.println("balanced");
            }
            else
            {
                System.out.println("not balanced");
            }
            
    }
}

## FIRST NON REPETED CHARACTER
public class NonRepeat {
    public static void main(String[] args) {
        String str = "swiss";
        char result = 0;

        for (int i = 0; i < str.length(); i++) {
            char c = str.charAt(i);
            
            if (str.indexOf(c) == str.lastIndexOf(c)) {
                result = c;
                break;
            }
        }

        if (result != 0) {
            System.out.println("First non-repeated character: " + result);
        } else {
            System.out.println("No non-repeated character found");
        }
    }
}


## ALL REPETED AND NON REPEATED
class NonRepeat {
    public static void main(String args[]) {
        String str = "prachii";

        String nonRepeated = "";  // store non-repeated chars
        String repeated = "";     // store repeated chars

        for (int i = 0; i < str.length(); i++) {
            char c = str.charAt(i);

            // only check first occurrence (to avoid duplicate entries in repeated/non-repeated)
            if (str.indexOf(c) == i) {
                if (str.indexOf(c) == str.lastIndexOf(c)) {
                    nonRepeated += c + " ";
                } else {
                    repeated += c + " ";
                }
            }
        }

        System.out.println("Non-repeated characters: " + nonRepeated);
        System.out.println("Repeated characters: " + repeated);
    }
}

 ## PERMUTATION OF STRING
 public class PermutationsManual {
    public static void main(String[] args) {
        String str = "abc";
        char[] arr = str.toCharArray();
        permute(arr, 0);
    }

    static void permute(char[] arr, int start) {
        if (start == arr.length - 1) {
            // print current arrangement
            System.out.println(String.valueOf(arr));
            return;
        }

        for (int i = start; i < arr.length; i++) {
            swap(arr, start, i);          // fix character at 'start'
            permute(arr, start + 1);      // permute rest
            swap(arr, start, i);          // backtrack to restore original array
        }
    }

    static void swap(char[] arr, int i, int j) {
        char temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}

## Check if String Contains Only Digits
public class OnlyDigits {
    public static void main(String[] args) {
        String str = "12345";
        boolean allDigits = true;

        for (int i = 0; i < str.length(); i++) {
            if (!Character.isDigit(str.charAt(i))) {
                allDigits = false;
                break;
            }
        }

        System.out.println(allDigits);
    }
}

 ## Reverse words in a sentence

Example: "I love Java" → "Java love I"
public class ReverseWords {
    public static void main(String[] args) {
        String sentence = "I love Java";
        String[] words = sentence.split(" "); // split by space
        String reversed = "";

        for (int i = words.length - 1; i >= 0; i--) {
            reversed += words[i] + " ";
        }

        System.out.println(reversed.trim());
    }
}
## Find the longest word in a sentence

Logic:

Split sentence → loop through words → find word with max length.
public class LongestWord {
    public static void main(String[] args) {
        String sentence = "I love programming in Java";
        String[] words = sentence.split(" ");
        String longest = "";

        for (String w : words) {
            if (w.length() > longest.length()) {
                longest = w;
            }
        }

        System.out.println("Longest word: " + longest);
    }
}

 ## c) Count number of words

Logic:

Split sentence by space → array length = number of words.

String sentence = "I love Java";
int count = sentence.split(" ").length;
System.out.println("Number of words: " + count);
