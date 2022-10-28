# Group Members:  <br />
 &nbsp; Juliana Nguyen <br />
 &nbsp; Alyssa Krouson <br />
 &nbsp; Jake Javier <br />
 &nbsp; Ebrahima Diallo <br />
 
  ## Pseudocode:
  ```
  double labAvg(){
    int *array();
    //add lab grades from vector and divide by length
}

double hwAvg(){

    //add hw grades and divide by length
}

double finalGrade(labAvg, hwAvg, termProj, final, reviewProj){
    //take percentages and conver to points to find final grade
}

int main(){
    //int number of labs done, number of assignments done;
    //double labs vector -> list all lab grades;
    //double assignment vector -> list all assign grades;

    double labAvg;

    double hwAvg;

    double finalGrade;

    if finalGrade)
        A
        B
        C

}
  
```

## Code Completed
 ```
 
#include <iostream>
#include <string>
#include <fstream>
#include <vector>
#include <cmath>
#include <sstream>
#include <numeric>
//#include "run.h"

//calcuates lab grade average
double labAvg(std::vector<double> * labs, int labNum) {
    double sum;
    double avg;

    sum = std::accumulate(labs->begin(), labs->end(),0);
    avg = sum/labNum;

    return avg;
}

//calcuates homework grade average
double hwAvg(std::vector<double> * hws, int hwNum) {
    double sum;
    double avg;

    //adds together everything in the vector
    sum = std::accumulate(hws->begin(), hws->end(),0);
    avg = sum/hwNum;

    return avg;
}

//calculates the final grade using the grade of each category
double finalGrade(double labGrade, double hwGrade, double termProj, double final, double reviewProj){

    //lab grade out of 50 pts
    labGrade = (labGrade/100) * 50;
    //hw grade out of 500 pts
    hwGrade = (hwGrade/100) * 500;
    //term project out of 350 pts
    termProj = (termProj/100) * 350;
    //review proj out of 30 pts
    reviewProj = (reviewProj/100) * 30;

    //final grade calculated out of 1000 pts
    double total = (labGrade + hwGrade + termProj + final + reviewProj);
    total = total/ 10; //instead of /1000 then *100

    return total;
}


class run{
   public:
    int labNum;
    int hwNum;
};

int main() {
    
    run myObj;
    
    myObj.labNum = 12;
    myObj.hwNum = 5;
    
   // int myObj.labNum = 12, myObj.hwNum = 5;
    double grade;
    std::vector<double> labs;
    std::vector<double> hws;

    //adds grades to lab vector
    std::cout << "Enter lab grades" << '\n';
    for (int i = 0; i < myObj.labNum; i++) {
        std::cin >> grade;
        labs.push_back(grade);
    }
    //adds hw grades to hw vector
    std::cout << "Enter hw grades" << '\n';
    for (int i = 0; i < myObj.hwNum; i++) {
        std::cin >> grade;
        hws.push_back(grade);
    }

    //finds average grade of labs and hw
    double labGrade = labAvg(&labs, myObj.labNum);
    double hwGrade = hwAvg(&hws, myObj.hwNum);

    double termProj, final, reviewProj;
    std::cout << "Enter term project grade" << '\n';
    std::cin >> termProj;
    std::cout << "Enter final exam grade" << '\n';
    std::cin >> final;
    std::cout << "Review project grade"<< '\n';
    std::cin >> reviewProj;

    double termGrade = finalGrade(labGrade, hwGrade, termProj, final, reviewProj);

    std::cout << termGrade << '\n';

    if (termGrade >= 94){
        std::cout << "A" << std::endl;
    }
    else if (termGrade >= 90){
        std::cout << "A-" << std::endl;
    }
    else if (termGrade >= 87){
        std::cout << "B+" << std::endl;
    }
    else if (termGrade >= 83){
        std::cout << "B" << std::endl;
    }
    else if (termGrade >= 80){
        std::cout << "B-" << std::endl;
    }
    else if (termGrade >= 77){
        std::cout << "C+" << std::endl;
    }
    else if (termGrade >= 73){
         std::cout << "C" << std::endl;
    }
    else if (termGrade >= 70){
         std::cout << "C-" << std::endl;
    }
    else if (termGrade >= 67){
         std::cout << "D+" << std::endl;
    }
    else if (termGrade >= 60){
        std::cout << "D" << std::endl;
    }
    else{
        std::cout << "F" << std::endl;
}
   //run test;
   //test.hello();

   return 0;
}
 
 ```
  ## Summary <br />
&nbsp; &nbsp; For this assignment we were tasked with creating a code that will be able to produce a class average with the right information provided.

  ## Features
&nbsp; &nbsp; The information thats taken in include all of the grades that you have recieved by the end of the semester, and it outputs the total average with the associated letter grade. We beleive the letter grade is a helpful touch to include considering it helps you visualize the grade. <br />

&nbsp; &nbsp; The data is added in by prompts given by the compiler as to which grade you need to enter.

## Mock Data

Student Name  | Assignment 1 Grade | Assignment 2 Grade | Assignment 3 Grade |Assignment 4 Grade |Assignment 5 Grade | 
------------- | ------------- | -------------| -------------| -------------| -------------|
Juliana  | 20 | 50 | 70 | 80 | 90 |
Alyssa  | 60 | 50 | 100 | 87 | 90 |
Jake  | 0 | 100 | 100 | 43 | 90 |
Ebrahima  | 20 | 70 | 85 | 0 | 90 |

Student Name  | Lab 1 Grade | Lab 2 Grade | Lab 3 Grade |Lab 4 Grade |Lab 5 Grade | Lab 6 Grade |Lab 7 Grade |Lab 8 Grade |Lab 9 Grade |Lab 10 Grade |Lab 11 Grade |Lab 12 Grade | 
------------- | ------------- | -------------| -------------| -------------| -------------| -------------| -------------| -------------| -------------| -------------| -------------| -------------|
Juliana  | 100 | 100 | 0 | 100 | 100 | 100 | 0 | 100 | 0 | 100 | 100 | 100 |
Alyssa  | 100 | 100 | 0 | 100 | 100 | 100 | 0 | 100 | 0 | 100 | 100 | 100 |
Jake  | 100 | 100 | 0 | 100 | 100 | 100 | 0 | 100 | 0 | 100 | 100 | 100 |
Ebrahima  | 100 | 100 | 0 | 100 | 100 | 100 | 0 | 100 | 0 | 100 | 100 | 100 |

Student Name  | Review Project Grade | Final Project Grade |
------------- | ------------- | -------------|
Juliana  | 100 | 100 |
Alyssa  | 100 | 100 |
Jake  | 100 | 100 |
Ebrahima  | 100 | 100 |


