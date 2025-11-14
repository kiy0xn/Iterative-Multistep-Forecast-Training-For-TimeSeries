For clarity, this document is designed as a training document explaining the iterative (recessive) multi-step method for time series forecasting with an application example.

To this end, a simple, synthetic monthly price series was created. The model was trained using features with a 12-step lag (lag 1..12) as inputs, predicting the next month (one-step ahead). 
A linear regression model was chosen for simplicity and instruction. 
Test performance was calculated, and then the forecast model was created for the next 24 months using an iterative multi-step approach. 
In other words, one month was predicted at each step, and this forecast was used as input for the next step.

To reintroduce the output (the generated forecast) into the system as input, the last 12 values ​​were kept in the seed list. Each forecast was added to this seed list, 
and in the next step, this final forecast was included in the new forecast calculation according to the model's expected lag order (t−1, t−2, etc.). 
Thus, the model calculated the next step by seeing "the model's own prediction instead of the actual value."

Note! Each iteration is affected by the successes and failures of previous iterations. As the iterative method progresses, prediction errors (error accumulation) 
can increase as erroneous predictions are added to the input. This presents a significant disadvantage.

For the full story : https://medium.com/t%C3%BCrkiye/zaman-serilerinde-i%CC%87teratif-yinelemeli-%C3%A7ok-ad%C4%B1ml%C4%B1y%C3%B6ntemle-tahmin-400331812951
