/* This C code is written by KA
Multi-word variables are written in the following format: Variable_Name
While functions are written in the following format: FunctionName
*/


#include <stdio.h>
#include <math.h>

float UsageBill(int Units_Consumed[]);
float TaxCalc(float Usage_Bill);
float PenaltyCalc(float Final_Amount);
void PrintBill(int User_Account_no, float Final_Amount,float Final_Amount_with_Penalty);


int main() {
    int User_Account_no;
    int Units_Consumed[3];
    float Usage_Bill;
    float Final_Amount;
    float Final_Amount_with_Penalty;
    
    printf("Welcome to Electricity Bill Application\n");
    
    printf("\nEnter the Account number to proceed \n");
    do{
    scanf("%d",&User_Account_no);
     if (User_Account_no<0){
                  printf("Invalid Input, enter a positive Account number only \n");
              }
        } while (User_Account_no<0);
        
        
    printf("Enter the Units Consumed in the past 3 months \n");
    
    for(int i=0; i<3; i++){
        do {
              scanf("%d",&Units_Consumed[i]);
              if (Units_Consumed[i]<0){
                  printf("Invalid Input, enter a positive number only \n");
              }
        } while (Units_Consumed[i]<0);
    }
    
    Usage_Bill = UsageBill(Units_Consumed);
    
    Final_Amount = TaxCalc(Usage_Bill);
                            
    Final_Amount_with_Penalty= PenaltyCalc(Final_Amount);
   
   PrintBill(User_Account_no,Final_Amount,Final_Amount_with_Penalty);
   

    return 0;
}

//Bill Calculation
float UsageBill(int Units_Consumed[]){
    float Usage_Bill = 0;
    int Total_Units =0;
    int Fixed_Charge;
    float Energy_Charge;
    
    
    for (int i=0; i<3; i++){
        Total_Units+= Units_Consumed[i];
    }
    
    
        if (Total_Units>=0 && Total_Units<=100){
            Fixed_Charge= 3; Energy_Charge = 0.25;
            
        }
        else if (Total_Units>=101 && Total_Units<=300){
            Fixed_Charge= 7; Energy_Charge = 0.5;
            
        }
        else if (Total_Units>=301 && Total_Units<=500){
            Fixed_Charge= 10; Energy_Charge = 0.75;
            
        }
        else{
            Fixed_Charge= 12; Energy_Charge = 1;
            
        }
        Usage_Bill = Fixed_Charge + (Total_Units * Energy_Charge);
        
        
    printf("\nTotal Consumed Units: %d\n",Total_Units);
    printf("\nCharges Levied as: \nFixed Cahrge: $%d \nEnergy Charge: $%.2f\n",Fixed_Charge,Energy_Charge);
    
    return Usage_Bill;
    
}

//Tax Calculation
float TaxCalc(float Usage_Bill){
    float Tax = 0.5/100;
    float Levied_Tax = Tax * Usage_Bill;
    float Final_Amount = Levied_Tax + Usage_Bill;
    return ceil(Final_Amount);
}

//Penalty Calulation after passing due date
float PenaltyCalc(float Final_Amount){
    float Penalty = 5.0/100.0;
    float Final_Amount_with_Penalty = Penalty*Final_Amount + Final_Amount;
    return ceil(Final_Amount_with_Penalty);
}

//Print the Bill
void PrintBill(int User_Account_no, float Final_Amount,float Final_Amount_with_Penalty){
    printf("\n*******************\n\n");
    
    printf("Account Numeber:  %d\nFinal Amount:  $%.2f\nFinal Amount DueDate: $%.2f\n",User_Account_no, Final_Amount, Final_Amount_with_Penalty);
    
    printf("\n*******************\n");
}
