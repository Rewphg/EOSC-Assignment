# Assignment 1
## Building a Dynamic Shopping List
#### Instruction
Build a dynamic shopping list app that will test your knowledge of Vue by using all the basic functions of an SFC, such as expressions, loops, two-way binding, and event binding.

The application should let users create and delete individual list items and clear the total list in one click. The following steps will help you complete the assignment:

1.  Build an interactive form in one component using an input bound to v-Model.
2.  Add one input field that you can add shopping list items to. Allow users to add items by using the Enter key by binding a method to the @keyup.enter event.
3.  User can expect to clear the list by deleting all the items or removing them one at a time. To do so, you can use a delete method that can pass the array position as an argument, or simply overwrite the whole shopping list data property to be an empty array [ ].
