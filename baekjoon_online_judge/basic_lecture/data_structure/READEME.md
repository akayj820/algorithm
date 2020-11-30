알고리즘 기본 개념정리


## 자료구조
</br>

### 스택
***
* 한쪽 끝에서만 자료를 넣고 뺄 수 있는 자료구조이다. 
* 마지막으로 넣은 것이 가장 먼저 나오기 때문에 Last In First Out(LIFO) 라고 한다.

</br>

> stack 구현 소스코드 java ver.

````java
import java.util.*;
public class Main {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] stack = new int[n];
        int size = 0;
        while (n-- > 0) {
            String cmd = sc.next();
            
            if (cmd.equals("push")) {
            /*** push 함수 ***/	
                int num = Integer.parseInt(sc.next());
                stack[size++] = num;
                
            } else if (cmd.equals("top")) {
            /*** top 함수 ***/	
                if (size == 0) {
                    System.out.println("-1");
                } else {
                    System.out.println(stack[size-1]);
                }
                
            } else if (cmd.equals("size")) {
            /*** size 함수 ***/	
                System.out.println(size);
                
            } else if (cmd.equals("empty")) {
        	/*** empty 함수 ***/
                if (size == 0) {
                    System.out.println("1");
                } else {
                    System.out.println("0");
                }
                
            } else if (cmd.equals("pop")) {
        	/*** pop 함수 ***/
                if (size == 0) {
                    System.out.println("-1");
                } else {
                    System.out.println(stack[size-1]);
                    size -= 1;
                }
            }
        }
    }
}
````

</br></br></br>

### 큐
***
* 한쪽 끝에서만 자료를 넣고 다른 한쪽 끝에서만 뺄 수 있는 자료구조이다.

</br>

> queue 구현 소스코드 java ver.

````java
import java.util.*;

public class Main {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] queue = new int[n];
        int begin = 0;
        int end = 0;
        while (n-- > 0) {
            String cmd = sc.next();
            if (cmd.equals("push")) {
                int num = Integer.parseInt(sc.next());
                queue[end++ ] = num;
            } else if (cmd.equals("front")) {
                if (begin == end) {
                    System.out.println("-1");
                } else {
                    System.out.println(queue[begin]);
                }
            } else if (cmd.equals("size")) {
                System.out.println(end-begin);
            } else if (cmd.equals("empty")) {
                if (begin == end) {
                    System.out.println("1");
                } else {
                    System.out.println("0");
                }
            } else if (cmd.equals("pop")) {
                if (begin == end) {
                    System.out.println("-1");
                } else {
                    System.out.println(queue[begin]);
                    begin += 1;
                }
            } else if (cmd.equals("back")) {
                if (begin == end) {
                    System.out.println("-1");
                } else {
                    System.out.println(queue[end-1]);
                }
            }
        }
    }
}
````

