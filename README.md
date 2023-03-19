# Decomposing the Equity Yield Term Structure

## A calculation of equity yields on Eurostoxx 50 and a variance decomposition into risk premium and expected growth.


This project is about calculating **equity yields** $e_t^{(n)}$ on the Eurostoxx 50 and to decompose them into a its dividend **risk premium** $\theta_t^{(n)}$ and expected **dividend growth** $g_t^{(n)}$: 

$$ e_t^{(n)} = \theta_t^{(n)} - g_t^{(n)} $$

$e_t^{(n)}$ is derived from dividend futures data and $g_t^{(m)}$ is estimated using a prediction OLS model and a VAR(1) model. The methodology follows that of van Binsbergen et. al. (2013). The main part of the exercise is to do a variance decomposition of equity yields to gain insights into the predictability of dividend risk premium and expected growth rates.

## 1. Notebook Outline 

Note that the notebook is separated into 11 sections:

1. Model Specification
2. Preliminaries
3. Data Importation
4. Data Handling
5. Figure 1
6. Finalize Features and Outcomes
7. Figure 2
8. Predictive OLS Model
9. VAR(1) Model
10. Variance Decomposition
11. Appendix Plots

## 2. Preliminaries

The following specifications (version) were used for this project:
- Computer: MacBook Air M1 GPU
- Operating system: Darwin 
- Python (3.10.6)
- IDE: Jupyter Notebook (6.5.2)
- Pandas (1.5.2)
- Numpy (1.24.1)
- xlrd (2.0.1)
- openpyxl (3.0.10)
- statsmodels (0.13.5)
- plotly (5.13.1)
- platform (1.0.8)

In *section 1* the code imports the required modules for the project and checks for the versions for each module.

*NOTE: if a package is not installed on the computer, you need to install the module first*. 

## 3. Replication Files

To replicate the tables and figures used in the assignment. The aforementioned modules needs to be used. Furthermore, the two underlying data files: 

- dataset.xls
- dividend_data.xls

needs to be in *the same folder* as the jupyter notebook. In the first cell in *section 3*, specify the current working directory (*cwd*) where all replication files (including the notebook) are located. The *dataset.xls* contains the trading day prices of the FEXD dividend futures on the Eurostoxx 50 DVP. The file *dividend_data.xls* contains the Eurostoxx 50 DVP. 

## 4. Full Paper Replication

To run the code as intended, please make sure that all the modules in *section 2* are installed before importing them. Ideally, use the same versions of each module as we did. Furthermore, pay attention to *section 3: Data Importation*. In order to import the data as intended, find the working directory of all replication files and change the directory to that folder in the following line:

<img width="474" alt="Screenshot 2023-03-19 at 17 19 16" src="https://user-images.githubusercontent.com/123584534/226189518-cb964f6e-df43-456e-bd1a-235aabf8c4d4.png">

Do *not* change the filename or sheet-name variables in the cell.

To replicate all figures and tables used in the paper, take note of the only cell in *section 1: Model Specification*. It is in this cell where you can change between the model specifications used. As outlined in the paper, we consider 3 models: 

1. BHK: $e_t^{(2)}$ and $e_t^{(5)}$
2. SML: $e_t^{(1)}$, $e_t^{(5)}$ and $e_t^{(10)}$
3. S2: $e_t^{(1)}$ and $e_t^{(2)}$

To implement the BHK model, simply uncomment the 'VARS' variable where we indicate that the BHK specification is, and then run every cell in the notebook from start to end. Note that it may take some seconds for some of the cell to execute, depending on GPU.

<img width="296" alt="bhk_spec" src="https://user-images.githubusercontent.com/123584534/226125909-62f7ec69-46e8-4c65-8df2-960efaf1cf3b.png">

Similarly, to implement the SML model, *reset the kernel* and simply uncomment the 'VARS' variable where we indicate that the SML specification is and run every cell again.

<img width="286" alt="sml_spec" src="https://user-images.githubusercontent.com/123584534/226125910-a3184ce7-7965-456e-b3e6-e782f1ee2c6d.png">

Finally, to implement the S2 model, *reset the kernel* and simply uncomment the 'VARS' variable where we indicate that the S2 specification is and run every cell again.

<img width="299" alt="s2_spec" src="https://user-images.githubusercontent.com/123584534/226126010-f3a4b5c9-827c-4c96-a8af-aaa81f294d17.png">

## 5. Where to find outputs included in the paper?

Simply, for Figure 1, Figure 2, and the Appendix figures (Figure 5 and Figure 6), look at the output in sections 5, 7, and 11, respectively.

In the only cell in *section 8: Predictive OLS Model*, the OLS output in Table 2 for the active model is outputted, as well as its respective panel that is in Figure 3. Therefore, to get every number in the OLS portion of Table 2, you need to run the notebook for each model and take note of the output for each active model. Similarly, to get every panel of Figure 3, you need to save the figure output for each active model.

The rest of Table 2, the part that pertains to the VAR(1) model is contained under the following section, *section 9: VAR(1) Model*. In the first cell in that section you will find the output to the VAR(1) portion of Table 2. Again, the output pertains only to the active model, and to replicate the results for all models used, you will have to run the notebook for each model and take note of the output for each active model. 

The last cell in *section 9: VAR(1) Model* also contains the outputs to Figure 4 in the paper. The output contains the time-series decomposition of equity yields at all maturities between 1-10 years. In Figure 4, we only include maturities 2, 5, and 10 for brevity. To find these figures, simply save the 2nd, 5th, and 10th figure in the output. Again, the output pertains only to the active model, and to replicate the figures for all models used, you will have to run the notebook for each model and take note of the output for each active model. 

Finally, to replicate Table 3 from the paper, consider *section 10: Variance Decomposition*. There are 2 cells of code in the section and the second one outputs the decomposition for the active model. Again, the output pertains only to the active model, and to replicate the output for all models, you will have to run the notebook for each model and take note of the output for each active model. 

***Fin!***
