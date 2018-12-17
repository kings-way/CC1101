CXX := g++
CXXFLAGS := -W -Wall
CXXLDFLAGS := -lwiringPi
OBJECTS = TX_Demo.o RX_Demo.o cc1100_raspi.o

PROGRAM := TX_Demo RX_Demo


all: $(OBJECTS)
	$(CXX) $(CXXLDFLAGS) TX_Demo.o cc1100_raspi.o -o TX_Demo
	$(CXX) $(CXXLDFLAGS) RX_Demo.o cc1100_raspi.o -o RX_Demo
	

TX_Demo.o: TX_Demo.cpp
	$(CXX) $(CXXFLAGS) -c TX_Demo.cpp -o TX_Demo.o

RX_Demo.o: RX_Demo.cpp
	$(CXX) $(CXXFLAGS) -c RX_Demo.cpp -o RX_Demo.o

cc1100_raspi.o: cc1100_raspi.cpp
	$(CXX) $(CXXFLAGS) -c cc1100_raspi.cpp -o cc1100_raspi.o

TX_Test: all
	@echo "\n================ TX Test ================"
	@echo "Run: ./TX_Demo -v -a1 -r3 -i1000 -t1 -c1 -f434 -m4"
	./TX_Demo -v -a1 -r3 -i1000 -t1 -c1 -f434 -m4

RX_Test: all
	@echo "\n================ RX Test ================"
	@echo "Run: ./RX_Demo -v -a3 -c1 -f434 -m4"
	./RX_Demo -v -a3 -c1 -f434 -m4	


.PHONY : clean
clean :
	 -rm $(OBJECTS) $(PROGRAM)
