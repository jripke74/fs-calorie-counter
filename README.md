# fs-calorie-counter

Sometimes when you're coding a web application, you'll need to be able to accept input from a user. In this calorie counter workshop, you'll practice how to validate user input, perform calculations based on that input, and dynamically update your interface to display the results.

You'll also practice basic regular expressions, template literals, the addEventListener() method, and more.

Step 1
In this workshop, you'll learn to create a calorie counter form that enables users to input their daily calorie budget and the calorie counts of various meals. The form will then calculate and display whether the user is in a calorie deficit or surplus.

You have been provided with boilerplate CSS and HTML. However, you need to build your calorie counter form.

Feel free to explore the HTML and CSS, then add a form element and give it an id set to calorie-counter.

Step 2
In your form, users will be able to input a number which represents their daily calorie budget.

Create a label element, give it a for attribute set to budget and the text Budget, then create an input element with the id set to budget.

Step 3
Your input element needs some additional attributes. Give it a type set to number to only allow numeric inputs, a min attribute set to 0 to only allow positive numbers, and a placeholder set to Daily calorie budget.

Finally, mark the input element as required.

Step 4
In your form, users should have the capability to add various meal types along with their calorie counts.

Create a fieldset element with the id set to breakfast.

Within that element, create a legend with the text Breakfast, and an empty div with the class set to input-container.

Step 5
Next, create a fieldset element with the id set to lunch.

Within that element, create a legend element with the text Lunch, and an empty div with the class set to input-container.

Step 6
Continuing the pattern, create a fieldset for dinner with the same nested elements.

Step 7
You need two more of these fieldset code blocks – one for snacks and one for exercise.

Step 8
When users want to select a meal type to input their calorie counts, they should be presented with a dropdown menu and a button to add the meal type.

Start by creating a div element and assign it a class attribute with the value controls. Then, nest a span element inside this div.

Step 9
In your span element, create a label element for an entry-dropdown and give it the text Add food or exercise:. Then create a select element with the id set to entry-dropdown and a name set to options. Below that, add a button element with the id set to add-entry and the text Add Entry.

Give your button element a type attribute set to button to prevent automatic form submission.

Step 10
Your select menu needs options for each of the food and exercise fieldset elements you created in the previous steps. Use the option element to create a new option for each fieldset. The value attribute of each option should be the id of the fieldset, and the text of each option should be the text of the legend.

Set the Breakfast option as the selected option.

Step 11
Create another div element. Within it, nest a button to submit the form. This button should have the text Calculate Remaining Calories.

Then add a button with the id set to clear to clear the form (don't forget to give it a type attribute that prevents it from submitting the form). This button needs the text Clear.

Step 12
Your form needs somewhere to display the results. Add an empty div element and give it an id of output and the class values of output and hide.

Step 13
Finally, you need to link your JavaScript file to your HTML. Create a script element to do so.

Step 14
It is time to start writing the script that makes your form work.

To access an HTML element with a given id name, you can use the getElementById() method. Here's an example of how to use this method:

Example Code
<h1 id="title">Main title</h1>
Example Code
const mainTitleElement = document.getElementById('title');
Begin by getting the form element (using the id) and storing it in a variable called calorieCounter.

Step 15
Get your #budget element and assign it to budgetNumberInput, and your #entry-dropdown element and assign it to entryDropdown.

Step 16
Following the same pattern, assign your #add-entry element to addEntryButton, your #clear element to clearButton, and your #output element to output.

Step 17
In programming, prefixing a variable with is or has is a common practice to signify that the variable represents a boolean value.

Here are a few examples:

Example Code
let isRunning = true;
let hasCompleted = false;
Declare a variable named isError using let and initialize it with false, allowing for its reassignment later.

Later on in the project, you will update the value of isError if the user provides an invalid input.

Step 18
When the user inputs their daily calorie budget, the input field will only accept numerical values. However, if a number is entered with a + or - sign, you'll need to remove those characters.

Start by declaring a cleanInputString function that takes a str parameter.

NOTE: Values from an HTML input field are received as strings in JavaScript. You'll need to convert these strings into numbers before performing any calculations. Converting string values into numbers will be covered in a future step.

Step 19
To match specific characters in a string, you can use Regular Expressions or "regex" for short.

Regex in JavaScript is indicated by a pattern wrapped in forward slashes. The following example will match the string literal "hello":

Example Code
const regex = /hello/;
Declare a regex variable and assign it the value from the example above. In future steps, you will update this regex pattern to match specific characters needed for the calorie counter.

Step 20
The current pattern will match the exact text "hello", which is not the desired behavior. Instead, you want to search for +, -, or spaces. Replace the pattern in your regex variable with \+- to match plus and minus characters.

Note that you need to use the backslash \ character to escape the + symbol because it has a special meaning in regular expressions.

Step 21
In regex, shorthand character classes allow you to match specific characters without having to write those characters in your pattern. Shorthand character classes are preceded with a backslash (\). The character class \s will match any whitespace character. Add this to your regex pattern.

Step 22
Your current pattern won't work just yet. /+-\s/ looks for +, -, and a space in order. This would match +- hello but would not match +hello.

To tell the pattern to match each of these characters individually, you need to turn them into a character class. This is done by wrapping the characters you want to match in brackets. For example, this pattern will match the characters h, e, l, or o:

Example Code
const regex = /[helo]/;
Turn your +-\s pattern into a character class. Note that you no longer need to escape the + character, because you are using a character class.

Step 23
Regex can also take specific flags to alter the pattern matching behavior. Flags are added after the closing /. The g flag, which stands for "global", will tell the pattern to continue looking after it has found a match. Here is an example:

Example Code
const helloRegex = /hello/g;
Add the g flag to your regex pattern.

Step 24
JavaScript provides a .replace() method that enables you to replace characters in a string with another string. This method accepts two arguments. The first argument is the character sequence to be replaced, which can be either a string or a regex pattern. The second argument is the string that replaces the matched sequence.

Since strings are immutable, the replace method returns a new string with the replaced characters.

In this example, the replace method is used to replace all instances of the letter l with the number 1 in the string hello.

Example Code
"hello".replace(/l/g, "1");
Use your regex to replace all instances of +, -, and a space in str with an empty string. Return this value.

Step 25
Now it is time to test out your cleanInputString function.

Inside your cleanInputString function, add a console.log() statement with two arguments. The first argument should be the string "original string: " and the second argument should be the str parameter.

Step 26
To see the results from the cleanInputString function, you will need to add a console.log() statement. Inside that console statement, call the cleanInputString function with the string value of "+-99" as an argument.

Open up the console and you should see the original string followed by the cleaned string value with the +- removed.

Step 27
Once you have finished testing your cleanInputString function, you can remove both of your console statements.

Step 28
In HTML, number inputs allow for exponential notation (such as 1e10). You need to filter those out.

Start by creating a function called isInvalidInput – it should take a single str parameter.

Step 29
Declare a regex variable, and assign it a regex that matches the character e.

Step 30
The e in a number input can also be an uppercase E. Regex has a flag for this, however – the i flag, which stands for "insensitive".

Example Code
/Hello/i
The regex above would match hello, Hello, HELLO, and even hElLo because of the i flag. This flag makes your pattern case-insensitive.

Add the i flag to your regex pattern.

Step 31
Number inputs only allow the e to occur between two digits. To match any number, you can use the character class [0-9]. This will match any digit between 0 and 9.

Add this character class before and after e in your pattern.

Step 32
The + modifier in a regex allows you to match a pattern that occurs one or more times. To match your digit pattern one or more times, add a plus after each of the digit character classes. For example: [0-9]+.