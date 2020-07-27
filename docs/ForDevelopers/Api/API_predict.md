## DataVisualization:
This class shall be used to include all Data Visualization techniques to be feed to the Machine Learning Models

###  balance_imbalance_check
This method will be used to plot the balance/imbalance datasets using barplot/countplot
Input: data: the input dataframe with target column.
     target: target column name.
Output: plot of target variable value count.
```python
   def balance_imbalance_check(self, dataframe, target):
            sns.barplot(x='is_promoted', y='is_promoted', data=dataframe,
                        estimator=lambda x: len(x) / len(dataframe) * 100)
            plt.xlabel('ispromoted')
            plt.ylabel('percentage')
            plt.title('Balance Imbalance Count')
            plt.savefig("static/graphs/imbalance.png")
```
###   correlation_heatmap
This method will be used to generate interactive heatmap plot to show the pairwise correlation of input variables
Input Description: data: the input dataframe with target column.
Output: returns json file with correlation information that can be used by plotly to generate interactive plots.
``` python 
 def correlation_heatmap(self, dataframe):
            data = dataframe.select_dtypes(include=[np.number])

            plotdata = [go.Heatmap(
                z=data.corr(),
                x=list(data.columns),
                y=list(data.columns)
                ,dx=1,dy=1
                )]
            graphJSON = json.dumps(plotdata, cls=plotly.utils.PlotlyJSONEncoder)

            return graphJSON
```
