# Writing Clean Code

Writing `clean`, `understandable`, and `maintainable` code is a skill that is crucial for every developer to master.

In this `readme`, we will look at the most important principles to improve code quality and I will give you code examples for each of them.

Most examples are taken from `Robert J. Martin's` Clean Code. It is a programming classic and I suggest you read the whole text when you have time.

## How to Name Variables (and other things)
> "There are only two hard things in Computer Science: cache invalidation and naming things." – Phil Karlton

There is a reason why we do not use memory addresses and have names instead: names are much easier to recall. And, more importantly, they can give you more information about the variable, so someone else can understand its significance.

It can take some time to find a good name but it will save you and your team even more time in the future. And I am sure most readers have faced the situation where you visit your code only a few months later and have a hard time understanding what you did before.

### How to Create Meaningful Names
Do not use comments to explain why a variable is used. If a name requires a comment, then you should take your time to rename that variable instead of writing a comment.

#### Bad

```js
var d; // elapsed time in days
```
I have seen this type of code so many times. It is a common misconception that you should hide your mess with comments. Do not use letters like x, y, a, or b as variable names unless there is a good reason (loop variables are an exception to this).

#### Good
```js
var elapsedTimeInDays;
var daysSinceCreation;
var daysSinceModification;
```

### Avoid Disinformation
Be careful about words that mean something specific. Do not refer to a grouping of accounts as accountList unless its type is actually a List. The word has a specific meaning and it may lead to false conclusions.
Even if the type is a list, accounts is a simpler and better name.

#### Bad:

```js
var accountList = [];
```
#### Good:

```js
var accounts = []
```

### Avoid Noise Words
Noise words are the words that do not offer any additional information about the variable. They are redundant and should be removed.

Some popular noise words are:

- The (prefix)
- Info
- Data
- Variable
- Object
- Manager

If your class is named UserInfo, you can just remove the Info and make it User. Using BookData instead of Book as class name is just a no-brainer, as a class stores Data anyways.

You can also read Jeff Atwood's blog post about SomethingManager naming [here](https://blog.codinghorror.com/i-shall-call-it-somethingmanager/).


### Use Pronounceable Names
If you can't pronounce a name, you can't discuss it without sounding silly.

#### Bad:
```js
const yyyymmdstr = moment().format("YYYY/MM/DD");
```

#### Good:
```js
const currentDate = moment().format("YYYY/MM/DD");
```

### Use Searchable Names
Avoid using magic numbers in your code. Opt for searchable, named constants. Do not use single-letter names for constants since they can appear in many places and therefore are not easily searchable.

#### Bad:

```js
if (student.classes.length < 7) {
   // Do something
}
```

#### Good:

```js
if (student.classes.length < MAX_CLASSES_PER_STUDENT) {
    // Do something
}
```

This is much better because `MAX_CLASSES_PER_STUDENT` can be used in many places in code. If we need to change it to 6 in the future, we can just change the constant.

The bad example creates question marks in the reader's mind, like what is the importance of 7?

You should also make use of your language's constant naming and declaration conventions such as private static final in `Java` or `const` in `JavaScript`.

## Conclusion
Clean coding is not a skill that can be acquired overnight. It is a habit that needs to be developed by keeping these principles in mind and applying them whenever you write code.

Read more about writing clean code from this [blog article](https://www.freecodecamp.org/news/clean-coding-for-beginners/)
