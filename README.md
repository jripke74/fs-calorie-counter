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