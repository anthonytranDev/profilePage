-------------------------------------------------------------------------------------
Improvements
-------------------------------------------------------------------------------------
Research what is already available out there, such native functions and objects of the language
File size vs File processing time
Sound/Noise
> REFACTOR - May consider creating a calculator object, reducing the code base further
> TESTING - 
    landing - Should test out nice mocha features "landing", test progress bar.
    dot - test you approximately where all the test are

-------------------------------------------------------------------------------------
Doc Info - 30/09/2017 - 00:24
-------------------------------------------------------------------------------------

WEB DESIGN

Managed to complete the footer and lander of the app, nows to fill it with content, such as
my projects.

Things for tomorrow

Hidden Messages and inferences to notice, the analogy of Rick falling, also seems like he jumping, 
straight onto the page. It would be great if I can 

TASKS
> see if I can take nice pictures of other project - ahem makesure they do not consist of white borders on the top;
Would be great if we can find a subtle way to show the additional meta data of each project. Such as it's name, 
stage of completion, alpha tags, completed tags etc . Also I still think it would be nice to split the project a bit
more spaced out - more standoffish
> Complete the panel at the bottom of each character, include languages and tools used if used, frameworks and libraries.
Sorta like Evernote taxonomy, but more meaning full as developers and non-developers can understand from the layout

> I really feel I need more space for the project section, after getting rid of all of the whitespace, need see if more
space for this session is necessary

> Being thinking a separate media query for 1024 is required, what if someone wants to go half screen;

Bug Fixes
> Images of projects are squeezed even at 1366px, so need to find a way to keep them intact -> keep them to specific size
> If I could find a way to over these characters up with that would be great
-------------------------------------------------------------------------------------
Doc Info - 26/09/2017 - 02:09
-------------------------------------------------------------------------------------

-----------------------------
Doc Info - 26/09/2017 - 02:09
-----------------------------

APP DEVELOPMENT

Nearly completed the Morty leveling up system, really happy that I was able to pull it off.
Improvements to be made:
> Transition of images to smoother

Plan:

Need to start tidying up and planning things

UX decisions:

> Level 0 was used instead of level 1, as it forces the player to want to level up,
> Deciding to leave the initial progress circle in to encourage as well make the leveling system more intuitive; making
it disappear by scrolling up including the "Average Morty" name tag, would make the entire process less intuitive for the user.


Documentation

Reasons making this application:

A version of application already exists, so I have a form of a benchmark I can use to see how good my application is compared to an existing one. In this case it's the "Google Calculator Search Application"

Now use cases will now be prioritised into groups


    1) Basic functionality
    -----------------------------------------------------------------------------
    - utilize the equals button, to return an answer
    - use answer button to get the previous answer stated from before   
    - use the backspace key
        a) to delete the previous value, if I already entered that value; acts like CE on any other calculator: 123 -> 12, 4ln(5) -> 4ln(5
        b) to delete the entire value, after I have pressed the equals button; acts like the AC on any other calculator: 123 -> ""  , the "" depicts an empty string
    - do basic arithmetic on the calculator, and it should be a numerical value
    - use brackets to alter the precedence of the equation

    2) Conversion and Basic Operation, and constants
    -----------------------------------------------------------------------------
    - convert radians to degree, vice versa, simply by clicking on the Rad/Deg toggle: 1 Radian -> 180/pi
    - change return the factorial of a number: 5! -> 120
    - convert percentage value to a numerical value: 150% -> 1.5
    - use e button to get the constant of e: 2.718281
    - use pi button to get the constant of pi: 3.14159

    3) Passing numerical values through more complicated functions
    -----------------------------------------------------------------------------
    - use sine button to calculate the value of sin(x): Degrees is toggled on, sin(360) -> 0
    - use natural-log button to calculate the value of ln(x): ln(e) -> 1;
    - use cosine button to calculate the value of cos(x): Degress is toggled on, cos(360) -> 1
    - use logarithm button to calculate the value of log(x): log(10) -> 1;
    - use tangent button to calculate the value of tan(x): tan(45) -> 1;

    4) Power, exponents and square root
    -----------------------------------------------------------------------------
    - use square root to calculate the value of x^1/2: 4^1/2 -> 2;
    - use exponential button to raise the exponent of base 10 10^y: 10^3 -> 1000;
    - use power button to raise the exponent of any base x^y: 2^10 -> 1024;



------------------------------------------------------------------------------------
Simple Plan
-------------------------------------------------------------------------------------
Remember:
Main Aim - is to replicate the entire calculator to the best of my ability

- Configure a html and css clone of the Google Calculator
- The order of precedence is seen as the biggest problem, the plan is do a few mathematical sum at the start, using a plethera of values from the buttons, to mix and match possible calculations
- Current logic architecture
    - Create a file system where you can;
        - a file individual functions that can calculate the value
        - a file to takes able to take into the value and process
    - How each value will be processed
        - Buttons assigned events
            - describes how each button transcribes and store values in state
                - [Any value/except equals, backspace, rad|deg, ans] button -> inputs a value into state that are recognisable by regex
                - [equal] button is pressed -> state is casted into a string, regex is used to recognise specific parts of the string; regex will be used over and over again.
                Where the highest order of precedence is detected by regex, and values converted to numerical values. -> this process occurs again, until every value is
                converted to a string that can be processed by eval
                - [backspace] button (below is copied and pasted from user stories, with some alterations)
                    a) to delete the previous value, if I already entered that value; acts like CE on any other calculator: 123 -> 12, 4ln(5) -> 4ln(5
                    b) to delete the entire value, after I have pressed the equals button; acts like the AC on any other calculator: 123 -> ""  , the "" depicts an empty string
                - [rad|deg]toggle -> detects the use of sin, cos, tan, the alters the values within it's brackets
                - [ans] button -> returns ans values on the screen and us -> places it back into state
            - how those values will recognised by regex. Make it easier in sense where, if additional functionality, i.e. buttons were added, then how will this button fit into the applications
        - Precedence of each function over another
        - The end string state, must be able to process by eval, to spit out an answer
- Enter tests for the entire calculator

Discoveries
- Whenever you input specific values, the value of precedent also depends on whether the value is left of the operator such as 5! or 5%