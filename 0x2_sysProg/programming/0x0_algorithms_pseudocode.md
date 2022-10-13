# --[ ALGORITHMS & PSEUDOCODE

PROGRAMMING - THE ART OF EXPLOITATION

## 0x100 - INTRODUCTION
Hackers, since the infancy of computers, have creatively help in solving problems in an **elegance** manner.
Hackers persue knowledge itself by continually learning and exploring to trascend the boundaries.
Hackers are both those who write code and exploit it.

## 0x200 - PROGRAMMING
Understanding of programming helps those who exploit codes, and understanding of exploitation helps those who program to write code and technique used to exploit programs.

Programming is just a series of statement written in a specific language. Computers only understand machine language, instructions for computers must be in the machine language for the computer to follow.

Machine language consists of raw bits and bytes, differs from architecture to architecture. A translator is used to overcome the overhead of writing machine language.

An assembly is one form of machine-language translator. It translates assembly language into machine readable code; thus less cryptic.

Another form translator is the compiler, it converts higher-level language instructions into machine language. Higher level languages are much intuitive than assembly language and can be converted into many different types of machine language for different processor architectures.

C/C++, Fortran are examples of higher level languages. Higher level languages are much more readable than assembly language or machine language but follows very strict rules about wording of instructions.

### PSEUDO-CODE
Another form of programming language which is generally structured in English similar to a higher level language.
It is a useful way for programmers to arrange instructions. It isn't a well defined language. There are slight variations in pseud-code of different programmers.
It makes an excellent introduction common programming concepts. Compilers, assemblers or any computer do not understand pseudo-codes.

### CONTROL STRUCTURES
Control structures change the flow of the program's execution from simply sequencial other to a more complex and more useful flow.
* IF-ELSE STATEMENT
* WHILE LOOP
* UNTIL THEN
* FOR LOOP

### FUNDAMENTAL PROGRAMMING CONCEPTS
* Variables: An object that holds data that can change or a constant which doesn't change.
* Arithmetic Operators: Addition +, Subtraction -, Multiplication \*, Modulo %, and Division /.
* Comparison Operators: Less than <, Greater than >, Less or Equal <=, Greater or Equal >=, equal ==, and Not Equal !=.
* Logical Operators: OR ||, AND && and NOT !.
* Functions: Grouping of instructions into a smaller sub program used within a program.

### EXAMPLE: ALGORITHM & PSEUDO-CODE (Driving Instructions)
Start out down Main Street headed east.
Continue on Main Street until you see a church on your right.
If the street is blocked because of construction, turn right there is 15th Street, turn left on the Pine Street, and then turn right on 16th Street.
Otherwise, you can just continue and make a right on 16th Street.
Continue on 16th Street, an turn left onto Destination Road.
Drive Straight down Destination Road for 5 miles, an then you'll see the house on the right.
The address is 743 Destination Road.

## PSEUDO-CODE

Drive down Main Street;
While(there is not church on the right)
	Drive down Main Street;

If(street is blocked)
{
	Turn right on 15th Street;
	Turn left on Pine Street;
	Turn right on 16th Street;
}
Else
{
	Turn right on 16th Street;
}

Turn left on Destination Road;
For(i = 0; i < 5; i++)
	Drive straight for 1 mile;
Stop at 743 Destination Road;

### EXAMPLES WITH VARIABLES (SMART MOUSE)

While(hungry)
{
	Find some food;
	Eat the food;
}

While( (hungry) && !(cat_present) )
{
	Find some food;
	If(!(food on a mousetrap))
		Eat the food;
}

## FUNCTIONS (Turn)

Function Turn(variable\_direction)
{
	Activate the variable_direction blinker;
	Slow down;
	
	Check for oncoming traffic;
	while(there is oncoming traffic)
	{
		Stop;
		Watch for oncoming traffic;
	}

	Turn the steering wheel to the variable_direction;
	while(turn is not complete)
	{
		if(speed < 5 mph)
			Accelerate;
	}
	Turn the steering wheel back to the original position;
	Turn of the variable_direction blinker;
}

### MORE EXAMPLES WITH FUNCTIONS (Factorial of a number)
Function factorial(Number N)
{
	Number i;
	for(i = 1; i < N; i++)
		N = N * i;
	return N; 
}

### Turn (More Complete Version)

void turn(variable\_direction, target\_street\_name) 
{
	Look for a steet sign;
	current_intersection_name = read street sign name;
	while(current_intersection_name != target_street_name)
	{
		Look for another street sign;
		current_intersection_name = read street sign name;
	}
	Activate the variable_direction blinker;
	Slow down;
	Check for oncoming traffic;
	while(there is oncoming traffic)
	{
		Stop;
		Watch for oncoming traffic;
	}
	Turn the steering wheel to the variable_direction;
	while(turn is not complete)
	{
		if(speed < 5 mph)
			Accelerate;
	}
	Turn the steering wheel right back to the original position;
	Turn off the variable_direction blinker;
}

### UPDATE - Driving Instructions with function
Begin going East on Main Street;
while (there is not a church on the right)
	Drive down Main Street;
if (street is blocked)
{
	Turn(right, 15th Street);
	Turn(left, Pine Street);
	Turn(right, 16th Street);
}
else
	Turn(right, 16th Street);
Turn(left, Destination Road);
for(i = 0; i < 5; i++)
	Drive straight for 1 mile;
Stop at 743 Destination Road;
