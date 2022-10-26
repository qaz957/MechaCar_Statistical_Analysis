# MechaCar Statistical Analysis

## Linear Regression to Predict MPG

![Deliv_1](https://user-images.githubusercontent.com/108296899/198038458-7c396eba-4071-4d3e-9921-94a14c1961d9.png)

Here we see that the intercept, vehicle length and ground clearance will most likely provide non-random data. Their p-values are less than .05%. Similarly the p-value for the summary is 5.35e-11, much lower than our significance level. We can assume that our slope is non-zero. Our R-squared value for this model is .7149, meaning there is a 71.49% probability that this method can accurately predict the mpg of prototype cars. This is a connection and we can confidently use this data to predict results.


## Summary Statistics on Suspension Coils

![total_summary](https://user-images.githubusercontent.com/108296899/198046340-f4a961b7-b010-414f-a4fc-52d42ee1053b.png)

![lot_summary](https://user-images.githubusercontent.com/108296899/198046357-1baae0e4-d008-49a8-96ff-dbb0ad8b36ab.png)

The allowable variance for the suspension coils is 100psi. We can see for the total data, this is met with a variance of 62.29. However, when we look into the individual lot data, we can see that lot 3 does not meet this parameter with a variance of 170.28. We need to do some inspecting of these pieces to see what is causing this.

## T-Tests on Suspension Coils

    > t.test(suspension_coil$PSI,mu=mean(suspension_coil$PSI))

      One Sample t-test

    data:  suspension_coil$PSI
    t = 0, df = 149, p-value = 1
    alternative hypothesis: true mean is not equal to 1498.78
    95 percent confidence interval:
     1497.507 1500.053
    sample estimates:
    mean of x
      1498.78

    > t.test(subset(suspension_coil$PSI,suspension_coil$Manufacturing_Lot == "Lot1"),mu=mean(suspension_coil$PSI))

      One Sample t-test

    data:  subset(suspension_coil$PSI, suspension_coil$Manufacturing_Lot == "Lot1")
    t = 8.7161, df = 49, p-value = 1.568e-11
    alternative hypothesis: true mean is not equal to 1498.78
    95 percent confidence interval:
     1499.719 1500.281
    sample estimates:
    mean of x 
         1500 

    > t.test(subset(suspension_coil$PSI,suspension_coil$Manufacturing_Lot == "Lot2"),mu=mean(suspension_coil$PSI))

      One Sample t-test

    data:  subset(suspension_coil$PSI, suspension_coil$Manufacturing_Lot == "Lot2")
    t = 3.6739, df = 49, p-value = 0.0005911
    alternative hypothesis: true mean is not equal to 1498.78
    95 percent confidence interval:
     1499.423 1500.977
    sample estimates:
    mean of x 
       1500.2 

    > t.test(subset(suspension_coil$PSI,suspension_coil$Manufacturing_Lot == "Lot3"),mu=mean(suspension_coil$PSI))

      One Sample t-test

    data:  subset(suspension_coil$PSI, suspension_coil$Manufacturing_Lot == "Lot3")
    t = -1.4305, df = 49, p-value = 0.1589
    alternative hypothesis: true mean is not equal to 1498.78
    95 percent confidence interval:
     1492.431 1499.849
    sample estimates:
    mean of x 
      1496.14

The p-value for the total sample is =1. Meaning that there is mathematical certainty that thse results ocured by chance.  We can see by the individual results from each lot that Lot3 is heavily affecting the reliability of the data, with a 15% probability of chance.

## Study Design: MechaCar vs Competition

In this study we want to compare the MechaCar's cost, city fiel efficiency and maintenance cost to it's competitor. The goal is to the create data that can be used to compare the car's viability as a city cruiser. We will be analyziing these metrics on their differences to similar models from other manufacturers.

- Null Hypothesis: The MechaCar is statistically similar to it's competing models and should be compared to the existing market.
- Alt. Hypothesis: The MechaCar is statistically different to it's competing models and should be used in other markets.

We can run a two-sample T-test on these metrics to see if there is statistical similarity bewteen models in the city-cruiser market. We would need to collect data on the fuel efficiency of the most popular models being used by city-dwelling car owners and maintenance cost data to see what we should be aiming for as "city miles" are known to be harder on a car.
