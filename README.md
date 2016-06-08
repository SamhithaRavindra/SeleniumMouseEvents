# SeleniumMouseEvents
Selenium WebdriverCode To Demonstrate MouseHover


package newpackage;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Action;
import org.openqa.selenium.interactions.Actions;

public class Selenium1 {
	
	
	
	/*Webdriver code to check the background color of the element before and after mouseover*/
	/* Use of MoveToElement mouse function*/
	
	public static void main(String[] args) {
        
		WebDriver driver = new FirefoxDriver();
        String baseUrl = "http://newtours.demoaut.com/";
       driver.get(baseUrl);
        
        WebElement homelink=driver.findElement(By.linkText("Home"));
        WebElement hometable=driver.findElement(By.xpath("//html/body/div"
                + "/table/tbody/tr/td"
                + "/table/tbody/tr/td"
                + "/table/tbody/tr/td"
                + "/table/tbody/tr"));
        
        Actions builder=new Actions(driver); //Instantiating actions object
        Action MouseOnHome=builder.moveToElement(homelink).build();//Instantiating Action using Actions object
        //Build method is the final method to be used so that all the actions will be complied into a single step
        
        String bgColor1=hometable.getCssValue("background-color");
        System.out.println("Before hover: " + bgColor1); 
        
        MouseOnHome.perform();// Perform method is used to execute the Action defined.
        
        
        String bgColor2=hometable.getCssValue("background-color");
        System.out.println("After hover: " + bgColor2);
        driver.quit();
}
        
        
        
        
        
      
	}
	
	


