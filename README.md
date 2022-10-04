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
