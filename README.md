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
