# Recursion-basics
import java.util.*;
public class RecursionBasics{
    public static void decreasingOrder(int n){
        //base case
        if(n==0){
            return;
        }
        //kaam
        System.out.print(n+" ");
        decreasingOrder(n-1);

    }
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
    
   public static void main(String[] args){
    Scanner sc=new Scanner(System.in);
    System.out.println("Enter a value for n & x");
    int n=sc.nextInt();
    int x=sc.nextInt();
    decreasingOrder(n);
    System.out.println();
    increasingOrder(n);
    System.out.println();
    System.out.println(sum(n));
   }
}
