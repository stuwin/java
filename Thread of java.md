# Callable和Future
```
import java.util.concurrent.Callable;
import java.util.concurrent.FutureTask;

class MyThread implements Callable<String> {

	@Override
	public String call() throws Exception {
		// TODO Auto-generated method stub
		for (int i = 0; i < 20; i++) {
			System.out.println(Thread.currentThread().getName() + "--" + i);
		}
		return "this a test";

	}

}

public class TestMutilThread {
	public static void main(String[] args) {
		MyThread mt = new MyThread();
		FutureTask<String> fTask = new FutureTask<>(mt);
		for (int i = 0; i < 20; i++) {
			System.out.println(Thread.currentThread().getName() + "--" + i);
			if (i == 10) {
				new Thread(fTask, "子线程1").start();
			}
		}
		try {
			System.out.println("子线程返回值：" + fTask.get());
		} catch (Exception e) {
			e.printStackTrace();
		}
	}
}
```
