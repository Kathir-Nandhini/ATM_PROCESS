# Customer Bank Details and ATM Process
To program an Automated Teller Machine (ATM) to show the Main Menu specified below and perform some Tasks.

## Initialization of pre-processors
```
include<stdio.h>
include<stdlib.h>
include<string.h>
```
## Main function 
```
In the main function we are displaying the available options for the Customer and for the ATM depositor.
If the user is a customer then he will be given his own choice listed below or
if the user is an ATM depositor then he will be giving his own choice.
At the first step, customer_details_entry() function is called for updating the customer details,
so that the transaction for the customers will be initialized.
OUTPUT will be as follows:
-----------Welcome to the ATM service--------------
1. Load Cash to ATM
2. Maintain Customer Details
3. Handle ATM Operations
4. Check ATM Balance
5. Quit
--------------------------------------------------
```

## Task 1 : Load Cash to ATM
```
The ATM will be initially empty and we are required to feed money
into the machine, along with specific currency denominations
Initially, the ATM will be empty(0).
For the currency denominations, a general structure had implemented
struct denominations{
    int two_thousands,five_hundreds,hundreds;
}d;
By calling the load_cash() function in the main fucntion the ATM cash depositor can deposit money
it will be asking the details regarding the denominations. 
Finally, the obtained amount is added with the total available amount in the ATM.
 
It will print the available balance plus the loaded cash and then gives the denominations 
according to that and also provides the total.
OUTPUT will be like below:
Enter your choice: 1
Enter the no of Two thousands:  20
Enter the no of Five hundrens:  100
Enter the no of Hundreds:       100
-------------------------------------------------------
Denomination    Number          Value
-------------------------------------------------------
2000            20              40000
-------------------------------------------------------
500             100             50000
-------------------------------------------------------
100             100             10000
-------------------------------------------------------
The total available balance in the ATM is : 100000
```

## Task 2 : Maintain Customer Details
```
To maintain the given customer details in the seperate file I have used a structure for their required details.
Structure declaration for customer details is below:
struct customer_entry{
    int acc_no;
    char Name[50];
    int pin;
    int acc_balance;
}s[100]; --> for the time being I have given the size as 100
Then using the function show_customer_details() which is called in the main function 
the following output will be displayed.
Enter your choice: 2
-----------------------------------------------------
Acc_No  Account_Holder Pin_Number  Account Balance
---------------------------------------------------
 101     Suresh         2343        25234
 102     Ganesh         5432        34123
 103     Magesh         7854        26100
 104     Naresh         2345        80000
 105     Harish         1907        103400
---------------------------------------------------
```

## Task 3 : Handle ATM Process
```
In this task We are asking Account number and PIN number which is mandatory and only the user of their account knows the secret pin.
To check the the given input is valid or not we are using a valid() function and in that 
it will check the given input is valid or not from the structure stored in the customer details.
When it is valid it will allow you by shwing the options that you are going to perform.
It will be in switch case and list the options in this format below:
Enter your choice: 3
Enter your Account number: 104
Enter your PIN number: 2345
1. Check Balance
2. Withdraw Money
3. Transfer Money
```
#Task 3.1 : Check Balance :
```
Now our task 3.1 is to check the available balance of the given user when he chose this option.
Like given below the available balance will be displayed.
Enter your choice: 3
Enter your Account number: 104
Enter your PIN number: 2345
1. Check Balance
2. Withdraw Money
3. Transfer Money
Enter the right choice to be performed: 1
---------------------------------------------------
Your Available Account Balance : 80000
---------------------------------------------------
```
#Task 3.2 : Withdraw Money :
```
Basic criteria given for withdrawal of money are listed below. Customer should be alerted
when any of the criteria is met.
1. Max withdrawal limit for a single transaction is10,000₹ and minimum is100₹.
2. For every subsequent withdrawal, pin number should be entered by the customer.
After selecting Withdraw Money option the following actions should be performed.
1. Prompt to Enter the Amount to be withdrawn
2. An alert should be shown when the ATM does not have enough money to vend.
3. Cross verify Acc Balance with requested withdrawal amount and alert the Customer
when - account balance is lower than entered withdrawal amount.

It will be prompting to Enter the Amount to be withdrawn.
The given criterias are filled in the process and then the out will be:
1. Check Balance
2. Withdraw Money
3. Transfer Money
Enter the right choice to be performed: 2
NOTE : Your withdrawal money should be above 100 and below 10000
Enter the Amount to be Withdrawn : 3000
---Please Collect the Cash---Visit again------
```
#Task 3.3 : Transfer Money :
```
Basic Criteria for Transfer are the customer should be alerted when any of the criteria is met.
1. Max transfer limit per transaction cannot exceed 10,000 ₹ and should be more than 1000 ₹
2. Transaction can happen only between the customers mentioned previously
Upon selecting Transfer Money, the following actions should be performed
1. Prompt the customer to input Account Number to which the money has to be transferred
2. Account balance should be properly altered for both sender and receiver and the balance in
ATM should not be affected.
After the satisfaction of given criteria, the transaction between the users can be transfered successfully and lastly the message will be alerted.
OUTPUT will be:
Enter your choice: 3
Enter your PIN number: 2345
1. Check Balance
2. Withdraw Money
3. Transfer Money
Enter the right choice to be performed: 3
NOTE: Max transfer limit per transaction is above 1000 and below 10000
Enter the Amount to be transfered : 102
Enter the account Number to which the money has to be transfered : 103
-------------TRANSACTION SUCCESSFULL-------------
```

## Task 4 : Check ATM Balance:
```
While selecting this option, the user will be shown the balance amount
in the ATM along with its corresponding denominations.
The initial value in the ATM will be 10000 for the time being so that only the 
transaction can be checked efficiently.
The output will be:
Enter your choice: 4
Denomination    Number          Value
-----------------------------------------------------
2000            2               4000
-----------------------------------------------------
500             6               3000
-----------------------------------------------------
100             30              3000
-----------------------------------------------------
The Available Balance in ATM  10000
```

## Conclusion
```
While entering each choice the user can load and see the changes on the screen.
This will be usefull to make the transaction wise and clear.
OUTPUT when given as Quit.
Enter your choice: 5
-------------Thank you for using our ATM------------
```


