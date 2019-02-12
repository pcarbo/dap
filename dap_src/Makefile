# GSL installed with Homebrew (brew install gsl).
GSL_PATH=/usr/local/Cellar/gsl/2.4

CXX=g++
CXXFLAGS=-I$(GSL_PATH)/include

all: dap-g

dap-g: main.o controller.o parser.o MLR.o
	$(CXX) $(CXXFLAGS) main.o parser.o controller.o MLR.o \
          -lm -L$(GSL_PATH)/lib -lgsl -lgslcblas -o dap-g

main.o: main.cc
	$(CXX) -c $(CXXFLAGS) main.cc

parser.o: parser.cc parser.h
	$(CXX) -c $(CXXFLAGS) parser.cc

controller.o: controller.cc controller.h
	$(CXX) -c $(CXXFLAGS) controller.cc

MLR.o: MLR.cc MLR.h
	$(CXX) -c $(CXXFLAGS) MLR.cc

clean:
	rm *.o dap-g


