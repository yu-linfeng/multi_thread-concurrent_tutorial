# 线程创建与使用

**线程创建可以通过继承Thread类或实现Runnable接口两种方式。**创建线程的两种方式可能出现在大二学生的期末考试里，或者校招中。这两种方式尽量通过实现Runnable接口来创建线程，Java是单继承，如果继承了Thread类意味着不能再集成另外的类，但Java允许实现多个接口。所以为了保证扩展性，尽量使用实现Runnable接口的方式创建线程。

```public class MyThreadA extends Thread{...}```

```public class MyThreadB implements Runnable{…}```

在```run()```方法中实现线程中需要执行的逻辑。

```java
public class MyThreadB implements Runnable {
    @Override
    public void run() {
        //TODO 执行逻辑
    }
}
```

Runnable接口中的run方法并没有返回值，如果我们希望获取线程执行逻辑后的返回值，则需要实现另一个带参数返回的接口```Callable```，后面会介绍到。