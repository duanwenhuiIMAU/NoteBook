# java期中考试

## 1题目要求：以矩阵的形式打印输出二维数组,并在每行的行尾输出该行的和.
    import java.util.Arrays;
    public class Test{
    public static void main(String[] args){
            int[][] a={{1,2},{3,4},{5,6}};
            int i,j; /*循环变量*/
            int sum=0; /*行和变量*/
        /****************begin***************/
        for(i=0;row<a.length;i++){
            int sum_row=0;
            for(j=0; column<a[i].length;j++){
                System.out.print(a[i][j]+"  ");
                sum_row+=a[i][j];
            }
            System.out.print(sum_row); // out 为小写
            System.out.println();
        }
        /****************end***************/		
        }
        //用 sublime text 时要退出win + e
    }
## 2题目要求：接收命令行参数,形式如"3  +  2",输出两个数的和.

    public class Test{
    public static void main(String[] args){
        int x,y; /*操作数*/
    /****************begin***************/ 
        x=Integer.parseInt(args[0]);
        y=Integer.parseInt(args[2]);
        switch(args[1].charAt(0)){
            case'+':System.Out.println(x+y);break;
            case'-':System.Out.println(x-y);break;
            case'*':System.Out.println(x*y);break;
            case'/':System.Out.println(x/y);break;
        }
     /****************end***************/
    }
## 3题目要求：设计成员方法sign()和main(),

    其中sign()接收一个整型变量，如果其值大于0返回1，等于0返回0，小于0返回-1，
    在main()方法中调用sign()方法。

    public class Test{
        /****************begin***************/
        public static void main(String[] args){
            sign(1);
        }
        public static int sign(int a){
            if(a>0)return 1;
            else if (a==0)return 0;
            else return -1;
        }
        /****************end***************/	
    }
## 4题目要求：题目要求：用Scanner输入3个数，输出最大值。

    import java.util.Scanner;
    public class Test{
    /****************begin***************/
        Scanner input = new Scanner(System.in);
        int max = input.nextInt();
        int b = input.nextInt();
        if(max < b)max = b;
        int c = input.nextInt();
        if(max < c)max = c;
        System.out.println( max );
    /****************end***************/
    }
## 5用字符串输入一个小写字母输出它的大写字母和ASCII码
    import java.util.Scanner;

    public class test{
        //
        public static void main(String agrc[]){
            Scanner input = new Scanner(System.in);
            String str = input.nextLine();//用Scanner类读取键盘输入的一个字符
            char ch =str.charAt(0);//保存到char 类型变量中 
            System.out.println("upper char :"+ Character.toUpperCase(ch)+ "\n "+" ACSII of char : "+  ch+32);
            input.close();
        }
    }
## 6将形如 Kim Jones 的姓和名分别取出保存到字符串中
    public class Test{
    public static void main(String[] args){
        String s="Kim Jones"; 
        int k; 
    /****************begin***************/
        k=s.indexOf(" ");
        String xing = s.substring(0,k);
        String name = s.substring(k+1,s.length());
        System.out.println(xing + " " + name );
    /****************end***************/