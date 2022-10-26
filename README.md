# MechaCar Statistical Analysis

## Linear Regression to Predict MPG

![Deliv_1](https://user-images.githubusercontent.com/108296899/198038458-7c396eba-4071-4d3e-9921-94a14c1961d9.png)

Here we see that the intercept, vehicle length and ground clearance will most likely provide non-random data. Their p-values are less than .05%. Similarly the p-value for the summary is 5.35e-11, much lower than our significance level. We can assume that our slope is non-zero. Our R-squared value for this model is .7149, meaning there is a 71.49% probability that this method can accurately predict the mpg of prototype cars. This is a connection and we can confidently use this data to predict results.


## Summary Statistics on Suspension Coils

![total_summary](https://user-images.githubusercontent.com/108296899/198046340-f4a961b7-b010-414f-a4fc-52d42ee1053b.png)

![lot_summary](https://user-images.githubusercontent.com/108296899/198046357-1baae0e4-d008-49a8-96ff-dbb0ad8b36ab.png)

The allowable variance for the suspension coils is 100psi. We can see for the total data, this is met with a variance of 62.29. However, when we look into the individual lot data, we can see that lot 3 does not meet this parameter with a variance of 170.28. We need to do some inspecting of these pieces to see what is causing this.
