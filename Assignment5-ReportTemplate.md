**SENG 637- Dependability and Reliability of Software Systems***

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#: 15      |   |
|-----------------|---|
| Student Names:  |   |
| Sina Salimian   |   |
| Zahra Safari    |   |
| Alireza Esmaili |   |
| Sahar Hajjar Zadeh |   |
| Mehrnaz Senobari |   |
| Fatemeh Ghaffarpour |   |

# Introduction
In this assignment, we focus on analyzing integration test data with the help of tools designed for reliability assessment. We explore two distinct methods for evaluating failure data:

1) Reliability Growth Testing
2) Reliability Assessment through a Reliability Demonstration Chart (RDC)

We will apply the first method using SRTAT and the second method using RDC.
# 

# Assessment Using Reliability Growth Testing 
Using the C-SFRAT tool, we import the failure dataset and display the MVF and the Intensity graphs.
<img src="./media/1-Data-Upload-and-Model-Selection-MVF.png"  width="400px"/>
<img src="./media/3-Intensity-graph.png"   width="400px"/>

Next, we select all available models, execute the estimations for each, and compare their outcomes based on their log-likelihood values. 
As illustrated below, the two top-performing models are DW3 (covariates: F) and IFRGSB (covariates: E, F), which exhibit the lowest log-likelihoods compared to the others.
<img src="./media/2-Model-comparison.png"  />

Additionally, the model with the poorest performance is IFR SB (no covariates).
<img src="./media/5-worst.png"  />

To gain a clearer insight into the functioning of our models, we select each one and display their results collectively on a single graph.
<img src="./media/4-all-graphs.png"  />

Next, we choose our best two models (DW3 and IFRGSB) along with the lowest-performing model (IFR SB).
<img src="./media/6-bests-worst.png"  />

Here is the intensity graph showcasing the top two models.
<img src="./media/7-bests-intensity.png"  />

Here is the MVF graph displaying  the top two models.
<img src="./media/8-bests-MVF.png"  />

### Result of Range Analysis
#### Reliability

While testing often yields a vast amount of data, not all of it is pertinent. Conducting range analysis allows us to focus only on the failure data that is relevant to our study.

One method to determine the appropriate data range for analysis is the Laplace test. This test compares the observed failure data with the expected failure data derived from a specific model. By doing so, it identifies data points that fall outside the expected range and should therefore be excluded.

However, the C-SFRAT tool lacks the capability to perform range analysis using the Laplace test or similar methods. As a workaround, we have used Python to simulate Laplace analysis, employing the formula provided in our notes. Below is the plot for Laplace analysis.
<img src="./media/9-laplace.png"  />

After analyzing the plotted results, we observed improvements in reliability between intervals 3-18 and 27-31. Typically, a Laplace factor ranging from -2 to 2 suggests stable reliability, indicating that our data achieves stable reliability starting from the 19th interval onward. Additionally, negative Laplace factor values signify a decline in failure intensity, while positive values indicate an increase. Our data shows negative Laplace values between intervals 3-20 and 28-31. Consequently, a suitable range containing a sufficient number of data points for analysis would be from interval 1 to 20.

#### Failure rate
Next, we present the plot for the failure rate from intervals 2 to 31. We excluded the first interval because the results significantly differed from the subsequent intervals, which could skew the overall assessment of the failure rate.
<img src="./media/10-failure.png"  />

### Prediction
Regarding our prediction, we have established a failure intensity rate of 1.3 based on the plot above. As indicated, this rate is expected to be reached within a single interval.
<img src="./media/11-prediction.png"  />

## Advantages and Disadvantages of Reliability Growth Analysis
- ## Advantages
  - Identifies and corrects failures early, enhancing product reliability.
  - Provides data-driven insights for resource allocation.
  - It is suitable with complex systems or products.
  - Predicts when reliability goals will be achieved to better plan production.

- ## Disadvantages
  - Consumes significant time and data, which can delay projects.
  - Reliability of analysis is tied to the accuracy and completeness of data.
  - Requires specialized knowledge and can be challenging to implement.
  - Can lead to unrealistic expectations if not all variables are accounted for.


# Assessment Using Reliability Demonstration Chart 

# 

# Comparison of Results

# Discussion on Similarity and Differences of the Two Techniques

# How the team work/effort was divided and managed

# 

# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
