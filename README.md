# tui engine real

tui engine is an interpreted scripting language (aids), and it's the first programming language i've ever made (real)

## syntax:
pretty simple syntax, similar to batch or someshit

### chirp
chirp will print all arguments provided to the console
**e.g:**
source:

    chirp hello

output:
> hello

source:

    chirp deez nuts

output:
> deez nuts

pre simple

### jump
jump will skip execution over to a different line, which is useful for loops or simple "functions", if you could call it that.

**e.g.**

source:

    chirp hello
    jump 4
    chirp this line is skipped!
    chirp this line is jumped to!

output:
> hello
> this line is jumped to!

source:

    chirp this is an endless loop!
    jump 1

output:
> this is an endless loop!
> this is an endless loop!
> this is an endless loop!
> this is an endless loop!
> *... and so on*

### check
essentially a simple if statement, currently supporting two operators "is" and "isnt".
any code put immediately infront will be executed if the conditions are met.

for example:

source:

    check 123 is 123 chirp yes it is

output:
> yes it is

source:

    check 123 isnt 1234 jump 3
    chirp if it were, this would be run
    chirp but it isn't, so this is run!

output:
> but it isn't, so this is run!

### setvar

variables, how exciting

should be easy to understand:

source:

    setvar variablename 123
    chirp ^variablename

output:
> 123

when defining or editing a variable as an input to a function, you just put the variable's name.
If you are referencing a variable and want it's value, you add ^ to the start of it's name.

### add

pretty similar to setvar, however it adds an integer value to an integer that is pre-defined

example:
here is a simple loop that runs 10 times, using both the add and setvar statements:

source:

    setvar i 0
    add i 1 
    chirp ^i
    check ^i is 10 jump 6 
    jump 2
    chirp done

output:
> 1
> 2
> 3
> 4
> 5
> 6
> 7
> 8
> 9
> 10
> done

### varinput

source:

    setvar test deez
    chirp ^test
    varinput test new value:
    chirp ^test

output:
> deez
> new value: nuts
> nuts

u should be able to work out the rest of this from here

## http requests *(fancy)*

### httpget

source:

    setvar url https://api64.ipify.org/
	setvar data null
	chirp ^url
	httpget data ^url
	chirp ^data

output:
> https://api64.ipify.org/
> 123.123.123.123


### httppost

source:

    setvar result null
	setvar url http://example.com/
	setvar data "{"ligma":"balls"}"
	setvar contenttype "application/json"
	setvar timeout 5000
	httppost result ^url ^data ^contenttype ^timeout
	chirp ^result

output:
> blah blah blah whatever it responds with u aren't a baby bruv


