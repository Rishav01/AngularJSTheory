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
