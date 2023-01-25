# INTRODUCTION - C PROGRAMMING

## History

## Syntax

```c
/** Preprocessor Directives
 * #include <library_file> usually header file with .h extension
 * #include "path_to_file.h"
 * Imorts external functions from a different source file
 * 
 **/

#include <stdio.h> // Include headers from standard I/O library: Single-line comments Style

/***
Statements are terminated with semi-colon(;)
Commenting Style:
	- Multi-line comment /**\/
	- Single lin comment //
	- Comments are tripped off during preprocessing

main function:
	C Program starts execution from the main function

***/

int main(int argc, char *argv[])			// main(): Entry point of C programs with command arguments
{
	char *hello_world = "Hello World!";		// Variable Declaration & Assignment: Character pointer (String)

	printf("%s\n", hello_world);			// Function invokation (printf from the stdio lib)

	return 0;								// Return statement from a function
}
```

## Compiling C Program
```bash
$ # Using GNU C Compiler (gcc)
$ gcc [compile_flag(s)] source_file(s) [-o output_name]

# Compile Flags (Switches)
# -o : output name (filename)
# -g : include debugging information
# -c : Object file
# -E : Preprocessed file
# -S : Produce assembly source
# -l object_file : link to an object file
```

## Variables & Data Types | Arrays | Format & Access Specifiers
```c
/***
VARIABLES & DATA TYPES
	An object that holds data (temporally). Some variables are constant i.e. the data it holds does not change. All variables are stored in memory.
	Variables must be declared and/or given be it can be used. Assigning a value can be done later.
	The type of a variable describes the type of information it can hold/store.

	i.e: variable_type variable_name [ = value ];

DATA TYPES
	* Character types
		- Character type: char & char *pointers (char array[])
	* Number types
	  	- Size of number type is machine dependent; check using the sizeof operator
		- Positive number & Negative number (signed): All numbers are signed by default
		- Positive ONLY (unsigned) and can be extended/shorten using long/short
		- The macro sizeof can be used to determine the size of some types
		- Integer types: short, int, long
		- Decimal floating-point types: float, double
		- double has higher precision
	* Boolean Type: True/False; 0 is False, Number > 0 is True

SCOPE OF VARIABLE
	- Variable(s) with global scope persist across all function calls
	- Global variables are defined at the beginning of the code outside of any function.
	- Can be read/written to by any function and the changes persists between functions
	- Local variable overrides global & local variables with same name

ARRAYS
	- Declaring an array: data_type array_name[Length] = {optional};
	- Index starts at 0: Size of an array Length - 1

FORMAT STRINGS
	- %c: Single Character
	- %s: String
	- %d: Decimal
	- %l: 
	- %f: Float
	- %x: Hexadecimal
	- %u: Unsigned decimal
	- %n: Number of bytes written
	- %p: shorthand for displaying pointers; equivalent to 0x%08x

	%d for decimals and %u for unsigned decimal and %x for hexadecimals
	%s is used to print strings; address of the string is passed 
	Minimum field width can be added right after the % sign of the format string
	Adding a 0 after the % sign pads it with 0s

ESCAPE SEQUENCE
	- \n: Newline
	- \t: Tab
	- \r: Carriage return
	- \f: Line feed
	- \a: Bell
	- \0: Null byte
***/

// Declare variable & Assigned variable
char *my_name = "Taufiq Gh";
unsigned int date_of_birth = 19111993;
char TRUE = '1';
float PI = 22/7;

// Arrays
char char_array[] = {'A', 'r', 'r', 'a', 'y', '\0'};
int numbers[5];											// Declared an array of 5 integers
int value = 10;


for(int i = 0; i < 5; i++) {							// Looping to populate an array
	numbers[i] = value * 2;								// Assigning values to an array
}
```

## Arithmetic Operators
```c
/***
## Arithmetic Operators

* Addition (+)
* Subtraction (-)
* Multiplication (*)
* Division (/)
* Modulo reduction (%): Remainder

- Increment operator (++): Eg: i = 0; i++; or ++i;
- Decrement operator (--): Eg: --i; i--;
- Arithmetic and assignment operator can be used to perform operation a variable store it into the variable.
***/

int a, b, c;
a = 2;
b = 4;
c = a + b;
c = b - a;
c = a * b;

float f, r;
f = a / b;
r = a % b;
```

## Conditional Operators
```c
/***
Conditional statements are based on some comparison operations

* Less than (<) 
* Greater than (>)
* Less than or equal to (<=)
* Greater than or equal to (>=)
* Equal to (==)
* Not Equal to (!=)
* 
***/

char res;
res = (a > b);
res = (a < b);
res = (a >= b); 
res = (a <= b);
```

## Logical Operator
```c
/***
use to chain comparison operations
group simple comparison operations into more complex statement(s).
* OR (||)
* AND (&&)
* 
***/

char b_;
b_ = (a > b) && (b < a);
b_ = (b > a) || (b < a);
```

## Control Structures

* If-Then-Else structure
```c
/***
 Changes program's execution from a simple sequencial order to a more complex and more useful flow.

If (condition) then
{
	Set of instruction to execute if condition is met;
}
Else
{
	Set of instruction to execute if condition is not met;
}

***/

if(a > b) {
	c = a;
}
else {
	c = b;
}
```

* Switch case Structure
```c
// Select/case statements is similar to if-then-else structure but works on integers only.
switch(a)
{
	case 4: c = a;
			break;
	case 3:
			c = b;
			break;
	default:
			c = 0;
}
```

* Loops
```c
/***
* While/Until Loops
Executes instructions more than onces (in a loop)
Requires condition on when to stop looping else to infinity

While (Condition is True)
{
	Statement(s) to execute when condition is met;
	// Instruction will be repeated till condition becomes false
}

Until loop is similar to While loop except that the condition is inverted
Until (Condition is false)
{
	Instructions to follow if condition is not met;
	// Repeat till condition becomes true

}
C does not support Until loop.
***/

int inc = 2;
while(true)
{
	if(inc != 10)
		continue;
	if(inc > 20)
		break;

	printf("Condition is true\n");
	inc += 2;
}

/***
* For Loops
Loops for a certain number of iterations: A while loop with a counter.

for(init_counter; condition; increment/decrement)
{
	Statement(s) to execute;
}
***/
```

* Break/Continue Keyword
```c
/***
Break/Continue statements
  - break: exit out of a loop
  - continue: skip an iteration
***/

for(int i = a; i < b; i++) {
	if(!a) {
		printf("Not %d", a);
		break;
	}
	else {
		continue;
	}
}
```

## Functions
```c
/***
Grouping instructions into smaller sub programs.
Can be used several times to avoid repeation of statements.

Function can take argument(s) and may return a value. 
A function that does not return anything is declared void
When a function is called, the statements or instructions found in it are executed

Function prototype
return_type function_name(optional arguments)
{
	Statements;

	return_value;
}

void function_name(optional args)
{
	Statement(s);
}

Eg: Function that returns factorial of a natural number.
***/

int factorial(int x)
{
	int i;
	for(i = 0; i < x; i++) {
		x *= i;
	}
	return x;
}

void print(int x)
{
	printf(x);
}

// Calling the function with an argument and a variable to store the return value.
int b = 2;
print(factorial(b));
```

## Pointers 
```c
/***
* Pointers
	- Can be defined and used like any other variable types
	- Points to a data of a type
	- Defined by prepending an asterick (*) to the variable name
	- Stores the address of the data it points to; the ampersand (&) operator attached to the pointer variable returns the address stored in the pointer.
	- The address-of operator (&) used to get (address) of a pointer points to
	- Deference operator (*) used to get the actual data a pointer points to
	- Void pointer is a typeless pointer defined by the void keyword i.e: void *ptr;
***/

char str_a[15];
char *char_ptr;		// Declaring char pointer

strcpy(str_a, "This is a pointer");
char_ptr = str_a;	// points char_ptr to the first byte of str_a
```

## Typecasting
```c
/***
* Typecasting
	- Temporally changing a variable datatype. The compiler treats the variable as if it were a new type
	- Format: (typecast_type) variable;
	- Typically used when dealing with integers and floating points variables
	- ONLY the compiler cares about the type of a variable
***/

unsigned int a, b;
float c, d;

a = 10;
b = 3;

c = a / b;
d = (float) a / (float) b;	// Casting int to float
```

## Command-Line Arguments
```c
/***
 * Command-Line Arguments
	- accessed in main() function; 2 args; an integer and a pointer to an array of strings
	- int main(int arg_count, char *arg_list[])
	- Bash/Sh shell expands the wildcards (?,*) if not quoted
***/

int main(int arg_count, char *arg_list[])
{
	for(int i = 0; i < arg_count; i++) {
		printf("Arg: #%d\t - %s\n", i, arg_list[i]);
	}
	return 0;
}
```

## Static Keyword
```c
/***
 
* Static Keyword (static)
	- Retains the value of a local variable in the between calls in a function
	- Limits the scope of a global variable or function to a file (visible only in the declared file)
		- Static global variable(s): static data_type variable_name [ = value ];
		- Static function(s): static return_type func_name(optional_args) {...};
	- Initialized only onces and retains its value between function calls
	- Local to the context in which it is declared
	- stored in data segment of the processor 
***/

// Static global variable
static unsigned int day = 1;
static unsigned short int age = 27;
const unsigned short int DAYS_IN_YEAR = 365;

void println(int x)
{
	printf("%d\n", x);
}

void incr_day()
{
	day = day + 1;
	println(day);
}

// Static function
static void incr_age()
{
	age = 27;
	age = age + 1;
}

int main()
{
	for(int i = 0; i < 365; i++) {
		if(day != 364) {
			incr_day();
		}
		else {
			incr_age();
		}
	}

	printf("Age inreased to %d after %d.\n", age, day);
	exit(0);
}
```

## Constant (const) & Define (#define)








