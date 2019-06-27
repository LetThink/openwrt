CC = gcc
CFLAGS = -g -Wall -I${DIR_INC}
DIR_SRC = ./source
DIR_INC = ./include
DIR_OBJ = ./obj
DIR_BIN = ./debug
FILE_OBJ = obj
FILE_DEBUG = debug
SRC = $(wildcard ${DIR_SRC}/*.c) 
OBJ = $(patsubst %.c,${DIR_OBJ}/%.o,$(notdir ${SRC}))

TARGET = hello

BIN_TARGET = ${DIR_BIN}/${TARGET}

${BIN_TARGET}:${OBJ}
	test -d ${FILE_DEBUG} || mkdir -p ${FILE_DEBUG}
	$(CC) $(OBJ)  -o $@

${DIR_OBJ}/%.o:${DIR_SRC}/%.c
	test -d ${FILE_OBJ} || mkdir -p ${FILE_OBJ}
	$(CC) $(CFLAGS) -c  $< -o $@
	echo "successful"
.PHONY:clean
clean:
	rm -rf ${DIR_OBJ}/*.o ${FILE_DEBUG}  ${FILE_OBJ} 
