# TestNG-Code-Snippet

Q: TestNG Assert Methods

#1) assertEquals
String ActualTitle = driver.getTitle();
String ExpectedTitle = “Amazon.com: Online Shopping for Electronics, Apparel";
Assert.assertEquals(ActualTitle, ExpectedTitle);


#2) assertNotEquals
String Pincode1 = Adambakkam.getText();
String Pincode2 = Aminijikarai.getText();       
Assert.assertNotEquals(Pincode1, Pincode2);

#3) assertTrue
Boolean checkButtonPresence = SignInButton.isDisplayed();    
Assert.assertTrue(checkButtonPresence);

#4) assertFalse
Assert.assertFalse(SignIn.isDisplayed());

#5) assertNull
String str1 = null;
String str2 = "hello";              
AssertNull(str1); 

#6) assertNotNull
String str1 = null;
String str2 = "hello";              
AssertNotNull(str2); 


---------------------------------------------------------------------------------------------------------------------------------------------------

Hard Assert – Hard Assert throws an AssertException immediately when an assert statement fails and test suite continues with next @Test

The disadvantage of Hard Assert – It marks the method as failing if the assert condition fails and the remaining statements inside the method will be aborted.

Example:
@Test
public void hardAssert(){
	System.out.println("hardAssert Method Was Started");
	Assert.assertTrue(false);
	System.out.println("hardAssert Method Was Executed");
}
	
Soft Assert – Soft Assert collects errors during @Test. Soft Assert does not throw an exception when an assert fails and would continue with the next step after the assert statement.

If there is any exception and you want to throw it then you need to use assertAll() method as a last statement in the @Test and test suite again continue with next @Test as it is.

Example :
@Test
public void softAssert(){
	SoftAssert softAssertion= new SoftAssert();
	System.out.println("softAssert Method Was Started");
	softAssertion.assertTrue(false);
	System.out.println("softAssert Method Was Executed");
	softAssertion.assertAll();
}

---------------------------------------------------------------------------------------------------------------------------------------------------

## TestNG Annotations
TestNG Annotation	Description
@BeforeSuite	The @BeforeSuite annotated method will run before the execution of all the test methods in the suite.
@AfterSuite	The @AfterSuite annotated method will run after the execution of all the test methods in the suite.
@BeforeTest	The @BeforeTest annotated method will be executed before the execution of all the test methods of available classes belonging to that folder.
@AfterTest	The @AfterTest annotated method will be executed after the execution of all the test methods of available classes belonging to that folder.
@BeforeClass	The @BeforeClass annotated method will be executed before the first method of the current class is invoked.
@AfterClass	The @AfterClass annotated method will be invoked after the execution of all the test methods of the current class.
@BeforeMethod	The @BeforeMethod annotated method will be executed before each test method will run.
@AfterMethod	The @AfterMethod annotated method will run after the execution of each test method.
@BeforeGroups	The @BeforeGroups annotated method run only once for a group before the execution of all test cases belonging to that group.
@AfterGroups	The @AfterGroups annotated method run only once for a group after the execution of all test cases belonging to that group.




## Sample TestNG TestNG

package day1;  
import org.testng.annotations.Test;  
  
public class module1{  
    @Test  
    public void test1(){  
        System.out.println("Hello javaTpoint!!");  
    }  
      
    @Test  
    public void test2(){  
        System.out.println("JTP Travels");  
    }
}  

package day1;  
  
import org.testng.annotations.Test;  
  
public class module2{  
  @Test  
  public void test3(){  
      System.out.println("hindi100.com");  
  }  
}  


## Sample TestNG.xml file
<?xml version="1.0" encoding="UTF-8"?>  
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd">  
<suite name="loan_department">  
  <test name="Personal_loan">  
    <classes>  
      <class name="day1.module1"/>  
      <class name="day1.module2"/>  
    </classes>  
  </test> <!-- Test -->  
</suite> <!-- Suite -->


## TestNG Parameter
1. @Test(enabled=false)   /   @Test(enabled=true)
2. @Test(groups= {"SmokeTest"}), @Test(groups= {"Group A","Group B"})  
3. @Test(description="This is testcase1")  
4. @Test(dependsOnMethods= {"WebStudentLogin"})  
5. @Test(priority=2)  
6. @Test(timeOut=200)  
7. @Test(dependsOnGroups= {"security","database"})
8. @Parameters({"a","b"})  


## TestNG Listeners

ITestListener Interface

@Override  
public void onTestStart(ITestResult result) {  

}  
  
@Override  
public void onTestSuccess(ITestResult result) {  

System.out.println("Success of test cases and its details are : "+result.getName());  
}  
  
@Override  
public void onTestFailure(ITestResult result) {  
 
System.out.println("Failure of test cases and its details are : "+result.getName());  
}  
  
@Override  
public void onTestSkipped(ITestResult result) {  

System.out.println("Skip of test cases and its details are : "+result.getName());  
}  
  
@Override  
public void onTestFailedButWithinSuccessPercentage(ITestResult result) {  
  
System.out.println("Failure of test cases and its details are : "+result.getName());  
}  
  
@Override  
public void onStart(ITestContext context) {  
 
}  
  
@Override  
public void onFinish(ITestContext context) {  

}  




