## CSS
[Back to Table of Contents](../README.md)

The first thing that should be noted about CSS is the fact that it is not very maintainable in nature, at least not pure CSS.

Files get too long, selectors get too convoluted, and duplication can be a nightmare to identify or debug.
Pure CSS lends to the over-use of the misunderstood rule "!important".

This is where CSS specific tools can be invaluable.

The first concern should be CSS architecture, how do we structure our CSS in our application, and what methodologies are we using?

The concept of Atomic design presents an interesting solution to this problem.

### Atomic Design

#### What is it?

The problem that Atomic Design is trying to solve is two part; 1. create a rational and sensical way to structure project architecture, which, 2. can be used to effectively build components in a maintainable, and compositional manner.

The elements of Atomic Design are as follows:
1. Atoms - Smallest/Dumbest components representing the simplest form of a component (E.g. Label, Input, Button, etc.).
2. Molecules - Components composed of Atoms bonded together to describe something more meaningful (E.g. A Search component, which might be made up of a Label, Input, and Button).
3. Organisms - Components composed of Molecules bonded together to create building blocks for sections (E.g. Header containing Logo, Menu, and Search).
4. Templates - The combination of Organisms used to create pages, and therefore are also comparable to bluprints for a page.
5. Pages - Instances of Templates

If you would like to read more about Atomic Web Design, please visit Brad Frost's (The founder) website detailing the methodology.

Link: [Atomic Web Design by Brad Frost](http://bradfrost.com/blog/post/atomic-web-design/)

This guide does not detail the implementation or theory of Atomic Web Design, as we believe that designers and developers should only take what they need from a toolbox.

#### How does this help me?

The most useful tools that I've found within the Atomic Design methodology is that it lends to assisted component scaffolding, development, and maintenance.

Now instead of placing everything into a style.css file and searching for 5 to 10 minutes for what you are looking for, you can find what you're looking for instantly.

This is what we want! Otherwise it's not LIFT compliant.

How do we do this? Imagine you have a component you want to build, let's say that it's a calendar.

Instead of starting with the calendar, you can instead start with the smallest and dumbest parts of the calendar, then work your way up.

