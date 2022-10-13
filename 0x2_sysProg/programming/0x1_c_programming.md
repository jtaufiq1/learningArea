# --[ C PROGRAMMING

## Pointers
```c
/***
 * 
 * type *pointer_name [= &Value];
 * pointer_name = &AddressOfVariable;
 * *derefernce_pointer_name;
 * Pointer Arithmetic
 * pointer++ : Increases pointer by size of type
 * pointer-- : Decrease pointer by size of type
 ***/

// Void Pointer: Typeless
void *void_ptr;
char n = 10;
int c = 'A';

void_ptr = &n;

printf("Value of pointer Var: %c\n", *((void *) void_ptr));		// Dereferencing void pointer
printf("Address: of pointer: %p\n", void_ptr)					// Address of pointer

unsigned char *raw_bytes = "Sample bytes";
void *raw_ptr = raw_bytes;

for(int i = 0; i < sizeof((int *)raw_bytes);) {
	printf("%02x ", raw_bytes);
	raw_bytes++;
}
```

* Function Pointers
```c
/***
 * 
 ***/
int func1(){
	return 1;
}

int return_value;
int (*function_ptr) ();

function_ptr = func1;
return_value = function_ptr();
```

## Memory Segmentation
```c
/***
## MEMORY SEGMENTATION
	- A compiled program's memory is divided into 5 segments
	- Each segment represents a special portion set aside for a certain purpose
	- The segments are: text|code, data, bss, stack and heap
	- Compiled code goes into the text segment
	- Variables defined outside of any function and static variables are considered global
	- Initialized global variables go into the data segment and the rest goes into bss segment
	- Memory on the heap must must be allocated first using an allocater function
	- Pointers are used to reference memory on the heap
	- Function variables are stored on the stack.
***/

unsigned int WEEK = 7;	// Goes to the data segment
char * WEEK_DAY;		// Goes to the bss segment

void function(char letter, int l_number, short base)
{	// Local function Context
	// Local variables & function parameters goes to the stack segment
	int stack_var = 4;

	// Static local variables goes to the Data/bss segment
	static char static_init_var = 'A';	// Initialized static goes to the Data segment
	static int static_uninit_var;		// Uninitialized static goes to the bss segment
}

int main()
{
	// Stack segment var
	int stack_var;

	// Heap segment var
	char *heap_var;
	heap_var = (char *) malloc(4);

	function('B', 66, 0);
	free(heap_var);

	return 0;
}
```

## File Access
```c
/***
 * 
 * 
 ***/
#include <stdio.h>
#include <unistd.h>
#include <sys/stat.h> 	// File Flags
#include <fcntl.h> 		// File permissions

int fd; 	// File Descriptor
unsigned MODE, PERMISSION;
char *data;

FLAGS = O_RDWR|O_CREAT|O_APPEND;	// READ & WRITE, CREATE, APPEND
MODE = S_IRWXU;						// READ-WRITE-EXECUTE PERMISSION for USER (Owner of file)

// OPEN FILE
fd = open("Path/to/File", FLAGS, MODE);

// WRITE RAW BYTES
if(fd != -1)
	write(fd, &data, sizeof(data));
write(fd, 0, 1); 	// Terminate file
write(fd, '\0', 1); // Write newline to file

// READ FILE CONTENT
while(read(fd, &data, sizeof(data)) == -1)
	printf("%s", data);

// CLOSE FILE
close(fd);

```

## Structure (struct) | Union (union) | Type Declaration (typedef)

* Struct
```c
/***
 * 
 ***/
struct struct_type {
	void *data; 	// Typeless data
	char *string 	// Sequence of characters
	int number; 	// Positive and Negative number type
	unsigned pos_n; // Positive number type
	float dec_n;	// Number with decimal point
} new_type;

struct struct_type s_test;

s_test->data = "Sample typeless data"; 	// Accessing a pointer in struct
s_test->string = "Sequence of characters";

s_test.number = 10;


```

* union
```c

```

* typedef
```c


```
## Date and Time (time(NULL))

## Random Number Generator (rand() & srand(SEED_VALUE))

## Preprocessor Directives

## Header Files


















## MISCELLANIA
* Standard library functions
	- String functions: strcpy, strncpy(),strncat()
	- String to integer conversion functions: atoi(), strtol()
	- Memory management: malloc(size), free()
	- File Access: open(), read(), write(), close(), lseek()







