# Python List Exercises

Try these short programs to get some firsthand experience with<br/>
Python's lists. You might want to create a new folder for each<br/>
chapter's exercises to keep them organized.<br/>

## Chapter 3 - Lists

### Exercise 3-1. Names
Store the names of a few of your friends in a list called names. <br/>
Print each person's name by accessing each element in the list, one <br/>
at a time.<br/>

### Exercise 3-2. Greetings
Start with the list you used in Exercise 3-1, but instead of just <br/>
printing each person's name, print a message to them. The text of <br/>
each message should be the same, but each message should be <br/>
personalized with the person's name.<br/>

### Exercise 3-3. Your Own List
Think of your favorite mode of transportation, such as a motorcycle <br/>
or a car, and make a list that stores several examples. Use your <br/>
list to print a series of statements about these items, such as <br/>
"I would like to own a Honda motorcycle."<br/>

*The following exercises are a bit more complex than those in <br/>
Chapter 2, but they give you an opportunity to use lists in all <br/>
of the ways described.*<br/>

### Exercise 3-4. Guest List
If you could invite anyone, living or deceased, to dinner, who <br/>
would you invite? Make a list that includes at least three people <br/>
you'd like to invite to dinner. Then use your list to print a <br/>
message to each person, inviting them to dinner.<br/>

### Exercise 3-5. Changing Guest List
You just heard that one of your guests can't make the dinner, so <br/>
you need to send out a new set of invitations. You'll have to <br/>
think of someone else to invite.<br/>

- Start with your program from Exercise 3-4. Add a print() call at <br/>
  the end of your program stating the name of the guest who can't <br/>
  make it.
- Modify your list, replacing the name of the guest who can't make <br/>
  it with the name of the new person you are inviting.<br/>
- Print a second set of invitation messages, one for each person who <br/>
  is still in your list.

### Exercise 3-6. More Guests
You just found a bigger dinner table, so now more space is available. <br/>
Think of three more guests to invite to dinner.<br/>

- Start with your program from Exercise 3-4 or Exercise 3-5. Add a <br/>
  print() call to the end of your program informing people that you <br/>
  found a bigger dinner table.<br/>
- Use insert() to add one new guest to the beginning of your list.
- Use insert() to add one new guest to the middle of your list.
- Use append() to add one new guest to the end of your list.
- Print a new set of invitation messages, one for each person in <br/>
  your list.

### Exercise 3-7. Shrinking Guest List
You just found out that your new dinner table won't arrive in time <br/>
for the dinner, and you have space for only two guests.

- Start with your program from Exercise 3-6. Add a new line that <br/>
  prints a message saying that you can invite only two people for <br/>
  dinner.
- Use pop() to remove guests from your list one at a time until only <br/>
  two names remain in your list. Each time you pop a name from your <br/>
  list, print a message to that person letting them know you're sorry <br/>
  you can't invite them to dinner.
- Print a message to each of the two people still on your list, <br/>
  letting them know they're still invited.
- Use del to remove the last two names from your list, so you have <br/>
  an empty list. Print your list to make sure you actually have an <br/>
  empty list at the end of your program.

### Exercise 3-8. Seeing the World
Think of at least five places in the world you'd like to visit.<br/>

- Store the locations in a list. Make sure the list is not in <br/>
  alphabetical order.
- Print your list in its original order. Don't worry about printing <br/>
  the list neatly, just print it as a raw Python list.<br/>
- Use sorted() to print your list in alphabetical order without <br/>
  modifying the actual list.
- Show that your list is still in its original order by printing it.
- Use sorted() to print your list in reverse alphabetical order <br/>
  without changing the order of the original list.
- Show that your list is still in its original order by printing it <br/>
  again.
- Use reverse() to change the order of your list. Print the list to <br/>
  show that its order has changed.
- Use reverse() to change the order of your list again. Print the <br/>
  list to show it's back to its original order.
- Use sort() to change your list so it's stored in alphabetical <br/>
  order. Print the list to show that its order has been changed.
- Use sort() to change your list so it's stored in reverse <br/>
  alphabetical order. Print the list to show that its order has <br/>
  changed.

### Exercise 3-9. Dinner Guests
Working with one of the programs from Exercises 3-4 through 3-7, <br/>
use len() to print a message indicating the number of people you <br/>
are inviting to dinner.

### Exercise 3-10. Every Function
Think of something you could store in a list. For example, you <br/>
could make a list of mountains, rivers, countries, cities, <br/>
languages, or anything else you'd like. Write a program that <br/>
creates a list containing these items and then uses each function <br/>
introduced in this chapter at least once.

### Exercise 3-11. Intentional Error
If you haven't received an index error in one of your programs yet, <br/>
try to make one happen. Change an index in one of your programs to <br/>
produce an index error. Make sure you correct the error before <br/>
closing the program.
