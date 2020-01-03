Clear Trip Web Driver:
package com.mop.qa.exam;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class Driversteup {
WebDriver driver;
public static WebDriver setup1(){
System.setProperty("webdriver.chrome.driver","C:\\New folder\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
driver.get("https://www.cleartrip.com/");
return driver; } }
Clear Trip Excel:
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import org.apache.poi.ss.usermodel.Cell;
import org.apache.poi.ss.usermodel.DataFormatter;
import org.apache.poi.ss.usermodel.Row;
import org.apache.poi.xssf.usermodel.XSSFCell;
import org.apache.poi.xssf.usermodel.XSSFRow;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class Excel {
public static String getCellValue(String sheetName, int rowNum, int colNum) throws Exception {
File src;
String cellValue = null;
try {
src = new File("C:\\Users\\jisape0\\!strun\\src\\red.xlsx");
FileInputStream excelfile = new FileInputStream(src);
XSSFWorkbook workbook = new XSSFWorkbook(excelfile);
XSSFSheet sheet = workbook.getSheet(sheetName);
XSSFRow row = sheet.getRow(rowNum);
/DataFormatter formatter = new DataFormatter();
XSSFCell cell = row.getCell(colNum);
cellValue = cell.getStringCellValue();
} catch (Exception e) {
e.printStackTrace();  }    return cellValue;}}
Clear Trip Xpath:
public class Xpath {
public static String oneway = "//input[@id='OneWay']";
public static String From = "//input[@id='FromTag']";
public static String To = "//input[@id='ToTag']";
public static String date = "//input[@id='DepartDate']";
public static String adults = "//*[@id='Adults']/option[4]";
public static String child = "//*[@id='Childrens']/option[1]";
public static String infants = "//*[@id='Infants']/option[2]";
public static String search = "//*[@id='SearchBtn']";
}
import org.testng.annotations.Test;
import org.testng.annotations.BeforeTest;
import java.io.File;
import org.apache.commons.io.FileUtils;
import org.apache.poi.ss.usermodel.DataFormatter;
import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.AfterTest;
public class codee {
public static WebDriver driver;
@Test
public void f() throws Exception {
driver.findElement(By.xpath(Xpath.oneway)).click();
WebElement from = driver.findElement(By.xpath(Xpath.From));
from.sendKeys(Excel.getCellValue("sheetName", 2, 0));
WebElement to = driver.findElement(By.xpath(Xpath.To));
to.sendKeys(Excel.getCellValue("sheetName", 2, 1));
driver.findElement(By.xpath(Xpath.date)).sendKeys("01/01/2020");
driver.findElement(By.xpath(Xpath.adults)).click();
driver.findElement(By.xpath(Xpath.child)).click();
WebElement element1 = driver.findElement(By.xpath(Xpath.infants));
WebDriverWait wait = new WebDriverWait(driver, 30);
wait.until(ExpectedConditions.visibilityOf(element1));
element1.click();
WebElement element2 = driver.findElement(By.xpath(Xpath.search));
element2.click();
wait.until(ExpectedConditions.visibilityOf(element2));
element2.click();
File s = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(s, new File("C:\\Users\\jisape0\\Tst\\src" + "scrennsaver" + ".png"));
Thread.sleep(6000); }
@BeforeTest
public void beforeTest() {
driver = driversteup.setup1();}}
@AfterTest
public void afterTest(){
driver.quit();  }}
********************************************************************************************************
GOIBIBOO Web Driver
import java.io.File;
import java.io.IOException;
import java.util.concurrent.TimeUnit;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class chromeDriver {
static WebDriver driver;
public static WebDriver driver() {
System.setProperty("webdriver.chrome.driver", "C:\\Users\\770834\\Documents\\chrome\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
return driver; } }
GOIBIBOO Excel
public static String getCellValue(String sheetName, int rowNum, int colNum) throws Exception {
File src;
String cellValue = null;
try {
src = new File("C:\\Users\\jisape0\\!strun\\src\\red.xlsx");
FileInputStream excelfile = new FileInputStream(src);
XSSFWorkbook workbook = new XSSFWorkbook(excelfile);
XSSFSheet sheet = workbook.getSheet(sheetName);
XSSFRow row = sheet.getRow(rowNum);
XSSFCell cell = row.getCell(colNum);
cellValue = cell.getStringCellValue();
} catch (Exception e) {
e.printStackTrace();}
return cellValue; }
GOIBIBOO  Codee :
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileOutputStream;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;
import org.apache.bcel.generic.Select;
import org.apache.commons.collections4.map.StaticBucketMap;
import org.apache.commons.io.FileUtils;
import org.apache.poi.poifs.crypt.dsig.KeyInfoKeySelector;
import org.ietf.jgss.Oid;
import org.junit.jupiter.api.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.remote.server.handler.SendKeys;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;
import com.gargoylesoftware.htmlunit.javascript.host.file.FileReader;
import ExampleTwo.DriverSetup;
import ExampleTwo.excelReader;
import net.bytebuddy.asm.Advice.Enter;
import net.bytebuddy.asm.Advice.This;

public class mainclass {
chromeDriver set = new chromeDriver();
WebDriver driver;
@BeforeMethod
public void cleartrip() {
driver = chromeDriver.praveen();
driver.get("https://www.goibibo.com/");
}@Test
public void operation() throws Exception {
// elements
WebElement gb = driver.findElement(By.id("gosuggest_inputSrc"));
WebElement nextPlace = driver.findElement(By.id("gosuggest_inputDest"));
// clicks
gb.click();
nextPlace.click();
// values
gb.sendKeys(excel.getCellValue("sheetName", 2, 0));
Thread.sleep(2000);
gb.sendKeys(Keys.DOWN);
gb.sendKeys(Keys.ENTER);
nextPlace.sendKeys(excel.getCellValue("sheetName", 2, 1));
Thread.sleep(1000);
nextPlace.sendKeys(Keys.DOWN);
nextPlace.sendKeys(Keys.ENTER);
// dates
driver.findElement(By.id("pax_link_common")).click();
Scanner adult = new Scanner(System.in);
System.out.println("enter number of adults");
int k = adult.nextInt();
for (int i = 0; i < k; i++) {
driver.findElement(By.id("adultPaxPlus")).click();}
Thread.sleep(3000);
File screenshotFile = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(screenshotFile, new File("C:\\Users\\jisape0\\!strun\\src" + "scrennsaver" + ".png"));}




Marshall
package petZone;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.firefox.FirefoxDriver;
public class DriverSetUp {
static WebDriver driver;
public static WebDriver praveen() {
ChromeOptions options = new ChromeOptions();
options.addArguments("--disable-notifications");
WebDriver driver = new ChromeDriver(options);
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
return driver;
}
public static WebDriver fox() {
FirefoxDriver firefox = new FirefoxDriver();
firefox.manage().window().maximize();
firefox.manage().timeouts().implicitlyWait(30, TimeUnit.SECONDS);
return driver;
}}
//////////////////////////////////
package petZone;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.OutputStream;
import java.nio.file.Path;
import java.util.Date;
import org.apache.poi.ss.usermodel.CellValue;
import org.apache.poi.xssf.eventusermodel.XSSFSheetXMLHandler;
import org.apache.poi.xssf.usermodel.XSSFCell;
import org.apache.poi.xssf.usermodel.XSSFRow;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class Xcel {
public static String getcellvalue(String sheet, int rowNum, int colNum) {
String cellValue = null;
try {
FileInputStream src = new FileInputStream("C:\\Users\\jisape0\\MarshallsPetZone\\src\\red.xlsx");
XSSFWorkbook wb = new XSSFWorkbook(src);
XSSFSheet petSheet = wb.getSheet(sheet);
XSSFRow row = petSheet.getRow(rowNum);
XSSFCell cell = row.getCell(colNum);
cellValue = cell.getStringCellValue();
} catch (Exception e) {
// TODO: handle exception
}return cellValue;}
public static String write(String s, String s1) {
String writeValue = null;
try {
File path = new File("pet.xlsx");
// String pathOfXcel 
System.getProperty("C:\\Users\\jisape0\\MarshallsPetZone\\src");
XSSFWorkbook sheetName = new XSSFWorkbook();
XSSFSheet marshal = sheetName.createSheet("petSheet");
marshal.createRow(0).createCell(2).setCellValue(s);
// marshal.getRow(0).createCell(6).setCellValue(s1);
OutputStream fileOut = new FileOutputStream(path);
sheetName.write(fileOut);
} catch (Exception e) {
// TODO: handle exception}
return writeValue;}}
//////////////////////////////
package petZone;
import java.io.File;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
public class Main extends DriverSetUp {
// DriverSetUp set = new DriverSetUp();
WebDriver driver;
@BeforeMethod
public void Marshell() {
driver = DriverSetUp.praveen();
driver.get("https://www.marshallspetzone.com/");
}
@Test
public void Operation() throws Exception {
Actions actions = new Actions(driver);
WebElement menuOption = driver.findElement(By.xpath("//*[@id=\"cbp-hrmenu-tab-20\"]/a"));
actions.moveToElement(menuOption).build().perform();
driver.findElement(By.linkText("Puppy Food")).click();
WebDriverWait wait = new WebDriverWait(driver, 40);
WebElement element = driver
.findElement(By.xpath("//*[@id=\"js-product-list\"]/div/div[13]/article/div[1]/a/img"));
wait.until(ExpectedConditions.visibilityOf(element));
element.click();
WebDriverWait wait2 = new WebDriverWait(driver, 20);
WebElement element2 = driver
.findElement(By.xpath("//*[@id=\"add-to-cart-or-refresh\"]/div[2]/div/div[2]/div/button"));
wait.until(ExpectedConditions.visibilityOf(element2));
String str = element2.getText();
element2.click();
WebElement a = driver.findElement(By.linkText("Proceed to checkout"));
String st1r = a.getText();
Xcel.write(str, st1r);
File screenshotFile = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(screenshotFile, new File("C:\\Users\\jisape0\\MarshallsPetZone\\src" + "MARSHALL" + ".png"));
}}




AXIS BANK:
Driver SetUp:
package AxisBank;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.firefox.FirefoxOptions;
import org.openqa.selenium.ie.InternetExplorerDriver;
import org.openqa.selenium.ie.InternetExplorerOptions;
import org.openqa.selenium.remote.DesiredCapabilities;
public class DriverSetUp {
public static WebDriver driver;
public static String WebsiteUrl = "https://www.axisbank.com/retail/calculators/fd-calculator";
public WebDriver setUpChrome(){
System.setProperty("webdriver.chrome.driver", "C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\Selenium Softwares\\chromedriver\\chromedriver.exe");
ChromeOptions Options = new ChromeOptions();
Options.addArguments("--disable-notifications");
WebDriver driver = new ChromeDriver(Options);
driver.manage().window().maximize();
driver.manage().deleteAllCookies();
driver.manage().timeouts().pageLoadTimeout(300, TimeUnit.SECONDS);
driver.manage().timeouts().implicitlyWait(60, TimeUnit.SECONDS);
driver.navigate().to(WebsiteUrl);
return driver;}
public static WebDriver setUpFirefox(){
System.setProperty("webdriver.gecko.driver", "C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\Selenium Softwares\\geckodriver-v0.25.0-win64\\geckodriver.exe");
FirefoxOptions Options = new FirefoxOptions();
Options.addArguments("--disable-notifications");
driver = new FirefoxDriver(Options);
WebDriver driver = new FirefoxDriver(Options);
driver.manage().window().maximize();
driver.manage().deleteAllCookies();
driver.manage().timeouts().implicitlyWait(60, TimeUnit.SECONDS);
driver.navigate().to(WebsiteUrl);
return driver;}
public static WebDriver setUpIE(){
System.setProperty("webdriver.ie.driver", "C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\Selenium Softwares\\IEDriverServer_x64_3.4.0\\IEDriverServer.exe");
DesiredCapabilities cap = DesiredCapabilities.internetExplorer();
cap.setCapability("nativeEvents", false);
cap.setCapability("unexpectedAlertBehaviour", "accept");
cap.setCapability("ignoreProtectedModeSettings", true);
cap.setCapability("disable-popup-blocking", true);
cap.setCapability("enablePersistentHover", true);
cap.setCapability("ignoreZoomSetting", true);
cap.setCapability(InternetExplorerDriver.INTRODUCE_FLAKINESS_BY_IGNORING_SECURITY_DOMAINS,true);
InternetExplorerOptions options = new InternetExplorerOptions();
options.merge(cap);
WebDriver driver = new InternetExplorerDriver(options);
driver.manage().window().maximize();
driver.manage().deleteAllCookies();
driver.manage().timeouts().pageLoadTimeout(300, TimeUnit.SECONDS);
driver.manage().timeouts().implicitlyWait(60, TimeUnit.SECONDS);
driver.navigate().to(WebsiteUrl);
return driver;}}
Sending Data Through Excel:
package AxisBank;
import java.io.File;
import java.io.FileInputStream;
import org.apache.poi.xssf.usermodel.XSSFCell;
import org.apache.poi.xssf.usermodel.XSSFRow;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class ExcelUtils {
public static String getCellValue(String sheetName, int rowNum, int colNum) {
String CellValue = null;
try{
File file = new File("C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\SeleniumSbaProject\\Selenium Excels\\ExcelInput.xlsx");
FileInputStream source = new FileInputStream(file);
XSSFWorkbook workbook = new XSSFWorkbook(source);
XSSFSheet sheet = workbook.getSheet(sheetName);
XSSFRow row = sheet.getRow(rowNum);
XSSFCell cell = row.getCell(colNum);

CellValue = cell.getStringCellValue();
workbook.close();}
catch (Exception e){
e.printStackTrace();
}return CellValue;}}
Sending Data to Excel / Saving data in Excel:
package AxisBank;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import org.apache.poi.ss.usermodel.CellType;
import org.apache.poi.xssf.usermodel.XSSFCell;
import org.apache.poi.xssf.usermodel.XSSFRow;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class ExcelUtilsImport {
public static String getCellValue(String sheetName, int rowNum, int colNum , String Name) {
try{
File file = new File("C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\SeleniumSbaProject\\Selenium Excels\\ExcelOutput.xlsx");
FileInputStream source = new FileInputStream(file);
XSSFWorkbook workbook = new XSSFWorkbook(source);
XSSFSheet sheet = workbook.getSheet(sheetName);
XSSFRow row = sheet.createRow(rowNum);
XSSFCell cell = row.createCell(colNum);
cell.setCellType(CellType.STRING);
cell.setCellValue(Name);
FileOutputStream Final1 = new FileOutputStream("C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\SeleniumSbaProject\\Selenium Excels\\ExcelOutput.xlsx");
workbook.write(Final1);
Final1.close();
workbook.close();}
catch (Exception e){
e.printStackTrace();}
return Name;}}
PageObjectModel:
package AxisBank;
import org.openqa.selenium.By;
public class PageObjectModel extends DriverSetUp {
static By TypeofCustmor = By.xpath("//label[@class='flRight' and text() = 'Senior Citizen']");
static By TypeofFixedDeposit = By.id("FdepType");
static By AmountDeposit = By.name("mnthsavings");
static By RandomClick = By.xpath("/html/body/div[2]/div[3]/div[3]/div[2]");
static By RateofInterest = By.xpath("//div//span[@class='idRate pull-right' and @id='matIntRate' ]");
}
Application Flow:
package AxisBank;
import java.io.File;
import java.io.IOException;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
public class Application extends PageObjectModel {
public static void code(){
driver.findElement(TypeofCustmor).click();
File Shot1 = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
try {
FileUtils.copyFile(Shot1,new File( "C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\SeleniumSbaProject\\Selenium Shots\\Shot1.png"));
} catch (IOException e) {
// TODO Auto-generated catch block
e.printStackTrace();
}
Select Td = new Select (driver.findElement(TypeofFixedDeposit));
Td.selectByVisibleText("Monthly Payout");
File Shot2 = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
try {
FileUtils.copyFile(Shot2,new File( "C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\SeleniumSbaProject\\Selenium Shots\\Shot2.png"));
} catch (IOException e) {
// TODO Auto-generated catch block
e.printStackTrace();
}
JavascriptExecutor js = (JavascriptExecutor)driver;
js.executeScript("window.scrollBy(0,250)");
try {
Thread.sleep(3000);
} catch (InterruptedException e1) {
// TODO Auto-generated catch block
e1.printStackTrace();
}
WebElement Ad = driver.findElement(AmountDeposit);
Ad.click();
Ad.clear();
Ad.sendKeys(ExcelUtils.getCellValue("Excel", 0, 0));
driver.findElement(RandomClick).click();
File Shot3 = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
try {
FileUtils.copyFile(Shot3,new File( "C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\SeleniumSbaProject\\Selenium Shots\\Shot3.png"));
} catch (IOException e) {
// TODO Auto-generated catch block
e.printStackTrace();
}
String RoI = driver.findElement(RateofInterest).getText();
System.out.println(RoI);
ExcelUtilsImport.getCellValue("Excel", 0, 0, RoI);
File Shot4 = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
try {
FileUtils.copyFile(Shot4,new File( "C:\\Users\\748107\\Desktop\\ATS Rajasekhar\\SeleniumSbaProject\\Selenium Shots\\Shot4.png"));
} catch (IOException e) {
// TODO Auto-generated catch block
e.printStackTrace();
}
driver.close();}}
TestNg Class:
package AxisBank;
import org.testng.annotations.Test;
public class Runner extends DriverSetUp {
@Test (priority =0)
public void runChrome(){
driver = setUpChrome();
Application.code();
}
@Test (priority = 1)
public void runFirefox(){
driver = setUpFirefox();
Application.code();
}@Test (priority = 2)
public void runIE(){
driver = setUpIE();
Application.code();
}}
Customer reg:
package com.selenium.setup;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.util.Properties;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.firefox.FirefoxDriver;
public class DriverSetup {
public static WebDriver driver=null;
public static String baseUrl = "http://apps.qa2qe.cognizant.e-box.co.in/CustomerRegistration/";
public WebDriver getDriver() {
System.setProperty("webdriver.chrome.driver", "C:\\Users\\769175\\eclipse-workspace\\MyCcumber\\Driver\\chromedriver.exe");
driver = new ChromeDriver();
// driver =new FirefoxDriver();
driver.navigate().to(DriverSetup.baseUrl);
return driver;}}
package com.selenium.setup;
import java.io.FileInputStream;
import java.io.IOException;
import org.apache.poi.EncryptedDocumentException;
import org.apache.poi.openxml4j.exceptions.InvalidFormatException;
import org.apache.poi.ss.usermodel.Sheet;
import org.apache.poi.ss.usermodel.Workbook;
import org.apache.poi.ss.usermodel.WorkbookFactory;
public class ExcelUtils {
public static Workbook ExcelwBook;
public static Sheet Excelwsheet;
private static FileInputStream excelFile;
private static String filepath;
public static Object[][] readExcelData(String sheetName ) throws Exception {
object[] [] arrayExcelData = null;
string workingDir = System.getProperty(“user.dir”);
filepath = workingDir+File.separator+”src”+File.separator+”customer_registration.xlsx”;
excelFile = new FileInputStream(filepath);
ExcelWBook = WrokbookFactory.create(excelFile);
ExcelWSheet = ExcelWBook.getSheet(SheetName);
arrayExcelData = new object[ExcelWsheet.getLastRowNum()][ExcelWSheet.getRow(0).getLastCellNum()];
for (int i=0; i<=ExcelWSheet.getLastRowNum()-1;i++)
{ for(int j=0; j<ExcelWsheet.getRow(i).getLastCellNum();j++)
{ arrayExcelData[i][j[]= ExcelWsheet.getRow(i+1).getCell(j).toString(); }
return arrayExcelData;} }
package com.selenium.pages;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.PageFactory;
import com.selenium.setup.DriverSetup;
public class CustomerForm {
// fill the code
public CustomerForm()
{
// this.driver=driver;
PageFactory.initElements(DriverSetup.driver, this);
}
@FindBy(name="cname")
WebElement setCustomerName;
@FindBy(name="age")
WebElement setAge;
@FindBy(name="address")
WebElement setAddress;
@FindBy(name="phonenumber")
WebElement setPhoneNumber;
@FindBy(name="email")
WebElement setEmail;

@FindBy(id="submit")
WebElement submitClick;
@FindBy(id="message")
WebElement message;
public void setCustomerName(String cName)
{
setCustomerName.sendKeys(cName);
}
public void setAge(String age)
{
setAge.sendKeys(age);
}
public void setAddress(String address)
{
setAddress.sendKeys(address);
}
public void setPhoneNumber(String phoneNumber)
{
setPhoneNumber.sendKeys(phoneNumber);
}
public void setEmail(String email)
{
setEmail.sendKeys(email);
}
public void submitForm()
{
submitClick.click();
}
public String getErrorMessage()
{
return message.getText();
}}

package com.selenium.pages;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.PageFactory;
import com.selenium.setup.DriverSetup;

public class DisplayCustomer {
public DisplayCustomer(){
PageFactory.initElements(DriverSetup.driver, this);
}@FindBy(xpath = "/html/body/h2")
WebElement tittle;
@FindBy(xpath = "/html/body/table/tbody/tr[1]/td[2]")
WebElement name;
@FindBy(xpath = "/html/body/table/tbody/tr[2]/td[2]")
WebElement age;
@FindBy(xpath = "/html/body/table/tbody/tr[5]/td[2]")
WebElement email;
@FindBy(xpath = "/html/body/table/tbody/tr[3]/td[2]")
WebElement address;
@FindBy(xpath = "/html/body/table/tbody/tr[4]/td[2]")
WebElement phoneNumber;
public String getTitle(){
return tittle.getText();}
public String getName(){
return name.getText();}
public String getAge(){
return age.getText();}
public String getEmail(){
return email.getText();}
public String getAddress(){
return address.getText();}
public String getPhoneNumber(){
return phoneNumber.getText();}}
package com.selenium.tests;
import org.openqa.selenium.WebDriver;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.DataProvider;
import org.testng.annotations.Test;
import com.selenium.pages.CustomerForm;
import com.selenium.setup.DriverSetup;
import com.selenium.setup.ExcelUtils;
public class TestCustomerForm extends DriverSetup {
WebDriver driver;
CustomerForm customerForm;
static public String blankErrtxt;
@BeforeClass
// fill the code
public void setUp() {
driver = getDriver();
customerForm =new CustomerForm();}
@Test(dataProvider="customerInvalid")
public void testInvalidCustomerDetails(String Validation,String customerName, String age,String address,String phoneNumber,String email) throws Exception{
try{
// fill the code
customerForm.setCustomerName(customerName);
customerForm.setAge(age);
customerForm.setAddress(address);
customerForm.setPhoneNumber(phoneNumber);
customerForm.setEmail(email);
customerForm.submitForm();
blankErrtxt = customerForm.getErrorMessage();
if (blankErrtxt.contains("phoneNumber cannot be blank")){
System.out.println("Passed");
}else
System.out.println("Failed");}
catch (Exception e) {
e.printStackTrace();
}}
@DataProvider(name="customerInvalid")
public Object[][] getExcelData() throws Exception {
// fill the code
Object data[][] = ExcelUtils.getDataFromExcel("C:\\Users\\769175\\eclipse-workspace\\Customer\\customer_registration.xlsx","customer_invalid");
// System.out.println(data[1][1] );
return data;}
@AfterClass
public void closeBrowser(){
driver.close();
}}
package com.selenium.tests;
import org.openqa.selenium.WebDriver;
import org.testng.Assert;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.DataProvider;
import org.testng.annotations.Test;
import com.selenium.pages.CustomerForm;
import com.selenium.pages.DisplayCustomer;
import com.selenium.setup.DriverSetup;
import com.selenium.setup.ExcelUtils;
public class TestDisplayCustomer extends DriverSetup {
WebDriver driver;
DisplayCustomer displayCustomer;
CustomerForm customerForm;
public static String titletxt;
public static String customerNametxt;
public static String agetxt;
public static String addresstxt;
public static String numbertxt;
public static String emailtxt;
@BeforeClass
// fill the code
public void setUp() {
driver = getDriver();
displayCustomer= new DisplayCustomer();
customerForm = new CustomerForm();
}
@Test(dataProvider ="customervalid")
// fill the code
public void testValidCustomerDetails(String Validation, String customerName, String age,String address,String phoneNumber,String email) {
// fill the code
customerForm.setCustomerName(customerName);
customerForm.setAge(age);
customerForm.setAddress(address);
customerForm.setPhoneNumber(phoneNumber);
customerForm.setEmail(email);
customerForm.submitForm();
titletxt=displayCustomer.getTitle();
customerNametxt=displayCustomer.getName();
agetxt=displayCustomer.getAge();
addresstxt=displayCustomer.getAddress();
numbertxt=displayCustomer.getPhoneNumber();
emailtxt=displayCustomer.getEmail();
try {
Assert.assertEquals(titletxt, "Registered Succesfully");
Assert.assertEquals(customerNametxt, customerName+" "+age);
Assert.assertEquals(agetxt, age);
Assert.assertEquals(addresstxt, address);
Assert.assertEquals(numbertxt, phoneNumber);
Assert.assertEquals(emailtxt, email);
} catch (Exception e) {
// TODO Auto-generated catch block
e.printStackTrace();}}
@DataProvider(name ="customervalid")
public Object[][] getExcelData() throws Exception {
// fill the code
Object data[][] = ExcelUtils.getDataFromExcel("C:\\Users\\769175\\eclipse-workspace\\Customer\\customer_registration.xlsx","customer_valid" );
return data;}
@AfterClass
public void closeBrowser(){
driver.close();}}
Clear trip:
package exam;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class driversteup {
WebDriver driver;
public static WebDriver setup1()
{System.setProperty("webdriver.chrome.driver","C:\\New folder\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().window().maximize();
driver.get("https://www.cleartrip.com/");
return driver; } }
package exam;
import java.io.FileInputStream;
import java.io.IOException;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;

public class excel {
public static String getvalue() throws IOException
{FileInputStream f = new FileInputStream("C:\\Users\\770676\\Downloads\\trail seli\\Book2");
XSSFWorkbook wb = new XSSFWorkbook(f);
XSSFSheet sh = wb.getSheet("sheet1");
String value = sh.getRow(0).getCell(0).getStringCellValue();
// wb.close();
return value;}
}package exam;
public class xpath {
public static String oneway="//input[@id='OneWay']";
public static String From="//input[@id='FromTag']";
public static String To="//input[@id='ToTag']";
public static String date="//input[@id='DepartDate']";
public static String adults="//*[@id='Adults']/option[4]";
public static String child ="//*[@id='Childrens']/option[1]";
public static String infants ="//*[@id='Infants']/option[2]";
public static String search ="//*[@id='SearchBtn']";
}
package exam;
import org.testng.annotations.Test;
import org.testng.annotations.BeforeTest;
import java.io.File;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.testng.annotations.AfterTest;
public class codee {
public static WebDriver driver;
@Test
public void f() throws Exception
{
driver.findElement(By.xpath(xpath.oneway)).click();
driver.findElement(By.xpath(xpath.From)).sendKeys("Chennai, IN - Chennai Airport (MAA)");
driver.findElement(By.xpath(xpath.To)).sendKeys("Hyderabad, IN - Rajiv Gandhi International (HYD)");
driver.findElement(By.xpath(xpath.date)).sendKeys("01/01/2020");
//driver.findElement(By.xpath(xpath.dm)).click();
driver.findElement(By.xpath(xpath.adults)).click();
driver.findElement(By.xpath(xpath.child)).click();
driver.findElement(By.xpath(xpath.infants)).click();
Thread.sleep(6000);
driver.findElement(By.xpath(xpath.search)).click();
Thread.sleep(6000);
File s=((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(s, new File("C:\\Users\\770676\\Downloads\\trail seli\\screenshot.jpg"));
Thread.sleep(6000);
}
@BeforeTest
public void beforeTest(){
driver = driversteup.setup1();
}
@AfterTest
public void afterTest(){
driver.quit();
}
}
AXIS BANK:
package axis;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class driversetup {
WebDriver driver;
public static WebDriver setup1()
{
System.setProperty("webdriver.chrome.driver","C:\\New folder\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().window().maximize();
driver.get("https://www.axisbank.com/personal/calculators/fd-monthly-investment-calculator");
return driver;}
}
package axis;
import org.testng.annotations.Test;
import axis.driversetup;
import org.testng.annotations.BeforeTest;
import java.io.File;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
public class code {
public static WebDriver driver;
@Test
public void f() throws Exception {
Thread.sleep(3000);
driver.findElement(By.xpath("//select[@id='ddlCalc']/following-sibling::div/a[1]")).click();
Thread.sleep(3000);
driver.findElement(By.xpath("//a[text()='Monthly Investment']")).click();
Thread.sleep(3000);
String amount = "30000";
driver.findElement(By.xpath("//*[@class='form-control txtAmount']")).click();
WebElement amountField = driver.findElement(By.xpath("//*[@class='form-control txtAmount']"));
//amountField.clear();
//amountField.sendKeys(amount);
JavascriptExecutor js = (JavascriptExecutor)driver;
js.executeScript("arguments[0].value = '';", amountField);
js.executeScript("arguments[0].value = '"+amount+"';", amountField);
Thread.sleep(3000);
Strings=driver.findElement(By.xpath("//*[@id='ctl00_Body_C002_lblDisplayRate']")).getText();
System.out.println(s);
Thread.sleep(2000);
driver.findElement(By.xpath("//a[@id='ctl00_Body_C002_btnCal']")).click();
Thread.sleep(2000);
String c=driver.findElement(By.xpath("//span[@class='maturity_amt grossTotal']")).getText();
System.out.println(c);
File t=((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(t, new File("C:\\Users\\770676\\Downloads\\trail seli\\axisbankpic.jpg"));
Thread.sleep(6000);
}
@BeforeTest
public void beforeTest() {
driver = driversetup.setup1();
}
@AfterTest
public void afterTest() {
driver.quit(); }}
INDIGO:
INDIGO: ‘from’ location is going after adult enter
import org.testng.annotations.Test;
import as.driversetup;
import as.excel;
import org.testng.annotations.BeforeTest;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
public class codeindigo {
WebDriver driver;
@Test
public void f() throws Exception {
driver.findElement(By.xpath("//label[@for='oneWayTrip']")).click();
driver.findElement(By.xpath("//input[@name='or-src']"));
WebElement el= driver.findElement(By.xpath("//input[@name='or-src']"));
Thread.sleep(2000);
JavascriptExecutor js=(JavascriptExecutor) driver;
js.executeScript("arguments[0].value='Hyderabad (HYD)'",el);
driver.findElement(By.xpath("//input[@name='or-dest']"));
WebElement el1= driver.findElement(By.xpath("//input[@name='or-dest']"));
Thread.sleep(2000);
JavascriptExecutor js1=(JavascriptExecutor) driver;
js1.executeScript("arguments[0].value='Mumbai (BOM)'",el1);
Thread.sleep(3000);
String s ="12/12/2019";
driver.findElement(By.xpath("(//*[@name='or-depart'])"));
WebElement cal= driver.findElement(By.xpath("(//*[@name='or-depart'])"));
JavascriptExecutor j1=(JavascriptExecutor) driver;
j1.executeScript("arguments[0].value='"+s+"'",cal);
Thread.sleep(3000);
/* To click on passengers */
driver.findElement(By.xpath("//input[@placeholder='pax-class']")).click();
//to add the adults
Thread.sleep(4000);
driver.findElement(By.xpath("//*[@class='counter adult-pax']")).click();
driver.findElement(By.xpath("(//button[@class='pax-plus btn btn-info'])[1]")).click();
driver.findElement(By.xpath("(//button[@class='pax-plus btn btn-info'])[1]")).click();
//to add child
driver.findElement(By.xpath("(//input[@class='counter child-pax'])[1]")).click();
driver.findElement(By.xpath("(//button[@class='pax-plus btn btn-info'])[2]")).click();
//to add infants
//driver.findElement(By.xpath("(//input[@class='counter infant-pax'])[1]")).click();
driver.findElement(By.xpath("(//button[@class='btn btn-info pax-plus'])[1]")).click();
}
@BeforeTest
public void beforeTest() {
driver=driversetup.setup();
}
@AfterTest
public void afterTest() {
//driver.quit();}
}
ICICI:
package icici;
import org.testng.annotations.Test;
import icici.driversetp;
import org.testng.annotations.BeforeTest;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterTest;
public class icicicode {
public static WebDriver driver;
@Test
public void f() throws Exception {
driver.switchTo().frame("paymframe");
Thread.sleep(1000);
WebElement el =driver.findElement(By.xpath("//select[@id='ddlTypeOfFixedDeposit']"));
Select se =new Select(el);
se.selectByVisibleText("Quarterly Payout");
Thread.sleep(2000);
WebElement el1 = driver.findElement(By.xpath("//*[@id='loanAmount']"));
el1.clear();
el1.sendKeys("60,000");
String m = driver.findElement(By.xpath("//span[@id='spnMaturityValue']")).getText();
System.out.println("Maturity Amount="+m);
String ai = driver.findElement(By.xpath("//span[@id='spnAIAmount']")).getText();
System.out.println("Aggregate Interest Amount="+ai);
driver.findElement(By.xpath("//input[@id='idDays']")).click();
WebElement days = driver.findElement(By.xpath("//input[@id='tenureDay']"));
days.clear();
days.sendKeys("1000");
Thread.sleep(2000);
String m1 = driver.findElement(By.xpath("//span[@id='spnMaturityValue']")).getText();
System.out.println("For 1000 days Maturity Amount="+m1);
Thread.sleep(3000);
String ai1 = driver.findElement(By.xpath("//*[@id='spnAIAmount']")).getText();
System.out.println("For 1000 days Aggregate Interest Amount="+ai1);
Thread.sleep(2000);
driver.navigate().to("https://www.icicibank.com/calculator/fd-calculator.page");
//driver.switchTo().parentFrame();
//driver.findElement(By.xpath("//*[@id='main']/div[1]/div[2]/a")).click();}
@BeforeTest
public void beforeTest() {
driver = driversetp.setup();
}@AfterTest
public void afterTest() {
driver.quit();}}
91_MOBILE:
import org.testng.annotations.Test;
import mobile.driversetup1;
import org.testng.annotations.BeforeTest;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
public class mobcode {
public static WebDriver driver;
@Test
public void f() throws Exception {
WebElement el= driver.findElement(By.xpath("//input[@class='tiker_input mini_finder_input_1']"));
el.clear();
el.sendKeys("5000");
WebElement el1= driver.findElement(By.xpath("//input[@class='tiker_input mini_finder_input_2']"));
el1.clear();
el1.sendKeys("10000");
driver.findElement(By.xpath("//div[@class='view_details_btn find_mob mini_finder_btn enabled']")).click();
driver.findElement(By.xpath("//div[@id='price_box']")).click();
Thread.sleep(2000);
String s = driver.findElement(By.xpath("//a[@title='Spice Stellar 439']")).getText();
System.out.println("mobile name="+s);
String p = driver.findElement(By.xpath("//span[@class='price price_padding']")).getText();
System.out.println("Price of the mobile="+p);
Thread.sleep(2000);
driver.findElement(By.xpath("//div[@id='price_box']")).click();
Thread.sleep(2000);
String s1 = driver.findElement(By.xpath("//a[@title='Lava Z40']")).getText();
System.out.println("mobile name="+s1);
Thread.sleep(2000);
String p1 = driver.findElement(By.xpath("//span[@class='price price_padding']")).getText();
System.out.println("Price of the mobile="+p1);
Thread.sleep(2000);
driver.findElement(By.xpath("(//img[@src='//www.91-img.com/images/logo.gif'])[1]")).click();
}
@BeforeTest
public void beforeTest() {
driver = driversetup1.setup1();
}
@AfterTest
public void afterTest() {
// driver.quit();
}
}
SAVARI:
package savaari;
import org.testng.annotations.Test;
import org.testng.annotations.BeforeTest;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
public class scode {
public static WebDriver driver;
@Test
public void f() throws Exception {
driver.findElement(By.xpath("//label[@for='out_radio']")).click();
WebElement el =driver.findElement(By.xpath("//input[@id='fromCityList']"));
el.sendKeys("Hyderabad, Telangana");
el.sendKeys(Keys.ENTER);
el.sendKeys(Keys.DOWN);
Thread.sleep(2000);
WebElement et =driver.findElement(By.xpath("//*[@class='form-control ng-dirty ng-touched ng-invalid']"));
et.sendKeys("Bangalore, Karnataka");
et.sendKeys(Keys.ENTER);
el.sendKeys(Keys.DOWN);
Thread.sleep(2000);
//for from date
driver.findElement(By.xpath("//*[@inputstyleclass='form-control']/span[@class='ng-tns-c11-1 ui-calendar']")).click();
driver.findElement(By.xpath("//*[@id='approot']/mat-sidenav-container/mat-sidenav-content/app-home/div[1]/div[2]/div[2]/app-outstation/div/form/div[3]/div[1]/div/p-calendar[1]/span/div/table/tbody/tr[5]/td[3]/a")).click();
//for return date
driver.findElement(By.xpath("//div[@class='input returnDatePick']")).click();
driver.findElement(By.xpath("//*[@id='approot']/mat-sidenav-container/mat-sidenav-content/app-home/div[1]/div[2]/div[2]/app-outstation/div/form/div[3]/div[3]/div/p-calendar[1]/span/div/table/tbody/tr[5]/td[6]/a")).click();
//for time
driver.findElement(By.xpath("//select[@id='pickUpTime']")).sendKeys("1:45");
Thread.sleep(2000);
driver.findElement(By.xpath("//button[@class='book-button btn']")).click();
}
@BeforeTest
public void beforeTest() {
driver = driversetup.setup();}
@AfterTest
public void afterTest() {
//driver.quit();
}}
MARSHELL PET ZONE WITH EXCEL O/P
package sai;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.ie.InternetExplorerDriver;
public class driversetup {
WebDriver driver;
/* Driver setup for ChromeDriver */
public static WebDriver setup1(){
ChromeOptions options = new ChromeOptions();
options.addArguments("--disable-notifications");
System.setProperty("webdriver.chrome.driver","C:\\New folder\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.get("https://www.marshallspetzone.com/");
driver.manage().window().maximize();
return driver;
}
/* Driver setup for InternetExplorer */
public static WebDriver setup2(){
System.setProperty("webdriver.ie.driver", "");
WebDriver driver = new InternetExplorerDriver();
driver.get("https://www.marshallspetzone.com/");
driver.manage().window().maximize();
return driver;}
}
EXCEL:
package sai;
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class excel {
public static String value1;
public static String value2;
public static String value3;
public static String getvalue1() throws IOException{
FileInputStream fi = new FileInputStream("");
XSSFWorkbook wb = new XSSFWorkbook(fi);
XSSFSheet sh = wb.getSheet("sheet1");
sh.getRow(0).getCell(0).getStringCellValue();
return value1;}
public static String getvalue2() throws IOException{
FileInputStream fi = new FileInputStream("");
XSSFWorkbook wb = new XSSFWorkbook(fi);
XSSFSheet sh = wb.getSheet("sheet1");
sh.getRow(0).getCell(1).getStringCellValue();
return value2;}
public static String getvalue3(String w) throws IOException{
File f = new File("C:\\Users\\770676\\Desktop\\sai1.xlsx");
FileInputStream fi = new FileInputStream(f);
XSSFWorkbook wb = new XSSFWorkbook(fi);
XSSFSheet sh = wb.getSheet("sheet1");
sh.createRow(0).createCell(2).setCellValue(w);
FileOutputStream fos = new FileOutputStream(f);
wb.write(fos);
return value3;}
}
NEW PROJECT:
package sai;
import org.testng.annotations.Test;
import org.testng.annotations.BeforeTest;
import java.io.File;
import java.io.IOException;
import java.util.List;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
public class NewTest {
WebDriver driver;
@Test
public void f() throws InterruptedException, IOException {
/* To Select a category - "Bird" */
driver.findElement(By.xpath("//li[@id='cbp-hrmenu-tab-14']")).click();
Thread.sleep(3000);
/* To Select SubCategory as FOOD */
driver.findElement(By.xpath("//*[@id='left-column']/div[1]/div/ul/li[3]/a")).click();
/* To find the products in STOCK */
WebElement el = driver.findElement(By.xpath("//a[contains(text(),'In stock')]"));
el.click();
Thread.sleep(5000);
/*To print the Product Name */
String sort= driver.findElement(By.xpath("//h3[@class='h3 product-title']")).getText();
// System.out.println("Productname="+a1);
List <WebElement> sort8= driver.findElements(By.xpath("//h3[@class='h3 product-title']"));
System.out.println(sort8.get(0).getText());
excel.getvalue3(sort);
List <WebElement> price= driver.findElements(By.xpath("//span[@class='product-price']"));
System.out.println(price.get(0).getText());
Thread.sleep(3000);
driver.findElement(By.xpath("//*[@id='js-product-list']/div/div[1]/article/div[2]/h3/a")).click();
driver.findElement(By.xpath("//div[@class='add']")).click();
Thread.sleep(3000);
driver.findElement(By.xpath("//button[@class='btn btn-secondary btn-block']")).click();
Thread.sleep(3000);
driver.findElement(By.xpath("//a[@title='Next product']")).click();
Thread.sleep(3000);
String s1= driver.findElement(By.xpath("//h1[@class='h1 page-title']")).getText();
System.out.println("Productname="+s1);
File t = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
FileUtils.copyFile(t,new File("C:\\Users\\770676\\Downloads\\trail seli\\mpz.jpg"));
}
@BeforeTest
public void beforeTest() {
driver=driversetup.setup1();
}

@AfterTest
public void afterTest() {
// driver.quit();
}}
PEDIGREE CODE:
package pedigree;
import org.testng.annotations.Test;
import org.testng.annotations.BeforeTest;
import java.util.ArrayList;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.testng.annotations.AfterTest;
public class pedigreecode {
WebDriver driver;
@Test
public void f() throws Exception {
driver.findElement(By.xpath("//div[@class='search-box']")).click();
driver.findElement(By.xpath("//*[@id='form1']/section[3]/div/div/div[2]/span[1]/a")).click();
Thread.sleep(3000);
driver.findElement(By.xpath("//*[@id='form1']/section[4]/div/div/div[2]/ul/li")).click();
Thread.sleep(3000);
/* TO switch to main window */
ArrayList<String> wind = new ArrayList<String> (driver.getWindowHandles());
driver.switchTo().window(wind.get(0));
/* use either array method r below method */
// String winHandleBefore;
// winHandleBefore = driver.getWindowHandle();
// driver.switchTo().window(winHandleBefore);
/* to click on logo in pedigree page */
driver.findElement(By.xpath("//img[@id='Header_imgLogo']")).click();
}
@BeforeTest
public void beforeTest() {
driver=driversetup.setup();
}
@AfterTest
public void afterTest() {
//driver.quit();
}}
MAKE MY TRIP:

import org.testng.annotations.Test;
import as.driversetup;
import as.excel;
import org.testng.annotations.BeforeTest;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
public class makecode {
WebDriver driver;
@Test
public void f() throws Exception {
Thread.sleep(3000);
/* WebElement el= driver.findElement(By.xpath("//input[@id='fromCity']"));
el.sendKeys(excel.getvalue1());
Thread.sleep(3000);
driver.findElement(By.xpath("(//div[@class='calc60'])[1]")).click();
el.sendKeys(Keys.DOWN);
//el.sendKeys(Keys.ENTER);
Thread.sleep(2000);
WebElement el1=driver.findElement(By.xpath("//input[@id='toCity']"));
Thread.sleep(3000);
JavascriptExecutor js =(JavascriptExecutor)driver;
Thread.sleep(3000);
js.executeScript("arguments[0].value='BKK, Suvarnabhumi Airport Thailand';", el1);
el1.sendKeys(Keys.DOWN); */
WebElement web = driver.findElement(By.xpath("//input[@id='fromCity']"));
web.sendKeys(excel.getvalue1());
Thread.sleep(2000);
driver.findElement(By.xpath("(//div[@class='calc60'])[1]")).click();
web.sendKeys(Keys.DOWN);
WebElement web1= driver.findElement(By.xpath("//input[@id='toCity']"));
web1.sendKeys(excel.getvalue2());
Thread.sleep(2000);
driver.findElement(By.xpath("(//div[@class='calc60'])[1]")).click();
web1.sendKeys(Keys.DOWN);
Thread.sleep(3000);
driver.findElement(By.xpath("(//span[@class='lbl_input latoBold appendBottom10'])[1]")).click();
driver.findElement(By.xpath("(//div[@class='DayPicker-Day'])[2]")).click();
Thread.sleep(3000);
driver.findElement(By.xpath("(//span[@class='lbl_input latoBold appendBottom10'])[3]")).click();
driver.findElement(By.xpath("(//ul[@class='guestCounter font12 darkText'])/li[3]")).click();
driver.findElement(By.xpath("//button[@class='primaryBtn btnApply pushRight ']")).click();
driver.findElement(By.xpath("//a[@class='primaryBtn font24 latoBlack widgetSearchBtn ']")).click();
}
@BeforeTest
public void beforeTest() {
driver=driversetup.setup();
}
@AfterTest
public void afterTest() {
// driver.quit();
}}
PETCO:
package petzone;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class driversetup {
WebDriver driver;
public static WebDriver setup(){
System.setProperty("webdriver.chrome.driver","C:\\New folder\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().window().maximize();
driver.get("https://www.petco.com");
return driver;}
}
package petzone;
public class xpath {
public static String pet="//li[@id='shop-by-pet']";
public static String dog="//a[@href='/shop/en/petcostore/category/dog'][1]";
public static String food="//p[@class='text-center text-dark']";
public static String sortby="//*[@id='product-listing-sort-by_4_3074457345618259661_4099276460824412685']/option[3]";
// public static String title="//*[@class='product-name']";
// public static String price="//div[@class='price-rd-line']";
public static String price="//span[@id='facetLabel_12095115111114116951121141059910195801011169911183116111114101958583685840123494832505312532505341']";
public static String sort="//*[@id='product-listing-sort-by_4_3074457345618259661_4099276460824412685']/option[5]";
public static String logo="//div[@class='logo']";
}
package petzone;
import org.testng.annotations.Test;
import org.testng.annotations.BeforeTest;
import java.util.List;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
public class pcode {
public static WebDriver driver;
@Test
public void f() throws Exception {
Thread.sleep(3000);
// thanks statement is needed only if pop-up comes
driver.findElement(By.xpath("//div[@id='thanks']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath(xpath.pet)).click();
Thread.sleep(3000);
driver.findElement(By.xpath(xpath.dog)).click();
driver.findElement(By.xpath(xpath.food)).click();
driver.findElement(By.xpath(xpath.sortby)).click();
List<WebElement> sort1= driver.findElements(By.xpath("//div[@class='product-name']/a"));
System.out.println(sort1.get(2).getText());
List<WebElement> sort2= driver.findElements(By.xpath("//div[@class='price-rd-line']"));
System.out.println(sort2.get(2).getText());
Thread.sleep(3000);
driver.findElement(By.xpath(xpath.price)).click();
Thread.sleep(3000);
driver.findElement(By.xpath(xpath.sort)).click();
driver.findElement(By.xpath(xpath.logo)).click();
driver.quit();
}
@BeforeTest
public void beforeTest() {
driver = driversetup.setup();
}
@AfterTest
public void afterTest() {
driver.quit();
}}
GO IBIBO_ CHECK:
***** Driver Setup *****
package validation;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class goibibo {
WebDriver driver;
public WebDriver getchromedriver()
{
System.setProperty("webdriver.chrome.driver","G:\\Selenium\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().deleteAllCookies();
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
driver.get("https://goibibo.com");
return driver;}
}
***** ExcelUtils *****
package validation;
import java.io.FileInputStream;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class ExcelUtils {
public static XSSFWorkbook workbook;
public static XSSFSheet xfsheet;
public static void setPath() throws Exception{
FileInputStream fi=new FileInputStream("G:\\search.xlsx");
workbook=new XSSFWorkbook(fi);
xfsheet=workbook.getSheet("Sheet1");
}
public static String cellvalue(int row,int col){
try {
String data1=xfsheet.getRow(row).getCell(col).getStringCellValue();
return data1;
}catch (Exception e){
e.printStackTrace();
return null;}}}
***** Xpath *****
package validation;
public class Xpath {
public static String trip="//*[@id='content']/div/div[2]/div/div[1]/div[2]/div[1]/div/span[2]";
public static String from="//*[@id='gosuggest_inputSrc']";
public static String destination="//*[@id='gosuggest_inputDest']";
public static String departure="//*[@placeholder='Departure']";
public static String ret="//*[@placeholder='Return']";
public static String search="//*[@id='gi_search_btn']";}
***** TestNG class *****
package validation;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;
public class Searching extends goibibo {
WebDriver driver;
@Test
public void testForGoibibo() throws Throwable {
driver.findElement(By.xpath(Xpath.trip)).click();
ExcelUtils.setPath();
String start=ExcelUtils.cellvalue(0,0);
System.out.println(start);
String desti=ExcelUtils.cellvalue(0,1);
System.out.println(desti);
WebElement we1 = driver.findElement(By.xpath(Xpath.from));
we1.sendKeys(start);
Thread.sleep(5000);
we1.sendKeys(Keys.ARROW_DOWN);
we1.sendKeys(Keys.ENTER);
WebElement we2 = driver.findElement(By.xpath(Xpath.destination));
we2.sendKeys(desti);
Thread.sleep(5000);
we2.sendKeys(Keys.ARROW_DOWN);
we2.sendKeys(Keys.ENTER);
WebElement we3 = driver.findElement(By.xpath(Xpath.departure));
we3.click();
Thread.sleep(5000);
driver.findElement(By.id("fare_20190408")).click();
WebElement we4 = driver.findElement(By.xpath(Xpath.ret));
we4.click();
Thread.sleep(5000);
driver.findElement(By.id("fare_20190411")).click();
driver.findElement(By.xpath(Xpath.search)).click();
Thread.sleep(20000);}
@BeforeClass
public void beforeClass() {
driver = getchromedriver();
}
@AfterClass
public void afterClass() {
driver.quit();
}}
GO IBIBO_SEARCH:
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class driversetup{
WebDriver driver;
public WebDriver setup(){
System.setProperty("webdriver.chrome.driver","C:\\Users\\Administrator\\Desktop\\chromedriver_win32\\chromedriver.exe);WebDriver driver = new ChromeDriver();
String url = "https://www.goibibo.com/";
driver.navigate().to(url);
driver.manage().window().maximize();
return driver;
}
public void quit(){
driver.quit();}}
ITEM_LIST:
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class driversetup{
WebDriver driver;
public WebDriver setup(){
System.setProperty("webdriver.chrome.driver","C:\\Users\\Administrator\\Desktop\\chromedriver_win32\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
String url = "https://www.goibibo.com/";
driver.navigate().to(url);
driver.manage().window().maximize();
return driver;}
public void quit(){
driver.quit();}}
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class excel{
public static String Value1;
public static String Value2;
public static String getvalue1() throws Exception{
FileInputStream fi = new FileInputStream("C:\\Users\\Administrator\\Desktop\\Excel\\TestData.xlsx");
XSSFWorkbook wb = new XSSFWorkbook(fi);
XSSFSheet sh = wb.getSheet("Sheet1");
Value1 = sh.getRow(0).getCell(0).getStringCellValue();
return Value1;}
public static String getvalue2() throws Exception{
FileInputStream fi = new FileInputStream("C:\\Users\\Administrator\\Desktop\\Excel\\TestData.xlsx");
XSSFWorkbook wb = new XSSFWorkbook(fi);
XSSFSheet sh = wb.getSheet("Sheet1");
Value2 = sh.getRow(0).getCell(1).getStringCellValue();
return Value2;}}
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
public class search extends driversetup{
@BeforeMethod
public void test1(){
driver = setup();
}
@Test(priority=1)
public void searching() throws Exception{
driver.findElement(By.xpath("//*[@id='gi_roundtrip_label']")).click();
WebElement we = driver.findElement(By.xpath("(//*[@id='gosuggest_inputSrc'])"));
we.sendKeys(excel.getvalue1());
Thread.sleep(2000);
we.sendKeys(Keys.DOWN);
we.sendKeys(Keys.ENTER);
WebElement wc= driver.findElement(By.xpath("(//*[@id='gosuggest_inputDest'])"));
wc.sendKeys(excel.getvalue2());
Thread.sleep(2000);
wc.sendKeys(Keys.DOWN);
wc.sendKeys(Keys.ENTER);
Thread.sleep(2000);
driver.findElement(By.xpath("(//input[@class='form-control inputTxtLarge widgetCalenderTxt'])[1]")).click();
driver.findElement(By.xpath("(//*[text()='15'])[1]")).click();
Thread.sleep(3000);
driver.findElement(By.xpath("(//input[@class='form-control inputTxtLarge widgetCalenderTxt'])[2]")).click();
driver.findElement(By.xpath("(//*[text()='18'])[1]")).click();
Thread.sleep(2000);
//Select sc = new Select(driver.findElement(By.xpath("//*[@id='Adults']")));
//sc.selectByIndex(4);
//Thread.sleep(2000);
driver.findElement(By.xpath("//button[@type='submit']")).click();
Thread.sleep(25000);}
@AfterMethod
public void exit(){
quit();
}}
MARSHALL_PETZONE_PRODUCT PRICE:
MARSHELLS PETZONE
import org.testng.annotations.Test;
import as.driversetup;
import as.excel;
import org.testng.annotations.BeforeTest;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Wait;
import org.testng.annotations.AfterTest;
public class asdf {
public static WebDriver driver;
@Test
public void f() throws Exception {
WebElement el = driver.findElement(By.xpath("(//a[@href='https://www.marshallspetzone.com/15-Bird'])/span[@class='cbp-tab-title']"));
el.click();
driver.findElement(By.xpath("//*[@id='left-column']/div[1]/div/ul/li[3]/a")).click();
String p = driver.findElement(By.xpath("//h3[@class='h3 product-title']")).getText();
System.out.println("productname="+p);
//String pcv =driver.findElement(By.xpath("//h3[@class='h3 product-title']")).sendKeys(excel.outputcount(pcv));
String cost = driver.findElement(By.xpath("//span[@class='product-price']")).getText();
System.out.println("product cost="+cost);
driver.findElement(By.xpath("//*[@id='js-product-list']/div/div[8]/article/div[1]/a/img")).click();
driver.findElement(By.xpath("//button[@class='btn btn-primary btn-lg add-to-cart']")).click();
Thread.sleep(4000);
driver.findElement(By.xpath("//*[@id='blockcart-modal']/div/div/div[2]/div/div[2]/div/div/button")).click();
Thread.sleep(3000);
driver.findElement(By.xpath("//*[@id='iqitproductsnav']/a[2]")).click();
String p1 = driver.findElement(By.xpath("//h1[@class='h1 page-title']")).getText();
System.out.println("productname="+p1);}
@BeforeTest
public void beforeTest() {
driver = driversetup.setup();
}@AfterTest
public void afterTest() {
//driver.quit();}}
MARSHALL_PETZONE_ACCOUNT_BUTTON:
package xlsetup;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class XLsetup {
public static String value1;
public static void getStringnameinexcel(String n,int row,int col) throws Exception{
FileInputStream fis = new FileInputStream("D:\\Selenium SBA\\marshall\\Mbook.xlsx");
XSSFWorkbook wb = new XSSFWorkbook(fis);
XSSFSheet sh = wb.getSheetAt(0);
sh.getRow(row).getCell(col).setCellValue(n);
FileOutputStream fos = new FileOutputStream("D:\\Selenium SBA\\marshall\\Mbook.xlsx");
wb.write(fos);
fos.close();}}
package path;
public class Paths {
public static String catbutton = "(//span[contains(@class,'cbp-tab-title')])[3]";
public static String accbutton = "(//div[contains(@class,'category-top-menu block-content')]//ul//a)[1]";
public static String dropdown = "((//div[contains(@class,'products-sort-nb-dropdown products-sort-order dropdown')])//a[1])[1]";
public static String droplist = "(//div[contains(@class,'dropdown-menu')])[2]//a[4]";
public static String firstname = "(//*[contains(@class,'h3 product-title')])[1]//a";
}
package driversetup;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class Driversetup {
public static WebDriver driver;
public static WebDriver chromesetup(){
System.setProperty("webdriver.chrome.driver", "chromedriver.exe");
WebDriver driver = new ChromeDriver();
return driver;
}}
package testng;
import org.testng.annotations.Test;
import path.Paths;
import org.testng.annotations.BeforeTest;
import java.io.File;
import java.io.IOException;
import java.util.concurrent.TimeUnit;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.AfterTest;
public class NewTest {
public static WebDriver d;
public static void Wait(){
d.manage().timeouts().implicitlyWait(3000, TimeUnit.MILLISECONDS);}
public static void Screenshot(String a) throws Exception{
File src = ((TakesScreenshot)d).getScreenshotAs(OutputType.FILE);
File dst = new File("screenshots/"+a+".png");
FileUtils.copyFile(src, dst);}
@Test
public void testscript() throws Exception {
d.findElement(By.xpath(Paths.catbutton)).click();
Wait();
d.findElement(By.xpath(Paths.accbutton)).click();
WebDriverWait wait = new WebDriverWait(d, 20);
WebElement element = d.findElement(By.xpath(Paths.dropdown));
wait.until(ExpectedConditions.visibilityOf(element));
d.findElement(By.xpath(Paths.dropdown)).click();
WebDriverWait wait1 = new WebDriverWait(d, 20);
WebElement element1 = d.findElement(By.xpath(Paths.droplist));
wait1.until(ExpectedConditions.visibilityOf(element1));
d.findElement(By.xpath(Paths.droplist)).click();
Wait();
String textname = d.findElement(By.xpath(Paths.firstname)).getText();
System.out.println(textname);
xlsetup.XLsetup.getStringnameinexcel(textname, 0, 1);
Wait();
d.findElement(By.xpath("//i[contains(@class,'fa fa-th-list')]")).click();
Wait();
Screenshot("cat");}
@BeforeTest
public void beforeTest() {
d = driversetup.Driversetup.chromesetup();
String url = "https://www.marshallspetzone.com/";
d.get(url);
d.manage().window().maximize();
d.manage().deleteAllCookies();
Wait();}
@AfterTest
public void afterTest() {
d.quit();
}}
...............................................................................................................................................
Cleartrip:
package Browsers;
import java.io.IOException;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;
import xpath.Login;;
public class Chromedr{
WebDriver driver;
@BeforeTest
public void url(){
System.setProperty("webdriver.chrome.driver", "C:\\Program Files\\seleniumJars\\drivers\\chromedriver_win32 (1)\\chromedriver.exe");
driver = new ChromeDriver();
driver.get("https://www.cleartrip.com");
//driver.manage().window().maximize();
}@Test
public void start() throws InterruptedException, IOException{
Login hm = PageFactory.initElements(driver, Login.class);
hm.roundtrip();
hm.fromDetials();
hm.toDetials();
hm.fromDate();
hm.toDate();
hm.dropDown();
hm.screenshot111();}}
********************************************************************************************************package Excel;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import org.apache.poi.ss.usermodel.Cell;
import org.apache.poi.ss.usermodel.DataFormatter;
import org.apache.poi.ss.usermodel.Row;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class Excel {
public static String ExcelEntry(int cellIndex) throws IOException
{
FileInputStream fileis = new FileInputStream("C:\\Users\\india\\eclipse-workspace\\cleartrips\\excel.xlsx");
XSSFWorkbook wk = new XSSFWorkbook(fileis);
XSSFSheet sheet = wk.getSheetAt(0);
Row row = sheet.getRow(0);
DataFormatter formatter = new DataFormatter();
Cell cell = row.getCell(cellIndex);
String excelData = formatter.formatCellValue(cell);
return excelData;}}
********************************************************************************************************
package xpath;
import java.io.IOException;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import java.io.File;
import java.io.IOException;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.ui.Select;
import Excel.Excel;
public class Login {
WebDriver driver;
public Login(WebDriver driver)
{
this.driver = driver;
}
@FindBy(xpath="//input[@id='RoundTrip']")
WebElement roundrip;
@FindBy(xpath="//input[@id='FromTag']")
WebElement from;
@FindBy(xpath="//input[@id='ToTag']")
WebElement to;
@FindBy(xpath="//input[@id='DepartDate']")
WebElement fromdate;
@FindBy(xpath="(//a[@class='ui-state-default '])[11]")
WebElement frompop;
@FindBy(xpath="(//a[@class='ui-state-default '])[21]")
WebElement topop;
public void roundtrip() throws InterruptedException
{
Thread.sleep(3000);
roundrip.click();
}
public void fromDetials() throws InterruptedException, IOException
{
Thread.sleep(3000);
from.sendKeys(Excel.ExcelEntry(0));
from.sendKeys(Keys.TAB);
}
public void toDetials() throws InterruptedException, IOException
{
Thread.sleep(3000);
to.sendKeys(Excel.ExcelEntry(1));
to.sendKeys(Keys.TAB);
}
public void fromDate() throws InterruptedException
{
Thread.sleep(3000);
//fromdate.click();
frompop.click();
}
public void toDate() throws InterruptedException
{
Thread.sleep(2000);
topop.click();
}
public void dropDown() throws InterruptedException
{
Thread.sleep(3000);
Select drop = new Select(driver.findElement(By.xpath("//select[@id='Adults']")));
drop.selectByVisibleText("7");
}
public void screenshot111() throws IOException
{
TakesScreenshot tc = ((TakesScreenshot) driver);
File sc = tc.getScreenshotAs(OutputType.FILE);
//File des = new File("./screenshots/screenshots.png");
File ds = new File("C:\\Users\\india\\eclipse-workspace\\cleartrips\\screenshot.png");
FileUtils.copyFile(sc, ds);
//FileUtils.copyFile(sc, des);
System.out.println("SCREENSHOT TAKEN");
}}
000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000
Gobibo:
package Browsers;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class chromebrowser {
WebDriver driver;
public WebDriver getchromedriver()
{
System.setProperty("webdriver.chrome.driver", "C:\\Program Files\\seleniumJars\\drivers\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().deleteAllCookies();
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
driver.get("https://goibibo.com");
return driver;
}}
********************************************************************************************************
package Excel;
import java.io.FileInputStream;
import java.io.IOException;
import org.apache.poi.ss.usermodel.Cell;
import org.apache.poi.ss.usermodel.DataFormatter;
import org.apache.poi.ss.usermodel.Row;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class Excel {
public static XSSFWorkbook workbook;
public static XSSFSheet xfsheet;
public static void setPath() throws Exception
{
FileInputStream fi=new FileInputStream("C:\\Users\\india\\eclipse-workspace\\cleartripsss\\sheet1.xlsx");
workbook=new XSSFWorkbook(fi);
xfsheet=workbook.getSheet("Sheet1");
}
public static String cellvalue(int row,int col){
try {
String data1=xfsheet.getRow(row).getCell(col).getStringCellValue();
return data1;
}
catch (Exception e){
e.printStackTrace();
return null;}}}
********************************************************************************************************package Pages;
public class xpath {
public static String trip="//*[@id='content']/div/div[2]/div/div[1]/div[2]/div[1]/div/span[2]";
public static String from="//*[@id='gosuggest_inputSrc']";
public static String destination="//*[@id='gosuggest_inputDest']";
public static String departure="//*[@placeholder='Departure']";
public static String ret="//*[@placeholder='Return']";
public static String search="//*[@id='gi_search_btn']";
}
********************************************************************************************************
package Test;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;
import Browsers.chromebrowser;
import Excel.Excel;
import Pages.xpath;
public class Searching extends chromebrowser {
WebDriver driver;
@BeforeClass
public void beforeClass() {
driver = getchromedriver();
}
@Test
public void testForGoibibo() throws Throwable {
driver.findElement(By.xpath(xpath.trip)).click();
Excel.setPath();
String start=Excel.cellvalue(0,0);
System.out.println(start);
String desti=Excel.cellvalue(0,1);
System.out.println(desti);
WebElement we1 = driver.findElement(By.xpath(xpath.from));
we1.sendKeys(start);
Thread.sleep(5000);
we1.sendKeys(Keys.ARROW_DOWN);
we1.sendKeys(Keys.ENTER);
WebElement we2 = driver.findElement(By.xpath(xpath.destination));
we2.sendKeys(desti);
Thread.sleep(5000);
we2.sendKeys(Keys.ARROW_DOWN);
we2.sendKeys(Keys.ENTER);
WebElement we3 = driver.findElement(By.xpath(xpath.departure));
we3.click();
Thread.sleep(5000);
driver.findElement(By.id("fare_20190826")).click();
WebElement we4 = driver.findElement(By.xpath(xpath.ret));
we4.click();
Thread.sleep(5000);
driver.findElement(By.id("fare_20190831")).click();
driver.findElement(By.xpath(xpath.search)).click();
Thread.sleep(20000);}}
88888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
Indigo:
public class indigo {
public static void main(String args[]) throws InterruptedException {
System.setProperty("webdriver.chrome.driver", "C:/Selenium/drivers/chromedriver.exe");
WebDriver driver=new ChromeDriver();
driver.manage().window().maximize();
driver.get("https://www.goindigo.in/"); //url
driver.findElement(By.xpath("//label[contains(text(),'One Way')]")).click(); //one way
//from
driver.findElement(By.xpath("//input[@name='or-src']")).sendKeys(Keys.chord(Keys.CONTROL, "a"));
driver.findElement(By.xpath("//input[@name='or-src']")).sendKeys("Kolkata (CCU)");
driver.findElement(By.xpath("//div[contains(@class,'autocomplete-result')]//div[@data-name='Kolkata']")).click();
//to
driver.findElement(By.xpath("//input[@name='or-dest']")).click();
driver.findElement(By.xpath("//input[@name='or-dest']")).sendKeys(Keys.chord(Keys.CONTROL, "a"));
driver.findElement(By.xpath("//input[@name='or-dest']")).sendKeys("Delhi (DEL)");
driver.findElement(By.xpath("(//div[contains(@class,'autocomplete-result')]//div[@data-name='Delhi'])[3]")).click();
//date
driver.findElement(By.xpath("//div[contains(@class,'ui-datepicker-inline')]/div[1]//tr[3]/td[2]")).click();
//passenger
driver.findElement(By.xpath("//input[@name='passenger']")).click();
driver.findElement(By.xpath("(//label[contains(text(),'Adult(s)')]/following-sibling::div//button[@title='Up'])[1]")).click();
//instead of done clicking the radio button again to close tat popup
driver.findElement(By.xpath("//label[contains(text(),'One Way')]")).click();
//searchbutton
driver.findElement(By.xpath("//button[contains(@class,'btn btn-primary block bold ig-search-btn ig-common-cta addLoader')]")).click();
Thread.sleep(5000);
driver.findElement(By.xpath("(//button[contains(text(),'Non-stop')])[1]")).click();
String flightNo=driver.findElement(By.xpath("(//span[@class='flightNo'])[1]")).getText();
System.out.println(flightNo);
driver.findElement(By.xpath("//a[@id='headerLogo']")).click();}}
********************************************************************************************************
package indigo;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class HomePage {
public static void main(String args[]) throws InterruptedException {
System.setProperty("webdriver.chrome.driver", "C:\\Program Files\\seleniumJars\\drivers\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver=new ChromeDriver();
driver.manage().window().maximize();
driver.get("https://www.goindigo.in/"); //url
driver.findElement(By.xpath("(//div[@class='d-inline-block new_radio-wrap'])[2]")).click(); //one way
//from
driver.findElement(By.xpath("//input[@name='or-src']")).sendKeys(Keys.chord(Keys.CONTROL, "a"));
driver.findElement(By.xpath("//input[@name='or-src']")).sendKeys("Kolkata (CCU)");
driver.findElement(By.xpath("//div[contains(@class,'autocomplete-result')]//div[@data-name='Kolkata']")).click();
//to
driver.findElement(By.xpath("//input[@name='or-dest']")).click();
driver.findElement(By.xpath("//input[@name='or-dest']")).sendKeys(Keys.chord(Keys.CONTROL, "a"));
driver.findElement(By.xpath("//input[@name='or-dest']")).sendKeys("Delhi (DEL)");
driver.findElement(By.xpath("(//div[contains(@class,'autocomplete-result')]//div[@data-name='Delhi'])[3]")).click();
//date
driver.findElement(By.xpath("(//a[@class='ui-state-default'])[10]")).click();
driver.findElement(By.xpath("//a[@class='ui-state-default ui-state-hover']")).click();
//passenger
driver.findElement(By.xpath("//input[@name='passenger']")).click();
driver.findElement(By.xpath("(//label[contains(text(),'Adult(s)')]/following-sibling::div//button[@title='Up'])[1]")).click();
instead of done clicking the radio button again to close tat popup
driver.findElement(By.xpath("//label[contains(text(),'One Way')]")).click();
searchbutton


driver.findElement(By.xpath("//button[contains(@class,'btn btn-primary block bold ig-search-btn ig-common-cta addLoader')]")).click();
Thread.sleep(5000);
//driver.findElement(By.xpath("(//button[contains(text(),'Non-stop')])[1]")).click();
String flightNo=driver.findElement(By.xpath("(//span[@class='flightNo'])[1]")).getText();
System.out.println(flightNo);
driver.findElement(By.xpath("//a[@id='headerLogo']")).click();}}
88888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
Redbus:
package driver;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import pages.Home;
public class Chromedriver {
WebDriver driver;
@Test
public void getMethod() throws InterruptedException
{
//Home h=new Home(driver);
Home h = PageFactory.initElements(driver, Home.class);
h.setFrom();
h.setTo();
h.onwarddate();
h.search1();
h.fareis();
h.busname();
}@BeforeMethod
public void getUrl() {
System.setProperty("webdriver.chrome.driver", "C:\\Users\\Swati Kumari\\Downloads\\chromedriver_win32 (1)\\chromedriver.exe");
driver=new ChromeDriver();
driver.get("https://www.redbus.in");
driver.manage().window().maximize();}
@AfterMethod
public void close(){
driver.quit();}}
……………………………………………………………………………………
package pages;
import org.apache.bcel.generic.GETSTATIC;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy
public class Home {
WebDriver driver;
public Home(WebDriver driver) {
// TODO Auto-generated constructor stub
this.driver=driver;
}
//click on from
@FindBy(xpath="//input[@id='src']")
WebElement from;
//select value from dropdownchennai
@FindBy(xpath="//ul[@class='autoFill']//li[text()=\"Chennai (All Locations)\"]")
WebElement dropdown;
//click on
@FindBy(xpath="//input[@id='dest']")
WebElement to;
//select value from dropdown
@FindBy(xpath="//li[text()='Bangalore (All Locations)']")
WebElement d2;
//select onwards date
@FindBy(xpath="//label[text()='Onward Date']")
WebElement onwardaate;
//Giving date
@FindBy(xpath="(//td[text()='30'])[2]")
WebElement date;
//selecting return date
@FindBy(xpath="//input[@id='return_cal']")
WebElement retu;
//finding search button
@FindBy(xpath="//*[@id='search_btn']")
WebElement search;
//finding fare
@FindBy(xpath="//a[text()='Fare']")
WebElement fare;
//teking highest fare bus
@FindBy(xpath="//div[@class='travels lh-24 f-bold d-color'][1]")
WebElement busname;
public void setFrom() throws InterruptedException{
Thread.sleep(10000);
from.click();
from.sendKeys("chennai");
Thread.sleep(5000);
dropdown.click();}
public void setTo() throws InterruptedException{
Thread.sleep(10000);
to.click();
to.sendKeys("bangalore");
Thread.sleep(5000);
d2.click();
}
public void onwarddate() throws InterruptedException{
Thread.sleep(10000);
onwardaate.click();
Thread.sleep(5000);
date.click();
Thread.sleep(5000);
}
public void returndate() throws InterruptedException{
Thread.sleep(1000);
retu.click();
}
public void search1(){
search.click();
}public void fareis() throws InterruptedException
{
Thread.sleep(10000);
fare.click();
}
public void busname() throws InterruptedException{
Thread.sleep(10000);
System.out.println(busname.getText());}}
8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
savaari:
package com.cognizant;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.ie.InternetExplorerDriver;
import org.testng.annotations.Test;
public class SampleClass{
WebDriver driver;
public WebDriver setup(){
System.setProperty("webdriver.chrome.driver", "C:\\Skillwar\\01 Automation Jars\\Automation Jars\\Selenium\\chromedriver_win32\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.get("https://www.savaari.com/");
return driver;}}
package com.cognizant;
import java.util.List;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
public class Search extends SampleClass{
@BeforeMethod
public void test1() throws Exception{
driver = setup();
Thread.sleep(5000);
}
@Test(priority=1)
public void searching() throws Exception{
driver.findElement(By.xpath("//*[@class='margin-left-20px']/span")).click();
Thread.sleep(2000);
WebElement wc=driver.findElement(By.xpath("//*[@id='fromCityList']"));
wc.sendKeys("Mumbai");
Thread.sleep(2000);
wc.sendKeys(Keys.DOWN);
wc.sendKeys(Keys.ENTER);
Thread.sleep(2000);
WebElement we=driver.findElement(By.xpath("((//*[@type='text'])[2])"));
we.sendKeys("Pune,");
Thread.sleep(2000);
we.sendKeys(Keys.DOWN);
we.sendKeys(Keys.ENTER);
Thread.sleep(2000);
driver.findElement(By.xpath("//input[@class='ng-tns-c11-1 form-control ui-inputtext ui-widget ui-state-default ui-corner-all']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@class='ui-datepicker-calendar ng-tns-c11-1']/tbody[@class='ng-tns-c11-1']/tr[4]/td[5]")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='pickUpTime']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='pickUpTime']/option[@value='2019-06-20T04:00:00+05:30']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@class='book-button btn']")).click();
Thread.sleep(5000);
String text=driver.findElement(By.xpath("((//*[@class='carNamesDesktop'])[1])")).getText();
System.out.println("First Car Name :"+text);
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='sv_header']/div/div[1]/a/img")).click();
Thread.sleep(5000);
}
@AfterMethod
public void exit() throws Exception{
driver.quit();
}
}
88888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
Marshalls:
Bird:
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import Pages.MainPage;
public class Home {
WebDriver driver;
@Test
public void getPages() throws InterruptedException {
MainPage m = PageFactory.initElements(driver, MainPage.class);
m.clickBird();
m.clickFood();
m.getProductName();
m.clickProduct();
m.clickAddtoCart();
m.clickNextProduct();
m.clickAddtoCart1();
m.clickCheckOut();
m.cartSummaryPage();
}
@BeforeMethod
public void getUrl() {
System.setProperty("webdriver.chrome.driver", "C:\\Users\\743058\\Downloads\\chromedriver_win32\\chromedriver.exe");
driver = new ChromeDriver();
driver.get("https://www.marshallspetzone.com/");
driver.manage().window().maximize();
System.out.println("Completed");
}
/*@AfterMethod
public void closeBrowser() {
driver.quit();
}*/
}
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------package Pages;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.Assert;
public class MainPage {
WebDriver driver;
public MainPage(WebDriver driver) {
this.driver= driver;
}@FindBy(xpath="//li[@id='cbp-hrmenu-tab-14']")
WebElement bird;
@FindBy(xpath="//div[@class='category-top-menu block-content']//a[text()=\"Food\"]")
WebElement food;
@FindBy(xpath="(//div[@class='product-description']//h3[@class='h3 product-title']//a)[1]")
WebElement productName;
@FindBy(xpath="(//div[@class='thumbnail-container'])[1]")
WebElement product;
@FindBy(xpath="//button[@class='btn btn-primary btn-lg add-to-cart']")
WebElement addtoCart;
@FindBy(xpath="//button[text()=\"Continue shopping\"]")
WebElement continueBtn;
@FindBy(xpath="(//span[@class='custom-checkbox'])[2]"
WebElement instock;
@FindBy(xpath="(//div[@class='thumbnail-container'])[2]")
WebElement nextProduct;
@FindBy(xpath="//div[@class='cart-content-btn']//a[@class='btn btn-primary btn-block btn-lg mb-2']")
WebElement checkout;
@FindBy(xpath="ps-shoppingcart")
WebElement cart;
@FindBy(xpath="(//div[@class='product-line-info']//a)[1]")
WebElement firstProduct;
String first;
@FindBy(xpath="(//h3[@class='h3 product-title'])[2]")
WebElement secondProduct;
String second;
@FindBy(xpath="(//a[@class='label'])[1]")
WebElement cartFirstProduct;
@FindBy(xpath="(//a[@class='label'])[2]")
WebElement cartSecondProduct;
public void clickBird(){
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(bird)).click();
}
public void clickFood() {
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(food)).click();
}
public void getProductName() throws InterruptedException {
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.visibilityOf(instock)).click();
Thread.sleep(10000);
//System.out.println(wait.until(ExpectedConditions.visibilityOf(productName)).getText());
//String s = wait.until(ExpectedConditions.visibilityOf(productName)).getText();
first = productName.getText();
System.out.println("String is "+first);
}
public void clickProduct() {
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(secondProduct));
second = secondProduct.getText();
System.out.println("Second product NAme :"+second);
wait.until(ExpectedConditions.visibilityOf(product)).click();
}
public void clickAddtoCart() throws InterruptedException {
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(addtoCart)).click();
Thread.sleep(10000);
//wait.until(ExpectedConditions.visibilityOf(continueBtn)).click()
driver.navigate().back();
}
public void clickNextProduct() {
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(nextProduct)).click();
}
public void clickAddtoCart1() throws InterruptedException {
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(addtoCart)).click();
Thread.sleep(10000);
}
public void clickCheckOut()
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(checkout)).click();
}
/*public void cartBtn() {
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(cart)).click();
}*/
public void cartSummaryPage() {
WebDriverWait wait = new WebDriverWait(driver, 10);
wait.until(ExpectedConditions.visibilityOf(cartFirstProduct));
String cartFirst = cartFirstProduct.getText();
Assert.assertTrue(cartFirst.equals(first));
wait.until(ExpectedConditions.visibilityOf(cartSecondProduct));
String s = cartSecondProduct.getText();
Assert.assertTrue(s.equals(second));
System.out.println("Completed Thank You");
}
}
…………………………………………………………………………………………….
Marshall:
Login Page:
package pages;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
public class Login {
WebDriver driver;
public Login(WebDriver driver) {
this.driver = driver;
}
@FindBy(xpath="//div[@id='iqitmegamenu-horizontal']//li[@id='cbp-hrmenu-tab-13']")
WebElement cat;
@FindBy(xpath="//ul[@class='category-sub-menu']//li/a[text()=\"Accessories\"]")
WebElement accessories;
@FindBy(xpath="//div[@class='products-sort-nb-dropdown products-sort-order dropdown']")
WebElement dropdown;
@FindBy(xpath="//div[@class='dropdown-menu']//a[contains(text(),'Price, low to high')]")
WebElement lowToHigh;
@FindBy(xpath="//div[@class='dropdown-menu']//a[contains(text(),'Price, high to low')]")
WebElement highToLow;
@FindBy(xpath="(//h3[@class='h3 product-title'])[1]")
WebElement productName;
@FindBy(xpath="(//span[@class='product-price'])[1]")
WebElement price;
@FindBy(xpath="(//div[@class='category-top-menu block-content']//ul[@class='category-sub-menu']//li/a[contains(text(),'Food')])[1]")
WebElement food;
@FindBy(xpath="//a[@class=' js-search-link']")
WebElement list;
@FindBy(xpath="//div[@id='desktop_logo']")
WebElement logo;
public void clickCat() throws InterruptedException {
Thread.sleep(10000);
//WebDriverWait wait = new WebDriverWait(driver, 10);
//wait.until(ExpectedConditions.elementToBeClickable(cat)).click();
//JavascriptExecutor executor = (JavascriptExecutor) driver;
//executor.executeScript("arguments[0].click();", cat);
cat.click();
}
public void clickAccess() {
WebDriverWait wait = new WebDriverWait(driver, 50);
wait.until(ExpectedConditions.elementToBeClickable(accessories)).click();
}
public void dropDown() {
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.elementToBeClickable(dropdown)).click();
}
public void clickLowtoHigh() {
JavascriptExecutor exe = (JavascriptExecutor) driver;
exe.executeScript("window.scrollBy(0,250)", "");
WebDriverWait wait = new WebDriverWait(driver, 50);
wait.until(ExpectedConditions.elementToBeClickable(lowToHigh)).click();
}
public void getProductName() throws InterruptedException {
//WebDriverWait wait = new WebDriverWait(driver, 30);
// System.out.println(wait.until(ExpectedConditions.elementToBeClickable(productName)).getText());
Thread.sleep(10000);
System.out.println(productName.getText());
}
public void getPrice() {
WebDriverWait wait = new WebDriverWait(driver, 10);
System.out.println(wait.until(ExpectedConditions.elementToBeClickable(price)).getText());
}
public void clickFood() {
WebDriverWait wait = new WebDriverWait(driver, 50);
wait.until(ExpectedConditions.elementToBeClickable(food)).click();
}
public void clickHighToLow() throws InterruptedException {
JavascriptExecutor exec= (JavascriptExecutor) driver;
exec.executeScript("window.scrollBy(0,250)", "");
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.elementToBeClickable(highToLow)).click();
//highToLow.click();
}
public void clickList() {
WebDriverWait wait = new WebDriverWait(driver, 1000);
wait.until(ExpectedConditions.elementToBeClickable(list)).click();
}
public void homePage() {
JavascriptExecutor exec= (JavascriptExecutor) driver;
((JavascriptExecutor) exec).executeScript("window.scrollBy(0, -250)", "");
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.elementToBeClickable(logo)).click();
}}
==============================================================================================
ChromeDriver Class:
package testrunner;
import java.io.IOException;
import java.util.Properties;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import pages.Login;
import setup.Driver;
public class ChromeDriver{
WebDriver driver;
@Test
public void methods() throws InterruptedException {
// Login login = new Login(driver);
Login login = PageFactory.initElements(driver, Login.class);
login.clickCat();
login.dropDown();
login.clickLowtoHigh();
login.getProductName();
login.getPrice();
login.clickCat();
login.clickFood();
login.dropDown();
login.clickHighToLow();
login.getProductName();
login.getPrice();
login.clickList();
login.homePage();
}
@BeforeMethod
public void getUrl() {
System.setProperty("webdriver.chrome.driver", "C:\\Users\\708753\\Downloads\\chromedriver_win32\\chromedriver.exe");
driver = new org.openqa.selenium.chrome.ChromeDriver();
driver.get("https://www.marshallspetzone.com/");
driver.manage().window().maximize();
System.out.println("Completed");
}
@AfterMethod
public void close() {
driver.quit();}}
=============================================================================================
FirefoxBrowser Class
package testrunner;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import pages.Login;
public class FirefoxBrowser {
WebDriver driver;
@Test
public void methods() throws InterruptedException {
// Login login = new Login(driver);
Login login = PageFactory.initElements(driver, Login.class);
login.clickCat();
login.clickAccess();
login.dropDown();
login.clickLowtoHigh();
login.getProductName();
login.getPrice();
login.clickCat();
login.clickFood();
login.dropDown();
login.clickHighToLow();
login.getProductName();
login.getPrice();
login.clickList();
login.homePage();
}
@BeforeMethod
public void getUrl() {
System.setProperty("webdriver.gecko.driver", "C:\\Users\\708753\\Downloads\\geckodriver-v0.24.0-win64\\geckodriver.exe");
driver = new FirefoxDriver();
driver.get("https://www.marshallspetzone.com/");
driver.manage().window().maximize();
System.out.println("Completed");
}
@AfterMethod
public void close() {
driver.quit();}}

===================================================================================================
testng.xml
<?xml version="1.0" encoding="UTF-8"?>
<suite name="Sample Test Suite" parallel="tests" thread-count="3">
<test name="Assignments">
<classes>
<class name="testrunner.FirefoxBrowser">
</class>
</classes>
</test>
<test name="Assignments1">
<classes>
<class name="testrunner.ChromeDriver">
</class>
</classes>
</test>
</suite>
============================================================================================
Marshall food:
package testrunner;
import java.io.IOException;
import java.util.Properties;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import pages.Login;
import setup.Driver;
public class ChromeDriver{
WebDriver driver;
@Test
public void methods() throws InterruptedException {
// Login login = new Login(driver);
Login login = PageFactory.initElements(driver, Login.class);
login.clickCat();
login.clickAccess();
login.dropDown();
login.clickLowtoHigh();
login.getProductName();
login.getPrice();
login.clickCat();
login.clickFood();
login.dropDown();
login.clickHighToLow();
login.getProductName();
login.getPrice();
login.clickList();
login.homePage();
}
@BeforeMethod
public void getUrl() {
System.setProperty("webdriver.chrome.driver", "C:\\Users\\708753\\Downloads\\chromedriver_win32\\chromedriver.exe");
driver = new org.openqa.selenium.chrome.ChromeDriver();
driver.get("https://www.marshallspetzone.com/");
driver.manage().window().maximize();
System.out.println("Completed");
}
@AfterMethod
public void close() {
driver.quit();
}
}

========================================================================================================
package pages;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.ui.ExpectedCondition;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
public class Login {
WebDriver driver;
public Login(WebDriver driver) {
this.driver = driver;
}

@FindBy(xpath="//div[@id='iqitmegamenu-horizontal']//li[@id='cbp-hrmenu-tab-13']")
WebElement cat;
@FindBy(xpath="//ul[@class='category-sub-menu']//li/a[text()=\"Accessories\"]")
WebElement accessories;
@FindBy(xpath="//div[@class='products-sort-nb-dropdown products-sort-order dropdown']")
WebElement dropdown;
@FindBy(xpath="//div[@class='dropdown-menu']//a[contains(text(),'Price, low to high')]")
WebElement lowToHigh;
@FindBy(xpath="//div[@class='dropdown-menu']//a[contains(text(),'Price, high to low')]")
WebElement highToLow;
@FindBy(xpath="(//h3[@class='h3 product-title'])[1]")
WebElement productName;
@FindBy(xpath="(//span[@class='product-price'])[1]")
WebElement price;
@FindBy(xpath="(//div[@class='category-top-menu block-content']//ul[@class='category-sub-menu']//li/a[contains(text(),'Food')])[1]")
WebElement food;
@FindBy(xpath="//a[@class=' js-search-link']")
WebElement list;
@FindBy(xpath="//div[@id='desktop_logo']")
WebElement logo;
public void clickCat() throws InterruptedException {
Thread.sleep(10000);
//WebDriverWait wait = new WebDriverWait(driver, 10);
//wait.until(ExpectedConditions.elementToBeClickable(cat)).click();
//JavascriptExecutor executor = (JavascriptExecutor) driver;
//executor.executeScript("arguments[0].click();", cat);
cat.click();
}
public void clickAccess() {
WebDriverWait wait = new WebDriverWait(driver, 50);
wait.until(ExpectedConditions.elementToBeClickable(accessories)).click();
}
public void dropDown() {
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.elementToBeClickable(dropdown)).click();
}
public void clickLowtoHigh() {
JavascriptExecutor exe = (JavascriptExecutor) driver;
exe.executeScript("window.scrollBy(0,250)", "");
WebDriverWait wait = new WebDriverWait(driver, 50);
wait.until(ExpectedConditions.elementToBeClickable(lowToHigh)).click();
}
public void getProductName() throws InterruptedException {
//WebDriverWait wait = new WebDriverWait(driver, 30);
// System.out.println(wait.until(ExpectedConditions.elementToBeClickable(productName)).getText());
Thread.sleep(10000);
System.out.println(productName.getText());
}
public void getPrice() {
WebDriverWait wait = new WebDriverWait(driver, 10);
System.out.println(wait.until(ExpectedConditions.elementToBeClickable(price)).getText());
}
public void clickFood() {
WebDriverWait wait = new WebDriverWait(driver, 50);
wait.until(ExpectedConditions.elementToBeClickable(food)).click();
}
public void clickHighToLow() throws InterruptedException {
JavascriptExecutor exec= (JavascriptExecutor) driver;
exec.executeScript("window.scrollBy(0,250)", "");
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.elementToBeClickable(highToLow)).click();
//highToLow.click();
}
public void clickList() {
WebDriverWait wait = new WebDriverWait(driver, 1000);
wait.until(ExpectedConditions.elementToBeClickable(list)).click();
}
public void homePage() {
JavascriptExecutor exec= (JavascriptExecutor) driver;
((JavascriptExecutor) exec).executeScript("window.scrollBy(0, -250)", "");
WebDriverWait wait = new WebDriverWait(driver, 20);
wait.until(ExpectedConditions.elementToBeClickable(logo)).click();
}
}
Shalu:
Driverpage:-
package marsell;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import pages.Loginpage;
public class Drivercalling {
WebDriver driver;
@BeforeMethod
public void getURl() throws InterruptedException{
System.setProperty("webdriver.chrome.driver", "C:\\Users\\708649\\Downloads\\cognizant-intelligent-test-scripter-1.2-setup\\cognizant-intelligent-test-scripter-1.2\\lib\\Drivers\\chromedriver.exe");
driver=new ChromeDriver();
//Thread.sleep(10000);
driver.get("https://www.marshallspetzone.com");
driver.manage().window().maximize();}
@Test
public void getmethod() throws InterruptedException
{
Loginpage l=PageFactory.initElements(driver,Loginpage.class);
l.cat();
l.access();
l.dropdown();
l.lowtohigh();
l.product();
l.price();
l.cat();
l.food();
l.dropdown1();
l.hightolow();
l.productname();
l.proprice();
l.list();
l.logo();
}
@AfterMethod()
public void close(){
driver.quit();}
}
Loginpage:-
package pages;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
public class Loginpage {
WebDriver driver;
public Loginpage(WebDriver driver){
this.driver=driver;
}
@FindBy(xpath="(//span[@class='cbp-tab-title'])[3]") //finding element cat
WebElement cat;
@FindBy(xpath="(//a[text()='Accessories'])[11]")//finding element accessories
WebElement access;
@FindBy(xpath="(//div[@class='products-sort-nb-dropdown products-sort-order dropdown'])")
WebElement dropdown;
@FindBy(xpath="//div[@class='dropdown-menu']//a[contains(text(),'Price, low to high')]")//finding element price low to high
WebElement lowtohigh;
@FindBy(xpath="(//h3[@class='h3 product-title'])[1]")
WebElement productname;
@FindBy(xpath="(//span[@class='product-price'])[1]")//finding element price of product
WebElement productprice;
@FindBy(xpath="(//a[text()='Food'])[12]")//Finding element food
WebElement food;
@FindBy(xpath="//div[@class='products-sort-nb-dropdown products-sort-order dropdown']")//finding element second dropdown
WebElement dropdown2;
@FindBy(xpath="//div[@class='dropdown-menu']//a[contains(text(),'Price, high to low')]")
WebElement hightolow;
@FindBy(xpath="(//h3[@class='h3 product-title'])[1]")
WebElement Productname;
@FindBy(xpath="(//div[@class='product-price-and-shipping'])[1]")
WebElement proprice;
@FindBy(xpath="//a[@class='current js-search-link']")
WebElement list;
@FindBy(xpath="(//img[@class='logo img-fluid'])[1]")
WebElement logo;
public void cat() throws InterruptedException
{
//WebDriverWait w1=new WebDriverWait(driver,10);
//wait.until(ExpectedConditions.elementToBeClickable(cat)).click();
Thread.sleep(10000);
cat.click();
}
public void access(){
WebDriverWait wait=new WebDriverWait(driver,20);
wait.until(ExpectedConditions.elementToBeClickable(access)).click();
}
public void dropdown(){
WebDriverWait wait=new WebDriverWait(driver,50);
wait.until(ExpectedConditions.elementToBeClickable(dropdown)).click();
}
public void lowtohigh(){
JavascriptExecutor exe=(JavascriptExecutor)driver;
exe.executeScript("scroll(0,250)");
WebDriverWait wait=new WebDriverWait(driver, 50);
wait.until(ExpectedConditions.elementToBeClickable(lowtohigh)).click();
}
public void product() throws InterruptedException{
Thread.sleep(1000);
System.out.println(productname.getText());
}
public void price(){
WebDriverWait wait=new WebDriverWait(driver, 20);
System.out.println(wait.until(ExpectedConditions.elementToBeClickable(productprice)).getText());
}
public void food(){
WebDriverWait wait=new WebDriverWait(driver,20);
wait.until(ExpectedConditions.elementToBeClickable(food)).click();
}
public void dropdown1(){
WebDriverWait wait=new WebDriverWait(driver,20);
wait.until(ExpectedConditions.elementToBeClickable(dropdown2)).click();}
public void hightolow(){
JavascriptExecutor exe=(JavascriptExecutor)driver;
exe.executeScript("scroll(0,250)");
WebDriverWait wait=new WebDriverWait(driver,50);
wait.until(ExpectedConditions.elementToBeClickable(hightolow)).click();
}
public void productname(){
WebDriverWait wait=new WebDriverWait(driver,20);
System.out.println(wait.until(ExpectedConditions.elementToBeClickable(Productname)).getText());
}
public void proprice(){
WebDriverWait wait=new WebDriverWait(driver,20);
System.out.println(wait.until(ExpectedConditions.elementToBeClickable(proprice)).getText());
}
public void list() throws InterruptedException{
WebDriverWait wait=new WebDriverWait(driver,30);
wait.until(ExpectedConditions.elementToBeClickable(list)).click();
Thread.sleep(1000);
}
public void logo() throws InterruptedException{
WebDriverWait wait=new WebDriverWait(driver,20);
wait.until(ExpectedConditions.elementToBeClickable(logo)).click();
Thread.sleep(100);}}
888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
Petco:
Petco----
package com.cognizant;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.ie.InternetExplorerDriver;
import org.testng.annotations.Test;
public class SampleClass {
WebDriver driver;
public WebDriver setup(){
System.setProperty("webdriver.chrome.driver", "C:\\Skillwar\\01 Automation Jars\\Automation Jars\\Selenium\\chromedriver_win32\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.get("https://www.petco.com/");return driver;}}
********************************************************************************************************
package com.cognizant;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
public class Search extends SampleClass{
@BeforeMethod
public void test1() throws Exception{
driver = setup();
}
@Test(priority=1)
public void searching() throws Exception{
driver.findElement(By.xpath("//*[@class='top-level has-subnav toggle-open'][contains(text(),'Shop by Pet')]")).click();
driver.findElement(By.xpath("//*[@id='shop-by-pet-dog']//*[contains(text(),'Dog')]"));
driver.findElement(By.xpath("//*[@class='col']//li//a[contains(@href,'/shop/en/petcostore/category/dog/dog-food/prescription-dog-food-and-treats')][1]")).click();
Select sc=new Select(driver.findElement(By.xpath("//*[@id='product-listing-sort-by_4_3074457345618259661_4099276460824412685']")));
sc.selectByIndex(1);
Thread.sleep(10000);
String name=driver.findElement(By.xpath("//*[@class='product-name']//a[contains(@title,'Blue Buffalo BLUE Natural Veterinary Diet GI Gastrointestinal Support Dry Dog Food')]")).getText();
System.out.println("Name:"+name);
Thread.sleep(5000);
String price=driver.findElement(By.xpath("//*[@id='product-price_2457002']/div/span[1]")).getText();
System.out.println("Price:"+price);
Thread.sleep(5000);
//driver.findElement(By.xpath("//*[@class='next right_arrow ']")).click();
//Thread.sleep(10000);
driver.findElement(By.xpath("//*[@class='checkbox-button text-normal text-dark Between_$10_and_$25']")).click();
Thread.sleep(10000);
Select se=new Select(driver.findElement(By.xpath("//*[@id='product-listing-sort-by_4_3074457345618259661_4099276460824412685']")));
se.selectByIndex(4);
Thread.sleep(5000);
String name2=driver.findElement(By.xpath("//*[@class='product-name']//a[contains(@href,'https://www.petco.com/shop/en/petcostore/product/dog/dog-food/prescription-dog-food-and-treats/hills-prescription-diet-td-dental-care-small-bites-chicken-flavor-dry-dog-food')]")).getText();
System.out.println("Name2:"+name2);
Thread.sleep(5000);
String price2=driver.findElement(By.xpath("//*[@class='product-price-rddetail'][1]")).getText();
System.out.println("Price2:"+price2);
Thread.sleep(5000);
driver.findElement(By.xpath("//*[@class='pull-left brand-logo']")).click();
Thread.sleep(5000);
}@AfterMethod
public void exit() throws Exception{
driver.quit();}}
8888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
91 mobiles:
package com.cognizant;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.ie.InternetExplorerDriver;
import org.testng.annotations.Test;
public class SampleClass {
WebDriver driver;
public WebDriver setup()
{
System.setProperty("webdriver.ie.driver", "C:\\Skillwar\\01 Automation Jars\\Automation Jars\\Selenium\\chromedriver_win32\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.get("https://www.91mobiles.com/");
return driver;}
}
package com.cognizant;
import org.apache.bcel.generic.Select;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;
public class Mobiles extends SampleClass {
@BeforeTest
public void test1() throws Exception{
driver = setup();
}@Test
public void searching() throws Exception{
WebElement we = driver.findElement(By.xpath("//*[@class='tiker_input mini_finder_input_1']"));
Thread.sleep(5000);
we.clear();
Thread.sleep(5000);
we.sendKeys("5000");
WebElement wd = driver.findElement(By.xpath("//*[@class='tiker_input mini_finder_input_2']"));
Thread.sleep(5000);
wd.clear();
Thread.sleep(5000);
wd.sendKeys("10000");
driver.findElement(By.xpath("//*[@class='view_details_btn find_mob mini_finder_btn enabled']")).click();
Thread.sleep(5000);
WebElement findElement = driver.findElement(By.xpath("//*[@id='price_box']"));
findElement.click();
Thread.sleep(5000);
findElement.click();
Thread.sleep(5000);
// for low price mobile
String text = driver.findElement(By.xpath("//*[@class='hover_blue_link name gaclick'][contains(text(),'Innelo 1')]")).getText();
System.out.println("Low price mobile Name : "+text);
Thread.sleep(3000);
String price = driver.findElement(By.xpath("//*[@class='price price_padding'][contains(text(),'5,029')]")).getText();
System.out.println("Low price mobile's price : "+price);
// for high price mobile
driver.findElement(By.xpath("//*[@id='price_box']")).click();
Thread.sleep(2000);
String text1 = driver.findElement(By.xpath("//*[@class='hover_blue_link name gaclick'][contains(text(),'Samsung Galaxy J7 Nxt')]")).getText();
System.out.println("High price mobile Name : "+text1);
Thread.sleep(3000);
String price1 = driver.findElement(By.xpath("//*[@class='price price_padding'][contains(text(),'10,000')]")).getText();

System.out.println("High price mobile's price : "+price1);
driver.findElement(By.xpath("//*[@class='logo']/a")).click();
Thread.sleep(5000);
}
@AfterTest
public void exit() throws Exception{
driver.quit();}}
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Salesforce.com
package Browsers;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
public class Chromedr {
WebDriver driver;
public WebDriver getchromedriver(){
System.setProperty("webdriver.chrome.driver", "C:\\Program Files\\seleniumJars\\drivers\\chromedriver_win32 (1)\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().deleteAllCookies();
driver.manage().window().maximize();
driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
driver.get("https://developer.salesforce.com");
return driver;}}
********************************************************************************************************
package Excel;
import java.io.FileInputStream;
import java.io.IOException;
import org.apache.poi.ss.usermodel.Cell;
import org.apache.poi.ss.usermodel.DataFormatter;
import org.apache.poi.ss.usermodel.Row;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
public class Excel {
public static XSSFWorkbook workbook;
public static XSSFSheet xfsheet;
public static void setPath() throws Exception{
FileInputStream fi=new FileInputStream("C:\\Users\\india\\eclipse-workspace\\salesforce\\Sheet1.xlsx");
workbook=new XSSFWorkbook(fi);
xfsheet=workbook.getSheet("Sheet1");
}
public static String cellvalue(int row,int col){
try {
String data1=xfsheet.getRow(row).getCell(col).getStringCellValue();
return data1;
}
catch (Exception e){
e.printStackTrace();
return null;}}}
********************************************************************************************************package xpath;
public class xpath {
public static String SignUp="//a[@class='btn btn-success']";
public static String email="//input[@id='email']";
public static String country="(//select[@class='textFieldOp'])[2]";
public static String login="//a[text()='Log In']";
public static String remember="//input[@name='rememberUn']";
}
***************************************************************************************
package Test;
import org.testng.annotations.Test;
import Browsers.Chromedr;
import Excel.Excel;
import xpath.xpath;
import org.testng.annotations.BeforeTest;
import java.io.File;
import java.io.IOException;
import org.apache.commons.io.FileUtils;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeClass;
public class MainPage extends Chromedr{
WebDriver driver;
@BeforeTest
public void beforeClass() {
driver = getchromedriver();
}
@Test
public void testForGoibibo() throws Throwable {
driver.findElement(By.xpath(xpath.SignUp)).click();
Excel.setPath();
String start=Excel.cellvalue(0,0);
System.out.println(start);
String country=Excel.cellvalue(0,1);
System.out.println(country);
WebElement we1 = driver.findElement(By.xpath(xpath.email));
we1.sendKeys(start);
Thread.sleep(5000);
//we1.sendKeys(Keys.ARROW_DOWN);
we1.sendKeys(Keys.TAB);
System.out.println("Please enter a valid email address");
//WebElement we2 = driver.findElement(By.xpath(xpath.country));
//we2.sendKeys(country);
//Thread.sleep(5000);
//we2.sendKeys(Keys.ARROW_DOWN);
//we2.sendKeys(Keys.TAB);
Select drop = new Select(driver.findElement(By.xpath(xpath.country)));
drop.selectByVisibleText("Australia");
driver.findElement(By.xpath(xpath.login)).click();
driver.findElement(By.xpath(xpath.remember)).click();
TakesScreenshot tc = ((TakesScreenshot) driver);
File sc = tc.getScreenshotAs(OutputType.FILE);
//File des = new File("./screenshots/screenshots.png");
File ds = new File("C:\\Users\\india\\eclipse-workspace\\salesforce\\screenshot.png");
FileUtils.copyFile(sc, ds);
//FileUtils.copyFile(sc, des);
System.out.println("SCREENSHOT TAKEN");
driver.close();
}
}
888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888888
ICICI Bank
package com.cognizant;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
public class Search extends SampleClass{
@BeforeMethod
public void test1() throws Exception{
driver = setup();
}
@Test(priority=1)
public void searching() throws Exception{
driver.switchTo().frame("paymframe");
Select sc=new Select(driver.findElement(By.xpath("//*[@id='ddlTypeOfFixedDeposit']")));
sc.selectByIndex(1);
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='loanAmount']")).clear();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='loanAmount']")).sendKeys("60000");
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='idYYMMDD']")).click();
String Maturity=driver.findElement(By.xpath("//*[@id='spnMaturityValue']")).getText();
System.out.println("Maturity Value:"+Maturity);
Thread.sleep(2000);
String amt=driver.findElement(By.xpath("//*[@id='spnAIAmount']")).getText();
System.out.println("Aggregate amount:"+amt);
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='idDays']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='tenureDay']")).clear();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='tenureDay']")).sendKeys("1000");
driver.findElement(By.xpath("//*[@id='tenureDay']")).click();
Thread.sleep(20000);
String Maturity1=driver.findElement(By.xpath("//*[@id='spnMaturityValue']")).getText();
System.out.println("Maturity Value:"+Maturity1);
Thread.sleep(2000);
String amt1=driver.findElement(By.xpath("//span[@id='spnAIAmount']")).getText();
System.out.println("Aggregate amount:"+amt1);
Thread.sleep(2000);
driver.findElement(By.xpath("//a[@class='Logo']")).click();
Thread.sleep(2000);
}
@AfterMethod
public void exit() throws Exception{
driver.quit();
}
}
BufferedImage image=new Robot().createScreenCapture(new Rectangle(Toolkit.getDefaultToolkit().getScreenSize()));
ImageIO.write(image,"png",new File("C:\\Users\\701452\\Desktop\\PIC\\01"));
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
icicibank2
MainPage
package pages;
import java.awt.AWTException;
import java.awt.Robot;
import java.awt.event.KeyEvent;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.FindBy;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;
public class MainPage {
WebDriver driver;
public MainPage(WebDriver driver) {
this.driver= driver;
}
@FindBy(xpath="//select[@id='ddlTypeOfFixedDeposit']//option[@id='quarterly_payout']")
WebElement fd;
@FindBy(xpath="//select[@id='ddlTypeOfFixedDeposit']")
WebElement drpdwn;
@FindBy(xpath="//input[@id='loanAmount']")
WebElement amount;
@FindBy(xpath="//span[@id='spnMaturityValue']")
WebElement maturity;
@FindBy(xpath="//input[@id='idDays']")
WebElement days;
@FindBy(xpath="//input[@id='tenureDay']")
WebElement enterDays;
@FindBy(xpath="//span[@id='spnAIAmount']")
WebElement mamount;
public void selectFD() throws InterruptedException {
Thread.sleep(10000);
JavascriptExecutor executor = (JavascriptExecutor) driver;
executor.executeScript("window.scrollBy(0, 250)", "");
//((JavascriptExecutor) exec).executeScript("window.scrollBy(0, -250)", "");
Select select = new Select(drpdwn);
select.selectByIndex(1);
}
public void selectAmount() throws InterruptedException {
Thread.sleep(2000);
amount.clear();
Thread.sleep(2000);
amount.sendKeys("60000");
}
public void getMaturity() throws InterruptedException {
Thread.sleep(5000);
System.out.println(maturity.getText());
}
public void selectDays() throws InterruptedException {
days.click();
Thread.sleep(2000);
enterDays.clear();
enterDays.sendKeys("1000");
}
public void getAmount() throws InterruptedException {
Thread.sleep(2000);
mamount.getText();
}}==================================================================================================

ChromeDriver Page
package testrunner;
import java.awt.AWTException;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.support.PageFactory;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import pages.MainPage;
public class ChromeDriver {
WebDriver driver;
@Test
public void method() throws InterruptedException, AWTException {
MainPage mp = PageFactory.initElements(driver, MainPage.class);
driver.switchTo().frame(driver.findElement(By.id("paymframe")));
Thread.sleep(5000);
// MainPage mp = new MainPage(driver);
mp.selectFD();
mp.selectAmount();
mp.selectDays();
mp.getMaturity();
mp.getAmount();}
@BeforeMethod
public void getUrl() {
System.setProperty("webdriver.chrome.driver", "C:\\Users\\708753\\Downloads\\chromedriver_win32\\chromedriver.exe");
driver = new org.openqa.selenium.chrome.ChromeDriver();
driver.get("https://www.icicibank.com/calculator/fd-calculator.page");
driver.manage().window().maximize();
System.out.println("Completed");
}
/* @AfterMethod
public void close() {
driver.quit();
}*/
}

888888888888888888888888888888888888888888888888888888888888888888888888888888888
Axis Bank:
import org.testng.annotations.Test;
import org.testng.annotations.Test;
import java.util.concurrent.TimeUnit;
import org.openqa.selenium.Alert;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;
public class AxisBank {
public static WebDriver driver;
@BeforeMethod
public void beforeMethod() throws Exception {
//System.setProperty("webdriver.chrome.driver", "D:\\Selenium Training\\chrome driver 2.45\\chromedriver_win32\\chromedriver.exe");
//to disable notifications
ChromeOptions chromeOptions = new ChromeOptions();
chromeOptions.addArguments("--disable-notifications");
driver = new ChromeDriver(chromeOptions);
//to maximize the window size
driver.manage().window().maximize();
//Adding wait time implicitly and launching the Website link
driver.manage().timeouts().implicitlyWait(60,TimeUnit.SECONDS);
//driver = new ChromeDriver();
driver.get("https://www.axisbank.com/personal/calculators/fd-monthly-investment-calculator");
Thread.sleep(3000);
}
@Test

public void test() throws Exception{
//driver.switchTo().frame("notification-frame-~2514428c7");
//name="notification-frame-~2514428c7"
//driver.findElement(By.xpath("//*[@id='nvpush_cross']/svg/g/path")).click();
//Thread.sleep(2000);
//selecting the type of deposit as monthly investment
WebElement typeOfDeposit = driver.findElement(By.xpath("//div//div//a[contains(text(),'Monthly Investment')]"));
typeOfDeposit.click();
Thread.sleep(2000);
WebElement monthlyInvestment = driver.findElement(By.xpath("//div[normalize-space(text())='Type of Deposit']//div//ul//a[normalize-space(text())='Monthly Investment']"));
monthlyInvestment.click();
Thread.sleep(5000);
//Entering the amount of deposit as 30000
WebElement amountToDeposit = driver.findElement(By.xpath("//div//input[@class='form-control txtAmount']"));
amountToDeposit.clear();
amountToDeposit.sendKeys("30000");
//displaying the interest Rate
String interestRate = driver.findElement(By.xpath("//div[@class='interest_rate']//span[@class='inst_amt']")).getText();
System.out.println("Interest Rate = " + interestRate);
//calculating
WebElement calculate = driver.findElement(By.xpath("//div//a[normalize-space(text())='Calculate']"));
calculate.click();
Thread.sleep(5000);
//Displaying the Maturity Amount
String GrossTotal = driver.findElement(By.xpath("//span[@class='maturity_amt grossTotal']")).getText();
System.out.println("Maturity Amount = " + GrossTotal);
}
@AfterMethod
public void exit(){
driver.quit();}}
*******************************************************************************8
package com.cognizant;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
import com.cognizant.SampleClass;
@Test
public class Search extends SampleClass{
@BeforeMethod
public void test1() throws Exception{
driver = setup();
}
@Test
public void Run() throws Exception{
driver.findElement(By.xpath("//div[normalize-space(text())='Type of Deposit']//div//a[@class='sbToggle']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//div[normalize-space(text())='Type of Deposit']//div//ul//a[normalize-space(text())='Monthly Investment']")).click();
Thread.sleep(5000);
//WebDriverWait SpinnerWait= new WebDriverWait(driver, 10);
//SpinnerWait.until(ExpectedConditions.invisibilityOfElementLocated(locator));
String amount = "30000";
driver.findElement(By.xpath("//div//input[@class='form-control txtAmount']")).click();
WebElement amountField = driver.findElement(By.xpath("//div//input[@class='form-control txtAmount']"));
JavascriptExecutor js = (JavascriptExecutor)driver;
js.executeScript("arguments[0].value = '';", amountField); // To clear the textbox value using Javascript executor
js.executeScript("arguments[0].value = '" + amount + "';", amountField); // To enter value the textbox value using Javascript executor
//driver.findElement(By.xpath("//div//input[@class='form-control txtAmount']")).sendKeys("30000");
/*driver.findElement(By.xpath("//div//input[@class='form-control txtAmount']")).sendKeys(Keys.chord(Keys.CONTROL, "a"));
Thread.sleep(1000);
driver.findElement(By.xpath("//div//input[@class='form-control txtAmount']")).sendKeys("10000");*/
String InterestRate = driver.findElement(By.xpath("//div[@class='interest_rate']//span[@class='inst_amt']")).getText();
System.out.println("Interest Rate = "+InterestRate);
driver.findElement(By.xpath("//div//a[normalize-space(text())='Calculate']")).click();
Thread.sleep(5000);
String GrossTotal= driver.findElement(By.xpath("//span[@class='maturity_amt grossTotal']")).getText();
System.out.println("Maturity Amount = "+GrossTotal);
}@AfterMethod
public void exit() throws Exception{
driver.quit();}}
888888888888888888888888888888888888888888888888888888888888888888888888888888888
Cheap fight:
package com.cognizant;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.ie.InternetExplorerDriver;
import org.testng.annotations.Test;
public class SampleClass {
WebDriver driver;
public WebDriver setup(){
System.setProperty("webdriver.chrome.driver", "C:\\Skillwar\\01 Automation Jars\\Automation Jars\\Selenium\\chromedriver_win32\\chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.get("https://www.cheapflights.com/book-flights-online");
return driver;}}
package com.cognizant;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
public class Search extends SampleClass{
@BeforeMethod
public void test1() throws Exception{
driver = setup();
Thread.sleep(10000);
}
@Test(priority=1)
public void searching() throws Exception{
//driver.findElement(By.xpath("//*[@id='e2RB']//div[@class='col col-5-9-l col-m formContainer']//input[@id='e2RB-origin']")).clear();
//Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c9HGn-oneway-label']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c9HGn-origin']")).clear();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c9HGn-origin']")).sendKeys("Coimbatore");
Thread.sleep(2000);
Select sc= new Select(driver.findElement(By.xpath("//*[@id='c9HGn-origin']")));
sc.selectByIndex(2);
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c9HGn-destination']")).sendKeys("bangalore");
Thread.sleep(2000);
Select se= new Select(driver.findElement(By.xpath("//*[@id='c9HGn-destination']")));
se.selectByIndex(2);
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c9HGn-depart-input']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//div[@id='CTyw-201906']//div[@class='keel-grid weekGrid']//div[text()='20']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c9HGn-submit']/span")).click();
Thread.sleep(10000);
driver.findElement(By.xpath("//*[@id='c3C5c-slidecmp2-PRICELINEDFE_US_FPCMP2-label']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c3C5c-slidecmp2-COINTBBRa_US_FPCMP2-label']")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//*[@id='c3C5c-slidecmp2-cmp-all']")).click();
Thread.sleep(10000);
driver.switchTo().frame("provider-9931824-COINTBBRa_US_FPCMP2");
String cheap=driver.findElement(By.xpath("//*[@id='liPrice']/span[@class='visible-xs mob_tabs']")).getText();
Thread.sleep(2000);
System.out.println("Cheapest :"+cheap);
}@AfterMethod
public void exit() throws Exception{
driver.quit();}}
package sampleAutomation;
import java.util.ArrayList;
import java.util.List;
import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
public class clearTrip {
public static void main(String[] args) throws InterruptedException {
String URL = "https://www.cheapflights.com/book-flights-online/";
System.setProperty("webdriver.chrome.driver", ".//Driver//chromedriver.exe");
WebDriver driver = new ChromeDriver();
driver.manage().window().maximize();
driver.get(URL);
driver.findElement(By.xpath("(//label[@title='One-way'])[1]")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//div[contains(.,'From')]/input[@name='origin']")).sendKeys(Keys.chord(Keys.CONTROL, "a"));
driver.findElement(By.xpath("//div[contains(.,'From')]/input[@name='origin']")).sendKeys("Coimbatore");
Thread.sleep(3000);
driver.findElement(By.xpath("//div[contains(.,'To')]/input[@name='destination']")).sendKeys(Keys.chord(Keys.CONTROL, "a"));
driver.findElement(By.xpath("//div[contains(.,'To')]/input[@name='destination']")).sendKeys("");
Thread.sleep(1000);
driver.findElement(By.xpath("//div[contains(.,'To')]/input[@name='destination']")).sendKeys("Bengaluru");
Thread.sleep(2000);
driver.findElement(By.xpath("(//div[contains(@class,'dateRangeGrid')])[1]")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//div[@class='keel-grid monthsGrid']/div[3]//div[contains(@class,'weekGrid')][4]/div[2]")).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//div[contains(@class,'col button-col')]//button")).click();
Thread.sleep(5000);
ArrayList<String> tabs2 = new ArrayList<String> (driver.getWindowHandles());
driver.switchTo().window(tabs2.get(1));
Thread.sleep(2000);
List<WebElement> ele=driver.findElements(By.xpath("//div[contains(@id,'slidecmp2-inner')]//input[@type='checkbox']/following-sibling::label"));
ele.get(1).click();
ele.get(2).click();
Thread.sleep(2000);
driver.findElement(By.xpath("//div/button[contains(text(),'Compare Selected')]")).click();
Thread.sleep(5000);
ArrayList<String> tabs1 = new ArrayList<String> (driver.getWindowHandles());
driver.switchTo().window(tabs1.get(2));
Thread.sleep(8000);
Thread.sleep(5000);
//List<WebElement> iframeElements = driver.findElements(By.tagName("iframe"));
// System.out.println("The total number of iframes are " + iframeElements.size());
driver.switchTo().frame(0);
String Cheapest=driver.findElement(By.xpath("//div[contains(@class,'search-information-options')]//a[contains(text(),'Cheapest')]/strong")).getText();
String Shortest=driver.findElement(By.xpath("//div[contains(@class,'search-information-options')]//a[contains(text(),'Shortest')]/strong")).getText();
String Flexible=driver.findElement(By.xpath("//div[contains(@class,'search-information-options')]//a[contains(text(),'Flexible')]/strong")).getText();
System.out.println("Cheapest = "+Cheapest);
System.out.println("Shortest = "+Shortest);
System.out.println("Flexible = "+Flexible);
Thread.sleep(2000);
driver.quit();}
}


