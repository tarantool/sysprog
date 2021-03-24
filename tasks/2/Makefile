CC	=  cc
CFLAGS	=  -I .
CFLAGS	+= -W -Wall -Wextra -Werror -Wfloat-equal
CFLAGS	+= -Wundef -Wpointer-arith -Wcast-align -Wshadow
CFLAGS	+= -Wstrict-overflow=5 -Wwrite-strings -Waggregate-return
CFLAGS	+= -Wswitch-enum -Wunreachable-code -Winit-self
CFLAGS	+= -Wno-unused-parameter -pedantic -O3
LDFLAGS	=

BASE_SOURCES    = main.c
SOURCES		= $(BASE_SOURCES)
OBJS		= $(SOURCES:.c=.o)
EXECUTABLE	= task_2

all: test

build: $(EXECUTABLE)

$(EXECUTABLE): $(OBJS)
	$(CC) $(LDFLAGS) $(OBJS) -o $@

.c.o:
	$(CC) $(CFLAGS) -c $< -o $@

test: build
	python checker.py -e ./$(EXECUTABLE)

clean:
	rm -rf $(EXECUTABLE) $(OBJS)

.PHONY: clean
