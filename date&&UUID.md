```
import java.text.DecimalFormat;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Random;
import java.util.UUID;
import java.util.logging.Logger;

public class Ter {
	private static Logger logger = Logger.getLogger(Ter.class.toString());
	public static void main(String[] args) {
		Date date = new Date();
		System.out.println(date);
		System.out.println(date.getTime());
		SimpleDateFormat df = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
		System.out.println(df.format(date));
		
		Random random = new Random();
		for (int i = 0; i < 10; i++) {
			System.out.print(random.nextInt()+" ");
			System.out.println("");
		}
		for (int i = 0; i < 10; i++) {
			System.out.print(random.nextInt(1000)+" ");
		}
		double a =10f;
		DecimalFormat decimalFormat = new DecimalFormat("#.00");
		System.out.println(decimalFormat.format(a));
		
		
		logger.info(new SimpleDateFormat("yyyy-MM-dd hh:MM:ss").format(new Date())+"第一次使用logger");
		
		
		System.out.println(UUID.randomUUID().toString());

	}
}
```
