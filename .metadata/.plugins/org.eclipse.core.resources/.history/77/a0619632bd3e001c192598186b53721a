package com.test;

import java.util.concurrent.TimeUnit;

import org.junit.After;
import org.junit.Before;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.NoSuchElementException;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

public class AmazonSearch {
	private WebDriver driver;
	
	@Before
	public void setup() {
		
		System.setProperty("webdriver.chrome.driver", "./src/test/resources/Chrome/chromedriver.exe");
		driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.get("https://www.amazon.com/");
	}
	
	@Test
	
	public void testAmazon() {
		
		WebElement searchbox = driver.findElement(By.name("field-keywords"));
		
		//searchbox.clear();
		searchbox.sendKeys("adidas");
		searchbox.submit();
		

		driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		
		WebElement selectElement = driver.findElement(By.id("a-autoid-0-announce"));

		WebElement elements;
		try {
		   
			elements = selectElement.findElement(By.xpath("//*[@id=\"s-result-sort-select_2\"]"));

		} catch (NoSuchElementException e) { 
		   
		    selectElement.click();
		    
		    elements = selectElement.findElement(By.xpath("//*[@id=\"s-result-sort-select_2\"]"));
		}
		
		elements.click();
		
	
		driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
		
		WebElement price = driver.findElement(By.id("s-result-sort-select_2"));
		price.click();
	
		
		
	}
    
	@After
	
	public void tearDown() {
		
		driver.quit();
	}
}
