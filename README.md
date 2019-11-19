
package Gmail;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

public class Women {
	public static void main(String[] args) {
		System.setProperty("webdriver.chrome.driver", "D://chromedriver.exe");
		WebDriver driver = new ChromeDriver();
		driver.get("https://demoqa.com/droppable/");
		driver.manage().timeouts().implicitlyWait(4, TimeUnit.SECONDS);
		WebElement v=driver.findElement(By.id("draggable"));
		WebElement w =driver.findElement(By.id("droppable"));
		Actions act = new Actions(driver);
		//act.dragAndDrop(v, w).build().perform();
		act.clickAndHold(v).moveToElement(w).release().build().perform();
		driver.close();
		
	}

}
