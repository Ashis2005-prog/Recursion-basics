#Recursion Basics
import java.util.*;
public class RecursionBasics{
    //printing in decreasing manner
    public static void decreasingOrder(int n){
        //base case
        if(n==0){
            return;
        }
        //kaam
        System.out.print(n+" ");
        decreasingOrder(n-1);

    }
    //printing in increasing manner
    public static void increasingOrder(int n){
        //base case
        if(n==1){
            System.out.print(n+" ");
            return;
        }

        //kaam
        increasingOrder(n-1);
        System.out.print(n+" ");
    }
    //print sum
    public static int sum(int n){
       int sum=0;
        //base case
        if(n==0){
            return 0;
        }
        //kaam
        sum+=n+sum(n-1);
        return sum;
    }
    //friends pairing problem
    public static int pairing(int n){
        //base case
        if(n==0||n==1){
            return n;
        }
        //kaam
        return pairing(n-1)+(n-1)*pairing(n-2);
    }

    //remove duplicates in a String
    public static void removeDuplicates(String str, StringBuilder sb, boolean map[], int idx) {
        if (idx == str.length()) {
            System.out.println(sb);
            return;
        }
        // kaam
        char currChar = str.charAt(idx);
        if (map[currChar - 'a'] == true) {
            removeDuplicates(str, sb, map, idx + 1);
        } else {
            map[currChar - 'a'] = true;
            removeDuplicates(str, sb.append(currChar), map, idx);
        }
    }
   public static void main(String[] args){
    Scanner sc=new Scanner(System.in);
    System.out.println("Enter a value for n and str");
    int n=sc.nextInt();
    decreasingOrder(n);
    System.out.println();
    increasingOrder(n);
    System.out.println();
    System.out.println(sum(n));
    System.out.println(pairing(n));
    String str = sc.nextLine();
    int idx = 0;
    StringBuilder sb = new StringBuilder();
    removeDuplicates(str, sb, new boolean[26], idx);
   }
}
