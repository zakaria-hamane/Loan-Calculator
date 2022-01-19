# Loan-Calculator
This loan calculator should be able to do. In general, it takes several parameters like a loan principal and interest, calculates the values the user wants to know (for example, monthly payment or overpayment), and outputs them to the user.

## Description
Finally, let's add to our calculator the capacity to compute differentiated payments. We’ll do this for the type of repayment where the loan principal is reduced by a constant amount each month. The rest of the monthly payment goes toward interest repayment and it is gradually reduced over the term of the loan. This means that the payment is different each month. Let’s look at the formula:is loan!
![1](https://user-images.githubusercontent.com/48354769/150136903-f8ba9155-cf59-43f6-8132-392fbf53d34e.jpg)

The user has to input a lot of parameters, so it might be convenient to use command-line arguments.
You can run your loan calculator via command line like this:
```
python creditcalc.py
```

Using command-line arguments you can run your program this way:
```
python creditcalc.py --type=diff --principal=1000000 --periods=10 --interest=10
```

## Examples
The greater-than symbol followed by a space (> ) represents the user input. Note that this is not part of the input.

### Example 1: calculating differentiated payments

```
> python creditcalc.py --type=diff --principal=1000000 --periods=10 --interest=10
Month 1: payment is 108334
Month 2: payment is 107500
Month 3: payment is 106667
Month 4: payment is 105834
Month 5: payment is 105000
Month 6: payment is 104167
Month 7: payment is 103334
Month 8: payment is 102500
Month 9: payment is 101667
Month 10: payment is 100834

Overpayment = 45837
```

In this example, the user wants to take a loan with differentiated payments. You know the principal, the count of periods, and interest, which are 1,000,000, 10 months, and 10%, respectively.

The calculator should calculate payments for all 10 months. Let’s look at the formula above. In this case:

![1](https://user-images.githubusercontent.com/48354769/150137786-26fd4906-eb28-43ab-9ff4-75c851072071.jpg)

And so on. You can see other monthly payments above.

Finally, your loan calculator should add up all the payments and subtract the loan principal so that you get the overpayment.

### Example 2: calculate the annuity payment for a 60-month (5-year) loan with a principal amount of 1,000,000 at 10% interest

```
> python creditcalc.py --type=annuity --principal=1000000 --periods=60 --interest=10
Your annuity payment = 21248!
Overpayment = 274880
```

### Example 3: fewer than four arguments are given

```
> python creditcalc.py --type=diff --principal=1000000 --payment=104000
Incorrect parameters.
```

### Example 4: calculate differentiated payments given a principal of 500,000 over 8 months at an interest rate of 7.8%

```
> python creditcalc.py --type=diff --principal=500000 --periods=8 --interest=7.8
Month 1: payment is 65750
Month 2: payment is 65344
Month 3: payment is 64938
Month 4: payment is 64532
Month 5: payment is 64125
Month 6: payment is 63719
Month 7: payment is 63313
Month 8: payment is 62907

Overpayment = 14628
```

### Example 5: calculate the principal for a user paying 8,722 per month for 120 months (10 years) at 5.6% interest

```
> python creditcalc.py --type=annuity --payment=8722 --periods=120 --interest=5.6
Your loan principal = 800018!
Overpayment = 246622
```

### Example 6: calculate how long it will take to repay a loan with 500,000 principal, monthly payment of 23,000, and 7.8% interest

```
> python creditcalc.py --type=annuity --principal=500000 --payment=23000 --interest=7.8
It will take 2 years to repay this loan!
Overpayment = 52000
```
