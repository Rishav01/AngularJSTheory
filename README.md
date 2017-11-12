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
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        arrayList.add("Mishra");
        System.out.println((String)arrayList.get(10));
        arrayList.remove(10);
        System.out.println((String)arrayList.get(10));
    }
    public void add(Object obj){
        if(array.length-actualSize==0){
            /*System.out.println("Increse Size Called");*/
            increaseLength();
            add(obj);
        }
        else{
            /*System.out.println("Element added at index "+actualSize);*/
            array[actualSize++] = obj;
        }
    }
    
    public void increaseLength(){
        Object[] temp = array;
        array = new Object[(array.length)*2];    
        for(int i=0; i<temp.length; i++){
            array[i]=temp[i];
        }
    }
    
    public Object get(int index){
        return array[index];
    }
    
    public void remove(int index){
        if(index<actualSize){
            for(int i=0; i<actualSize-1; i++){
                if(array[index]==array[i]){
                    array[index]=null;
                    break;
                }
            }
        }
        else{
            System.out.println("Invalid index");
        }
    }
}

import java.util.*;
public class MyClass {
    public static void main(String args[]) {
        MyClass mc = new MyClass();
        String input = "AMan";
        mc.repeatCheck(input);
    }
    public void repeatCheck(String input){
        Map<String, Integer> repeatMap = new HashMap<String, Integer>();
        for(int i=0; i<input.length(); i++){
            for(int j=i+1; j<input.length(); j++){
                String onCheck=input.substring(i,i+1);
                String checkedWith=input.substring(j, j+1); 
                if(onCheck.equalsIgnoreCase(checkedWith)){
                    if(repeatMap.containsKey(onCheck)){
                        repeatMap.put(onCheck, repeatMap.get(onCheck)+1);
                    }
                    else{
                        repeatMap.put(onCheck, 1);
                    }
                }
            }
        }
        Set setview = repeatMap.entrySet();
        Iterator i = setview.iterator();
        while(i.hasNext()){
            System.out.println(i.next());
        }
    }
}

import java.util.*;
public class MyClass {
    public static void main(String args[]) {
        MyClass mc = new MyClass();
        int[] numbers = {1,2,3,4,5,6};
        mc.repeatCheck(numbers);
    }
    public void repeatCheck(int[] numbers){
        int max1, max2;
        if(numbers[0]>numbers[1]){
                max1=numbers[0];
                max2=numbers[1];
            }
            else{
                max2=numbers[0];
                max1=numbers[1];
            }
        for(int i=2; i<numbers.length; i++){
            if(numbers[i]>max1){
                max2=max1;
                max1=numbers[i];
            }
            else if(numbers[i]>max2){
                max2=numbers[i];
            }
        }
        System.out.println(max1+" "+max2);
    }
}




