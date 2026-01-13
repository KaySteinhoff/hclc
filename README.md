# hclc

hclc is a minmal stb style header library to evaluate mathematical equation on runtime.<br>

# How to use

As hclc uses the stb style implementation you'll need to define ``HCLC_IMPLEMENTATION` to use it's functionality.
```c
#include <stdio.h>
#define HCLC_IMPLEMENTATION
#include "hclc.h"

int main(int argc, char **argv)
{
	if(argc < 2)
		return -1;
	
	double result = 0;
	unsigned int error = 0;
	if((err = hclc(argv[1], &result)))
		return -2;
	
	printf("%g\n", result);
	return 0;
}
```

You may also define `HCLC_STATIC` to make all hclc functions static or `HCLC_NO_STRTOD` to avoid using the standard strtod function.<br>
Of course when removing the standard strtod function you'll need to provide a new function or `#define` that maps onto the default strtod argument list.
