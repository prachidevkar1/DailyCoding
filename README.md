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
