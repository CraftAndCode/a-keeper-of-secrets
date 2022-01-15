## Step 0 @showDialog
Hello! Today we're going to use our knowledge of variables to make a device that keeps your secrets safe by protecting them with a passcode!

## Step 1 @showDialog
### What's our goal?

First, let's talk about what we need our program to do.

Our program should:
- Memorize a secret string of text
- Store a passcode and compare it with the button input
- Display the memorized text if the input and passcode match

Let's get to work!

## Step 2
### Step 1: Creating variables
First, let's create three variables by clicking the `|Make a Variable|` button in the ``||variables.variables||`` category. Let their names be ``||variables.My_secret||``, ``||variables.passcode||`` and ``||variables.input||``.

## Step 3 @showHint
### Step 2: Setting the variables' values
Now, let's set the initial values for your new variables. Remember to drag a ``||text." "||`` block on the right side of your ``||variables.set||`` blocks to make your variables store text. Also, leave the ``||variables.input||`` variable empty.
```blocks
let input = ""
let My_secret = "Your secret here"
let passcode = "ABBAB"
input = ""
```

## Step 4 @showHint
### Step 3: Logging button presses
Let's add code to log button presses. We'll start our code on the ``||input.on button pressed||`` event. If this event happens, we add a letter to the text inside our variable with the help of the ``||variables.set||`` and ``||text.join||`` blocks.
```blocks
input.onButtonPressed(Button.A, function () {
    input = "" + input + "A"
})
```

## Step 5 @showHint
### Step 3: Logging button presses
After assembling the code for the `A` button, write similar code for the `B` button. Now, every time a button is pressed, the corresponding letter will be added to the text stored in the ``||variables.input||`` variable.
```blocks
input.onButtonPressed(Button.A, function () {
    input = "" + input + "A"
})
input.onButtonPressed(Button.B, function () {
    input = "" + input + "B"
})
```

## Step 6 @showHint
### Step 4: Let's compare
In order for your program to compare two variables, we need to add an ``||logic.if||`` condition that ensures the code inside will be executed only if these two variables match.
```blocks
basic.forever(function () {
    if (passcode == input) {
    }
})
```

## Step 7 @showHint
### Step 5: Reveal the secret!
There is one last thing to do. Add instructions to display your secret when a condition is met and try downloading your program to the Micro:bit! Does your passcode work?
```diffblocks
basic.forever(function () {
    if (passcode == input) { 
    }
----------
basic.forever(function () {
    if (passcode == input) {
        basic.showString(My_secret)
    }
```

## Step 8 @showHint
### Now it's your turn!
Currently, our program doesn't have a way to erase the logged input if the wrong button is pressed. That means if you've made a mistake entering the passcode, the only way to start again is to turn the device off and on again.
  
Let's remove this bug. Add the code that sets the ``||variables.input||`` variable to be empty when both buttons are pressed simultaneously.

## @showDialog

### Answers: Now it's your turn!
This is the code to be added to the program.
```blocks
input.onButtonPressed(Button.AB, function () {
    input = ""
})
```

## Step 9
You've made a cool device that can store secrets! You can also use it to write messages that can be read only by those who know the passcode. Isn't that great?
