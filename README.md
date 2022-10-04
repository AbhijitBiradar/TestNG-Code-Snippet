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


