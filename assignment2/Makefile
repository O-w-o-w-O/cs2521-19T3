# Makefile for Ass2

CC = gcc
CFLAGS =  -Wall -std=c11 -Werror -g
AR = ar
objs = Graph.o CentralityMeasures.o PQ.o Dijkstra.o GraphRead.o 

all :  testDijkstra testCentralityMeasures testLanceWilliamsHAC

$(objs) : %.o : %.c

GraphLib.a : $(objs)
	$(AR) rcs $@ $^


testDijkstra : testDijkstra.c GraphLib.a
	$(CC) -o  testDijkstra testDijkstra.c GraphLib.a 

testCentralityMeasures : testCentralityMeasures.c GraphLib.a
	$(CC) -o testCentralityMeasures testCentralityMeasures.c GraphLib.a 


BSTree.o : BSTree.c BSTree.h 
	$(CC)  -c   BSTree.c  

LanceWilliamsHAC.o : LanceWilliamsHAC.c Graph.o  BSTree.o 
	$(CC)  $(CFLAGS) -c  -o LanceWilliamsHAC.o LanceWilliamsHAC.c    

testLanceWilliamsHAC : testLanceWilliamsHAC.c Graph.h  Graph.o LanceWilliamsHAC.o BSTree.o GraphRead.o
	$(CC)   -o  testLanceWilliamsHAC testLanceWilliamsHAC.c Graph.o BSTree.o GraphRead.o LanceWilliamsHAC.o 

clean :
	rm -f *.o testCentralityMeasures testDijkstra  testLanceWilliamsHAC GraphLib.a
	
	
