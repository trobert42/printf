# Printf() function

A simple implementation of the C function printf. 

|    Project Name    |                                                                       ft_printf                                                                       |
| :----------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------: |
|    Description     |                                             My implementation of printf() C function                                             |
|    Technologies    | <a href="#"><img alt="C" src="https://custom-icon-badges.demolab.com/badge/C-03599C.svg?logo=c-in-hexagon&logoColor=white&style=for-the-badge"></a> |
| External libraries |     malloc(), free(), write(), va_start(), va_arg(), va_copy(), va_end()      |

## Usage

```bash
  gcl https://github.com/trobert42/printf.git
  cd printf
  make
```

It will create a library named libftprint.a. You can use the function ft_printf() if you include it inside your code and compile with the library. Here's how :
```C
// main.c
#include "includes/ft_printf.h"

int main() {
    ft_printf("Hello %d \n", 42);
    return 0;
}

```

Then the compilation process :
```bash
gcc -Wall -Werror -Wextra main.c libftprintf.a
```

If you want to use it in your project, you can link it into your makefile:
```bash
CC = gcc
CFLAGS = -Wall -Werror -Wextra
LDFLAGS = -L. -lftprintf
SRC = main.c
OBJ = $(SRC:.c=.o)
EXE = a.out

.PHONY: all clean fclean re

all: $(EXE)

$(EXE): $(OBJ)
    $(CC) $(CFLAGS) $(OBJ) $(LDFLAGS) -o $@

%.o: %.c
    $(CC) $(CFLAGS) -c $< -o $@

clean:
    rm -f $(OBJ)

fclean: clean
    rm -f $(EXE)

re: fclean all
```
