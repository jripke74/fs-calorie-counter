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