# Module_14_Challenge

## Established a Baseline Performance

**STEPS:**
*- Imported the OHLCV dataset into a Pandas DataFrame by reading the CSV file named "emerging_markets_ohlcv.csv" and setting the 'date' column as the index.

- Generated trading signals using short- and long-window SMA values. Calculated the simple moving averages (SMA) for the 'close' price using a short window of 4 days and a long window of 100 days. These SMAs were added as columns to the DataFrame.

- Filtered the DataFrame to remove rows with NaN values, ensuring data consistency.

- Initialized a new 'Signal' column in the DataFrame with default values of 0. This column stored trading signals.

- Based on the 'Actual Returns' column, generated signals to buy stock long when returns were greater than or equal to 0 and sell stock short when returns were less than 0.

- Calculated the strategy returns by multiplying the 'Actual Returns' by the 'Signal' and stored them in a new 'Strategy Returns' column.

- Plotted the cumulative returns of the strategy against the actual returns to visualize the baseline performance. Saved this plot as a PNG image saved as *(svm_plot)*.


## Tuned the Baseline Trading Algorithm

**STEPS:**

Tuned the training algorithm by adjusting the size of the training dataset. **6-month* period was selected. The results are discussed below in conclusion.

The impact of increasing or decreasing the training window on trading outcomes was evaluated.

Tuned the trading algorithm by adjusting the SMA input features. Both SMA periods were adjusted: short window was changed 21 days and long window to 50 days, while the DateOffset was for 6 months. In another iteration, short window was changed to 21 days and long window to 200 days, whereas the DateOffset was kept at 3 months. All the results are explained in conclusion.

Saved a PNG image of the cumulative product of the actual returns vs. the strategy returns for all three iterations and choose the best performing one.


### Conclusion

**Original Dataset:** The strategy produces slightly favourable results compared to the actual results based on the original paratmers. *Actual returns are 1.4**, whereas **strategy returns are 1.5*.

**Iteration 1:** By changing the parameters and increasing the end date to 6 months and changing the short and long windows to 21 days 50 days, the results are dratically different: the **actual returns has started an upward trend reaching 1.4* and the *strategy return has started a downward trend and going below 0.8**.

**Iteration 2:** By changing the windows to 21 and 200 days, the actual returns still performed better than the strategy: *actual returns at 1.6* and *strategy return at 1.45*.

## Evaluated a New Machine Learning Classifier

**STEPS:**
Imported a new classifier - LogisticRegression, from scikit-learn.
Used the original training data as a baseline model to fit another model with the new classifier. The model was trained using the training data, and predictions were made based on the testing data.
Backtested the new model to evaluate its performance. Created a cumulative return plot that showed the actual returns vs. the strategy returns for the updated trading algorithm. Saved this plot as a PNG image as *lr_plot.png*.

### Logistic Regression Model Conclusion:
The model produced almost similar results towards the end; however, it had a higher volatility than the original model.
