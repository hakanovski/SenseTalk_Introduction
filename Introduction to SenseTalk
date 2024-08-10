# SenseTalk Tutorial Series

## Introduction to SenseTalk

### What is SenseTalk?
SenseTalk is a high-level scripting language used in Eggplant Functional, a tool designed for automated testing. It is known for its natural language-like syntax, which makes it approachable for testers and developers alike. SenseTalk enables users to interact with applications via their graphical user interfaces (GUIs), making it ideal for functional testing across a variety of platforms.

### Key Features of SenseTalk
- **Natural Language Syntax:** The syntax is designed to be intuitive and easy to read, similar to plain English.
- **Powerful Image Recognition:** SenseTalk excels in automating GUI interactions by recognizing images and visual elements.
- **Cross-Platform Testing:** It supports testing on multiple platforms, including desktop, web, and mobile applications.
- **Data-Driven Testing:** SenseTalk allows for easy integration of data-driven testing scenarios, enhancing test coverage.

---

## Chapter 1: Getting Started with SenseTalk

### Setting Up Your Environment
Before writing your first script, ensure that you have Eggplant Functional installed. This tutorial assumes that you have a basic understanding of how to navigate the Eggplant Functional interface.

### Your First SenseTalk Script
Let's start by writing a simple script that performs a basic task: opening a web browser and navigating to a specific URL.

```sensetalk
// Open the browser
Start "Chrome"

// Navigate to a URL
TypeText "http://www.example.com", Return

// Wait for the page to load
WaitFor 10, "ExamplePageImage"

// Validate that the correct page has loaded
If ImageFound("ExamplePageImage")
    Log "Page loaded successfully!"
Else
    LogError "Failed to load the page."
End If

Explanation:

	•	Start "Chrome": This command launches the Chrome browser.
	•	TypeText "http://www.example.com", Return: This types the URL into the browser’s address bar and presses Enter.
	•	WaitFor 10, "ExamplePageImage": Waits up to 10 seconds for a specific image (which you’ve captured and named “ExamplePageImage”) to appear on the screen.
	•	If ImageFound("ExamplePageImage"): Checks if the expected image is found on the page, logging success or failure accordingly.

Running Your Script

	1.	Open Eggplant Functional.
	2.	Copy the script above into a new script file.
	3.	Run the script by clicking the “Run” button.

Chapter 2: Variables and Data Handling in SenseTalk

Declaring and Using Variables

Variables in SenseTalk are declared with the put command. Let’s see how to use variables:

// Declare a variable
put "Hello, World!" into greeting

// Use the variable
Log greeting

Explanation:

	•	put "Hello, World!" into greeting: This creates a variable named greeting and assigns it the value “Hello, World!”.
	•	Log greeting: This logs the value of greeting to the output.

Working with Lists and Property Lists

SenseTalk allows you to work with lists and property lists (dictionaries):

// Create a list
put ("apple", "banana", "cherry") into fruitList

// Access an item from the list
put fruitList's first item into firstFruit
Log firstFruit

// Create a property list
put (name:"John", age:30, occupation:"Tester") into person

// Access a property
Log person’s name

Explanation:

	•	Lists: Ordered collections of items. You can access items using their position in the list.
	•	Property Lists: Collections of key-value pairs, similar to dictionaries in other languages.

Chapter 3: Control Structures in SenseTalk

Conditionals

SenseTalk supports traditional conditional structures such as if, else, and switch:

put 10 into number

if number > 5
    Log "Number is greater than 5"
else
    Log "Number is 5 or less"
end if

Explanation:

	•	if number > 5: This checks whether the value stored in number is greater than 5.
	•	Log: Depending on the condition, either “Number is greater than 5” or “Number is 5 or less” is logged to the console.
	•	else: This block runs if the if condition is not met.

Switch Statement

The switch statement is another useful control structure for handling multiple conditions based on the value of a single variable:

put "banana" into fruit

switch fruit
    case "apple"
        Log "It's an apple."
    case "banana"
        Log "It's a banana."
    case "cherry"
        Log "It's a cherry."
    default
        Log "It's an unknown fruit."
end switch

Explanation:

	•	switch statement: Evaluates the value of fruit and runs the corresponding case block.
	•	default case: Runs if none of the specified cases match the value of fruit.

Loops

Loops allow you to repeat a block of code multiple times. SenseTalk supports various types of loops.

Repeat with Each Loop:

put ("apple", "banana", "cherry") into fruitList

repeat with each fruit in fruitList
    Log "Fruit: " & fruit
end repeat

	•	Explanation:
	•	repeat with each: This loop iterates over each item in fruitList and logs it.

Repeat with a Condition:

put 5 into counter

repeat while counter > 0
    Log "Counter is " & counter
    subtract 1 from counter
end repeat

	•	Explanation:
	•	repeat while: The loop continues as long as the condition (counter > 0) is true.
	•	subtract 1 from counter: Decrements the counter by 1 in each iteration.

Repeat a Fixed Number of Times:

repeat 3 times
    Log "This message will be logged three times."
end repeat

	•	Explanation:
	•	repeat X times: Repeats the enclosed block of code a fixed number of times.

Chapter 4: Advanced Topics

Image Recognition and Interaction

SenseTalk’s ability to interact with visual elements is one of its most powerful features. Let’s explore how to automate UI interactions using image recognition.

Clicking on an Image:

// Clicks on the image of a button
Click "SubmitButton"

	•	Explanation:
	•	Click "SubmitButton": This command searches for an image named “SubmitButton” and clicks on it. The image should be captured and stored in Eggplant Functional’s suite.

Waiting for an Image:

// Waits for up to 15 seconds for the image to appear
WaitFor 15, "LoadingIcon"

	•	Explanation:
	•	WaitFor 15, "LoadingIcon": Pauses the script for up to 15 seconds, waiting for the image “LoadingIcon” to appear on the screen.

Verifying the Presence of an Image:

// Checks if an image is present on the screen
if ImageFound("SuccessMessage")
    Log "Operation completed successfully."
else
    LogError "Operation failed."
end if

	•	Explanation:
	•	ImageFound: This function returns true if the specified image is found on the screen, enabling conditional logic based on the presence of UI elements.

Working with External Data

SenseTalk can interact with external data sources such as CSV files, databases, and even web services. Here’s how to read from a CSV file:

Reading Data from a CSV File:

// Define the file path
set filePath to "/path/to/data.csv"

// Read the CSV file
repeat with each record in file filePath
    Log "Record: " & record
end repeat

	•	Explanation:
	•	file filePath: Opens the specified file for reading.
	•	repeat with each record: Iterates over each line in the CSV file, treating it as a separate record.

Using Data in a Test Script:

// Define the file path and read the data
set filePath to "/path/to/users.csv"

repeat with each user in file filePath
    put user’s username into username
    put user’s password into password

    // Use the data to perform a login operation
    TypeText username, Tab, password, Return
    WaitFor 5, "Dashboard"

    if ImageFound("Dashboard")
        Log "Login successful for " & username
    else
        LogError "Login failed for " & username
    end if
end repeat

	•	Explanation:
	•	CSV Data: The script reads usernames and passwords from a CSV file and uses them to perform login operations, verifying the outcome for each user.

Chapter 5: Best Practices

Organizing Your Scripts

	•	Modular Design: Break your scripts into smaller, reusable modules. For example, create separate scripts for login, navigation, and verification steps, and call them as needed.
	•	Commenting: Always comment your code to explain what each part does. This is especially important in a collaborative environment.

Error Handling

SenseTalk allows you to manage errors gracefully:

try
    Click "NonExistentButton"
catch
    LogError "Button not found, continuing with the next steps."
end try

	•	Explanation:
	•	try...catch: This structure attempts to execute code in the try block and catches any errors that occur, allowing the script to continue running.

Debugging and Logging

Use Log and LogError statements generously to track your script’s execution and identify where issues arise:

Log "Starting the test..."
LogError "An unexpected error occurred."

Maintaining Image Libraries

	•	Consistency: Ensure your captured images are clear and representative of the elements they refer to. Avoid capturing unnecessary parts of the screen.
	•	Version Control: Keep track of your image libraries and update them whenever the UI changes.

