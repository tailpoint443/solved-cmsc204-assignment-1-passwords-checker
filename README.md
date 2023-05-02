Download Link: https://assignmentchef.com/product/solved-cmsc204-assignment-1-passwords-checker
<br>



Concepts tested by this program:

ArrayList

static

Read  Files

Javadoc

JUnit Tests

Exceptions




Create an application that will check for valid passwords.  The following rules must be followed to create a valid password.

<ol>

 <li>At least 6 characters long</li>

 <li>10 or more characters is a strong password, between 6 and 9 characters is a weak (but acceptable) password.</li>

 <li>At least 1 numeric character</li>

 <li>At least 1 uppercase alphabetic character</li>

 <li>At least 1 lowercase alphabetic character</li>

 <li>At least 1 special character</li>

 <li>No more than 2 of the same character in a sequence</li>

</ol>

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5119343d3d3e11606362">[email protected]</a> – OK

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="d4959595b6b694e5e6e7">[email protected]</a> – not OK

<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="acedcdcdceceec9d9e9f">[email protected]</a> – OK




<strong><u>Operation:</u></strong>

When the application begins, the user will be presented with a screen that states the above instructions for creating a password, two text entry boxes for typing in a password, and three buttons.

If the user wants to check a single password, they will type in the password in both boxes and select the “Check Password” button.

If the user wants to read in and check a list of passwords, they will select the “Check Passwords in File” button, be presented with a file explorer, and select the file to read from.  Those passwords that failed the check will be displayed, with their error message.

<strong><u>Specifications</u></strong>:

<strong>The Data Element</strong>

String

<strong>The Data Structure</strong>

ArrayList of Strings

<strong>Utility Class</strong>

<ol>

 <li>Create a PasswordCheckerUtility class based on the Javadoc given you.</li>

 <li>The PasswordCheckerUtility class will have at least three public methods:</li>

</ol>

<ul>

 <li>isValidPassword:</li>

</ul>

This method will check the validity of one password and return true if the password is valid and throw one or more exceptions if invalid.

<ul>

 <li>isWeakPassword:</li>

</ul>

This method will che throw an exception.

<ul>

 <li>getInvalidPasswords</li>

</ul>

This method will check an ArrayList of passwords and return an ArrayList with the status of any invalid passwords (weak passwords are not considered invalid).  The ArrayList of invalid passwords will be of the following format:

&lt;password&gt;&lt;blank&gt;&lt;message of exception thrown&gt;

<ul>

 <li>For each password requirement, you must have a static private method that validates the password for that requirement and throws an exception if invalid.</li>

</ul>

<ol start="3">

 <li>Create a separate exception classes for each exception listed in PasswordCheckerUtility Javadoc.</li>

</ol>

<strong>Hints:</strong>

<ul>

 <li>The GUI will check for the length of the password first, since that is the easiest and fastest check. Once the password fails one rule, there is no need to check the rest of the rules.</li>

 <li>To check for a special symbol, use the “regular expression” construct. Check the whole password, not just an individual character, using the following :</li>

</ul>

Pattern pattern = Pattern.compile(“[a-zA-Z0-9]*”);

Matcher matcher = pattern.matcher(str);

return (!matcher.matches());

<ul>

 <li>You will need to import Pattern and Matcher.</li>

 <li>Few helpful links on regular expression”</li>

 <li><a href="https://www.vogella.com/tutorials/JavaRegularExpressions/article.html">https://www.vogella.com/tutorials/JavaRegularExpressions/article.html</a></li>

 <li><a href="https://www.youtube.com/watch?v=rhzKDrUiJVk">https://www.youtube.com/watch?v=rhzKDrUiJVk</a></li>

 <li><a href="https://www.youtube.com/watch?v=sCuOJ8uadOg">https://www.youtube.com/watch?v=sCuOJ8uadOg</a></li>

</ul>




<strong>The GUI (provided):</strong>

The GUI has been provided, however you need to:

<ul>

 <li>The GUI will ask the user to enter the password and to re-type the password. If the two are not the same, inform the user.</li>

 <li>Use methods of PasswordCheckerUtility to check validity of one password when user clicks on “Check Password” button.</li>

 <li>Use methods of PasswordCheckerUtility to check validity of a file of passwords when user clicks on “Check Passwords in File” button.</li>

 <li>Use a FileChooser for the user to select the input file.</li>

 <li><u>Use try/catch structure to catch exceptions</u> thrown by PasswordCheckerUtility methods</li>

</ul>

<strong> </strong>

<strong>Exceptions</strong>

<u>Provide exception classes</u> for the following:

<ol>

 <li>Length of password is less than 6 characters (class LengthException)</li>

</ol>

Message – The password must be at least 6 characters long

<ol start="2">

 <li>Password doesn’t contain an uppercase alpha character (class NoUpperAlphaException)</li>

</ol>

Message – The password must contain at least one uppercase alphabetic character

<ol start="3">

 <li>Password doesn’t contain a lowercase alpha character (class NoLowerAlphaException)</li>

</ol>

Message – The password must contain at least one lowercase alphabetic character

<ol start="4">

 <li>Password doesn’t contain a numeric character (class NoDigitException)</li>

</ol>

Message – The password must contain at least one digit

<ol start="5">

 <li>Password doesn’t contain a special character (class NoSpecialCharacterException)</li>

</ol>

Message – The password must contain at least one special character

<ol start="6">

 <li>Password contains more than 2 of the same character in sequence (class InvalidSequenceException)</li>

</ol>

Message – The password cannot contain more than two of the same character in sequence.

<ol start="7">

 <li>Password contains 6 to 9 characters which are otherwise valid (class WeakPasswordException)</li>

</ol>

Message – The password is OK but weak – it contains fewer than 10 characters.

<ol start="8">

 <li>For GUI – check if Password and re-typed Password are identical (class UnmatchedException)</li>

</ol>

Message – The passwords do not match

Throw this exception from the GUI, not the utility class.




<strong>Note</strong>: If more than one error is present in a password, use the above order to throw exceptions.  For example, if a password is “xxyyzzwwaa$”, it fails rules 2 and 4 above.  Throw a NoUpperAlphaException, not a NoDigitException.




<strong>Student Junit methods</strong>:

<ul>

 <li>Use the file PasswordCheckerUtility.java</li>

 <li>Setup: include passwords that meet the below criteria.</li>

 <li>Teardown: set your student passwords ArrayList to null</li>

 <li>for each password requirement method in the PasswordCheckerUtility you must have a test case that passes and another one that fails</li>

</ul>




When you launch the GUI, this is what you will see.




If you select the button which reads “Check Passwords in File”, you will be presented with a file chooser.  You must navigate to where you stored the file “passwords.txt” and load it.  The file will be in the following format (one password per line):










Examples:







<ol>

 <li>No lowercase alphabetic character</li>

</ol>













Displayed to user:




<ol start="2">

 <li>No digit</li>

</ol>

Displayed to user:

<ol start="3">

 <li>If the password is OK, but between 6 and 10 characters, you will see:</li>

 <li>If password has more than two of the same characters in a row</li>

</ol>

Displayed to user:

<ol start="5">

 <li>If password is valid</li>

 <li>If the passwords do not match:</li>

</ol>

Displayed to user:

<ol start="6">

 <li>Based on the file above, when the user selects “Check Passwords in File”:</li>

</ol>

Displays errors to user when selecting Check Passwords in File. Note that valid passwords (including weak but otherwise valid passwords) are NOT displayed.
















<strong> </strong>

<u>Deliverables</u>:




<u>Design:</u>

Initial design document (UML and/or pseudo-code)




<u>Implementation:</u>

Final design document

Java files – The src folder with your driver (javafx application), data manager, exceptions and Junit Test (.java) files

Javadoc files – The entire doc folder with your javadoc for student generated files

Learning Experience document

GitHub screen shot

<em> </em>

<u>Deliverable format</u>: The above deliverables will be packaged as follows. Two compressed files in the following formats:

LastNameFirstName_AssignmentX.zip [compressed file containing following]:

doc [a directory] <em>include the entire doc folder with the javadoc for </em>

<em>student generated files</em>

file1.html (example)

file2.html (example)

class-use (example directory)

LearningExperience.doc <em>or other text format</em>

src [a directory] <em>contains your driver (javafx application), data manager, exceptions and Junit Test (.java) files</em>

File1.java (example)

File2.java (example)

File_Test.java (example)

<em>GitHub screen shot.</em>

LastNameFirstName_AssignmentX_<strong>Moss</strong>.zip [compressed file containing only]:

<em>.java file which includes the driver (javafx application), data manager, exceptions and Junit Test (.java) files – </em><em>NO </em>

<em>FOLDERS!!</em>

File1.java (example)

File2.java (example)


