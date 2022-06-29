# Java

Write a Hello world  program
```
public class basic{
           public static void main(string args[]){
           System.out.println(“Hello java”);
           }}
```

Get the Command line argument in java
```
public class basic{
    public static void main(String args[]){
         for(int i=0; i<args.length; i++){
                 System.out.println(args[i]);
        }}}
```

How to comment the code in java
```
Single line command // command
Multi line command /* command */
```

Scanner class
```
import java.util.Scanner;

public class basic{
    public static void main(String args[]){

        Scanner in = new Scanner(System.in);
        //a2+b2+2ab
        int a,b,c;
        a=in.nextInt();
        b=in.nextInt();
        c=(a*a)+(b*b)+(2*a*b);

        System.out.println(c);
       }
  }
 ```
 
 
 Factorial in java
 ```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        System.out.println("Enter your limit : ");
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int f = 1;
        for(int i=1;i<=n;i++){
           f=f*i;
        }
        System.out.println(f);
    }
}
```

Average of given n number in java
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        System.out.println("Enter your limit : ");
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int sum = 0,a;
        for(int i=1;i<=n;i++){
            System.out.println("Enter your value "+i+" :");
            a = in.nextInt();
            sum+=a;
        }
        System.out.println(sum/n);
    }
}
```

Fibonacci Series in java
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        System.out.println("Enter your limit : ");
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int a = -1,b=1,c;
        for(int i=1;i<=n;i++){
            c=a+b;
            System.out.println(c);
            a=b;
            b=c;
        }
    }
}
```

Reverse of n digit number in java
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        System.out.println("Enter your value : ");
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int reverse = 0, rem;
        while(n!=0){
            rem=n%10;
            reverse = (reverse*10)+rem;
            n=n/10;
        }
        System.out.println(reverse);
    }
}
```


Armstrong Number in java
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        System.out.println("Enter your value : ");
        Scanner in = new Scanner(System.in);
        int number = in.nextInt();
        int temp = number;
        int d1,d2,d3;
        d1 = temp%10;
        temp = temp/10;
        d2 = temp%10;
        temp = temp/10;
        d3 = temp%10;
        temp=temp/10;
        int result = (d1*d1*d1)+(d2*d2*d2)+(d3*d3*d3);
        if(number == result){
            System.out.println(number+" is armstrong number");
        }else{
            System.out.println(number+" is not armstrong number");
        }
    }}
```


Armstrong Number within 100 - 999 in java
```
public class basic{
    public static void main(String[] args){
        int d1,d2,d3,temp,result;
        for(int i=100; i<+999; i++){

            temp = i;
            d3 = temp%10;
            temp = temp/10;
   
            d2 = temp%10;
            temp = temp/10;
   
            d1 = temp%10;
            result = (d1*d1*d1)+(d2*d2*d2)+(d3*d3*d3);
           
        if(i == result){
            System.out.println(i+" is armstrong number");
        }
    }
  }
}
```


Multiplication tables in java
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        System.out.println("Enter your tables you want : ");
        int t = in.nextInt();
        System.out.println("Enter your limit : ");
        int n = in.nextInt();
        for (int i = 1; i <= n; i++){
            System.out.println(t + " x " + i + "= "+(t*i));
        }
    }
}
```


Find factors in java
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        System.out.println("Enter your number : ");
        int n = in.nextInt();
        for (int i = 1; i <= n; i++){
            if(n%i==0){
                System.out.println(i);
            }
        }
    }
}
```

Find prime number in java
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        System.out.println("Enter your number : ");
        int n = in.nextInt();
        int f = 0;
        for (int i = 1; i <= n; i++){
            if(n%i==0){
                f++;
            }
        }
        if(f==2){
            System.out.println(n +" is prime number");
        }else{
            System.out.println(n +" is not prime number");
        }
    }}
```

Find the given number is strong number are not
```
import java.util.Scanner;
public class basic{
    public static void main(String[] args){
        int num,orgnum,rem,factorial,sum=0;
        Scanner in = new Scanner(System.in);
        System.out.println("Enter your number : ");
        num = in.nextInt();
        orgnum = num;
        while(num>0){
            rem=num%10;
            factorial = 1;
            for(int i = 1; i<=rem; i++){
                factorial*=i;
            }sum+=factorial;
            num=num/10;}
        if(sum==orgnum){
            System.out.println(orgnum + " is a strong number");
        }else{
            System.out.println(orgnum + " is not a strong number");
        }}}
```

Find the given number is perfect number are not
```
import java.util.Scanner;
public class HelloWorld{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        System.out.println("Enter your number : ");
        int n = in.nextInt();//6
        int sum = 0;
        for (int i = 1; i < n; i++){
            if(n%i==0){
                sum+=i;
                System.out.println(sum);

            }
        }
        if(sum==n){
            System.out.println(n +" is perfect number");
        }else{
            System.out.println(n +" is not perfect number");
   }}}
```


Find odd even number in java
```
import java.util.Scanner;
public class test{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        System.out.println("Enter your number : ");
        int num = in.nextInt();
        if(num%2==0){
            System.out.println(num + " is a odd number");
        }else{
            System.out.println(num + " is a even number");
        }
     }
  }
```

Sort the array value
```
import java.util.Arrays;
public class test{
    public static void main(String[] args){
        int [] a = new int[]{1,8,10,90,88,45};
        int temp;
        System.out.println("Before sort : "+Arrays.toString(a));
        for(int i=0; i<a.length; i++){
            for(int j=i+1; j<a.length; j++){
                if(a[i] > a[j]){
                    temp = a[i];
                    a[i] = a[j];
                    a[j] = temp;
                }
            }
        }
        System.out.println("After sort : "+Arrays.toString(a));
    }
}
```

Program to insert a element in a specific index of an array
```
import java.util.Arrays;
public class test{
    public static void main(String[] args){
        int [] a = new int[]{1,8,10,90,88,45};
        int index = 3, value = 67;
        System.out.println("Before insert : "+Arrays.toString(a));
        for(int i=a.length-1; i>index; i--){
              a[i] = a[i-1];
        }
        a[index] = value;
        System.out.println("After insert : "+Arrays.toString(a));
    }
}
```


Find duplicate element in an array using java
```
import java.util.Arrays;
public class test{
    public static void main(String[] args){
        int [] a = new int[]{1,8,10,20,10,45,1,90,88,45};
        for(int i=0; i<a.length-1; i++){
            for(int j=i+1; j<a.length; j++){
                if(a[i] == a[j] && i!=j){
                    System.out.println("dubicate element : "+a[j]);
                }
            }
        }
    }
}
```

Two Dimensional Arrays
```
public class test{
    public static void main(String[] args){
        int [][] a = new int[][]{{1,8,10},{20,11,45},{1,90,88}};
        System.out.println(a[0][1]);
    }
}
```


















