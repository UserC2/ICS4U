# Inversion of Control
**April 3, 2024**

## Pizza
Imagine you are ordering pizza:
* You tell Domino's pizza: "I want a cheese pizza, delivered to 54 Westmount Rd."
* Domino's makes the pizza, and then delivers it to the address you specified.

You don't care what type of oven they have, or how high they throw the dough, or several other parts of the pizza making process, so Domino's takes care of it.
* Similar to the concept of "abstraction".

However, sometimes it would be useful to specify some parts of the pizza-making process:
* Religious requirements (e.g. Halal meat)
* Dietary restrictions (e.g. gluten-free)

To cater to the most customers as possible, Domino's would have to comply with these requirements.
* This would require staff familiar with all these requirements (which would be impractical with a large amount of allergies and religious requirements).

The entity in control of the pizza making process looks like this normally:
* You decide whether to call Domino's or not.
* When you call Domino's, control transfers to them.
* Control returns to you once the pizza is delivered.

However, Domino's would like to save money by reducing the amount of training required for employees, so instead, Domino's allows you to specify the parts of the pizza-making process according to your requirements instead of having staff familiar with them.
* Once Domino's makes your pizza, they ask you to confirm the pizza is acceptable before delivering it.

Now, the entity in control of the pizza looks differently:
* You decide whether to call Domino's or not.
* When you call Domino's, control transfers to them.
  * Control returns to you when they ask you to verify the pizza is completed correctly.
  * Once you verify the pizza is acceptable, control returns to Domino's so they can deliver the pizza.
* Control returns to you once the pizza is delivered.
* Control has been "inverted": Instead of Domino's having complete control over the pizza-making process, the caller has control.

Similarly, computer programs can *delegate* some of their responsibilities: They can take an important part of an algorithm (such as tasting a pizza) and allow the caller to provide a function to use in place it.
* *Function pointers* (or *callbacks*) can be used to provide this functionality.
* C# has [*Delegates*](https://learn.microsoft.com/en-US/dotnet/csharp/programming-guide/delegates/) to provide this functionality (more advanced function pointers).

### Why Delegate Responsibilites?
Imagine you want to connect a lamp to a switch.
* You solder the lamp to the switch to connect them.

This approach has a problem: You can't use the switch for anything else—It only works with the lamp (without modifying the wiring).
* This makes the switch *tighly-coupled* to the lamp—it can't be used with anything else.

A better approach would be to wire the switch to an outlet, which allows it to be used with any appliance with an outlet.
* Now, the switch is *generic*—it can be used with anything compatible with an outlet.

Likewise, a computer program can reduce its complexity (and improve its usability) by making things generic instead of tightly-coupled.