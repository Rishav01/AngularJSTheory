# AngularJSTheory

Java Programs
Multithreading
1.	How thread is created and how does it works?
By extending thread class – 
public class MyClass extends Thread{
    public void run(){
        System.out.println("Run method executed");
    }
    public static void main(String args[]) {
        MyClass mc1 = new MyClass();
        mc1.start();
    }
}
By implementing runnable interface – 
public class MyClass implements Runnable{
    public void run(){
        System.out.println("Run method executed");
    }
    public static void main(String args[]) {
        MyClass mc1 = new MyClass();
        Thread t1 = new Thread(mc1);
        t1.start();
    }
}
Note: We can extend Thread class and implement Runnable interface simultaneously by a class. 
2.	One task by two threads to see thread effect. 
public class MyClass implements Runnable {
    public void run(){
        for(int i=1; i<=10; i++){
            System.out.println(i);
           /* try{
                Thread.sleep(200);
            }
            catch(Exception e){
                System.out.println("Exception in Sleep method of thread");
            }*/
        }
    }
    public static void main(String args[]) {
        MyClass mc1 = new MyClass();
        MyClass mc2 = new MyClass();
        Thread t1 = new Thread(mc1);
        Thread t2 = new Thread(mc2);
        t1.start();
        t2.start();
    }
}
Note: Without sleep method, one thread works on the task at a time. However, sleep() method keeps the currently running thread to sleep for the specified time and control goes to the other thread. 
3.	Two task by two threads or multiple task by multiple threads. [home]
4.	


Date 9th November, 2017
public class MyArrayList {
    Object[] array;
    int actualSize=0;
    public MyArrayList(){
        array = new Object[10];
    }
    public static void main(String args[]) {
        MyArrayList arrayList = new MyArrayList();
        arrayList.add("Rishav");
        arrayList.add("Mishra");
        System.out.println((String)arrayList.get(1));
        
        /*System.out.println(arrayList.toString());*/
    }
    public void add(Object obj){
        if(array.length-actualSize<=5){
            increaseLength();
        }
        else{
            array[actualSize++] = obj;
        }
    }
    
    public void increaseLength(){
        array = new Object[(array.length)*2];    
    }
    
    /*
    public String toString(){
        String returnedString = (String) array[actualSize-1];
        return returnedString;
    }*/
    
    public Object get(int index){
        return array[index];
    }
    
    public void remove(Object obj){
        for(int i=0; i<actualsize-1; i++){
            if(array[i]==obj){
                array[i]=null;
            }
        }
    }
}
5. 
Solution:
import java.util.*;
public class MyClass {
    public static void main(String args[]) {
        ArrayList ar = new ArrayList();
        ar.add("a");
        ar.add("d");
        ar.add("c");
        ar.add("b");
        
        Collections.sort(ar);
        
        Iterator it = ar.iterator();
        while(it.hasNext()){
            System.out.println(it.next());
        }
    }
}
Note: it sort the number in increasing order as well. 

6. Same as above
7. ar.set(index, Element);
8. ar.contains(Element);
9. ar.remove(index);
10. 
Solutiion:
import java.util.*;
public class MyClass {
    public static void main(String args[]) {
        ArrayList ar = new ArrayList();
        ar.add("2");
        ar.add("2");
        ar.add("3");
        ar.add("1");
        ar.add("4");
        ar.add("4");
        for(int i=0; i<ar.size(); i++){
            for(int j=i+1; j<ar.size(); j++){
                if(ar.get(i)==ar.get(j)){
                    ar.remove(i);
                    break;
                } 
            }
        }
        Iterator i = ar.iterator();
        while(i.hasNext()){
            System.out.println(i.next());
        }
    }
}
Note: length of arraylist is found by mention size(). LinkedList and Vector works exactly same as ArrayList. 

Date 10th November, 2017

public class MyArrayList {
    Object[] array;
    int actualSize=0;
    public MyArrayList(){
        array = new Object[10];
    }
    public static void main(String args[]) {
        MyArrayList arrayList = new MyArrayList();
        arrayList.add("Rishav");
        arrayList.add("Mishra");
        System.out.println((String)arrayList.get(1));
        
        /*System.out.println(arrayList.toString());*/
    }
    public void add(Object obj){
        if(array.length-actualSize<=5){
            increaseLength();
        }
        else{
            array[actualSize++] = obj;
        }
    }
    
    public void increaseLength(){
        array = new Object[(array.length)*2];    
    }
    
    /*
    public String toString(){
        String returnedString = (String) array[actualSize-1];
        return returnedString;
    }*/
    
    public Object get(int index){
        return array[index];
    }
    
    public void remove(Object obj){
        for(int i=0; i<actualsize-1; i++){
            if(array[i]==obj){
                array[i]=null;
            }
        }
    }
}



