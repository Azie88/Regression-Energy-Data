# Appliances Energy Prediction 💡

Testing Multiple Regression Models to Predict Energy Efficiency of Buildings.

Multiple linear regression establishes the relationship between the target variable and the predictors (usually two or more). In reality, several factors contribute to a certain outcome as opposed to just one as suggested by simple linear regression. Multiple linear regression has similar assumptions as simple linear regression and also assumes that there is no significant correlation between the predictors. While the relationship between variables can be linear, it allows for non-linear relationships that are not straight lines.


## Dataset 💾

The dataset is Appliances Energy Prediction data. The data is time series data at 10 min intervals for about 4.5 months. The house temperature and humidity conditions were monitored with a ZigBee wireless sensor network. Each wireless node transmitted the temperature and humidity conditions around 3.3 min. Then, the wireless data was averaged for 10 minutes periods. The energy data was logged every 10 minutes with m-bus energy meters. Weather from the nearest airport weather station (Chievres Airport, Belgium) was downloaded from a public data set from Reliable Prognosis (rp5.ru), and merged together with the experimental data sets using the date and time column. 

Two random variables have been included in the data set for testing the regression models and to filter out non predictive attributes (parameters). The attribute information can be seen below.

<table>
<thead><tr>
<th><strong>Feature Name</strong></th>
<th><strong>Description</strong></th>
<th><strong>Data Type</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>date</td>
<td>year-month-day hour:minute:second</td>
<td>datetime64[ns]</td>
</tr>
<tr>
<td>Appliances</td>
<td>energy use in Wh</td>
<td>int64</td>
</tr>
<tr>
<td>lights</td>
<td>energy use of light fixtures in the house in Wh</td>
<td>int64</td>
</tr>
<tr>
<td>T1</td>
<td>Temperature in kitchen area, in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_1</td>
<td>Humidity in kitchen area, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T2</td>
<td>Temperature in living room area, in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_2</td>
<td>Humidity in living room area, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T3</td>
<td>Temperature in laundry room area</td>
<td>float64</td>
</tr>
<tr>
<td>RH_3</td>
<td>Humidity in laundry room area, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T4</td>
<td>Temperature in office room, in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_4</td>
<td>Humidity in office room, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T5</td>
<td>Temperature in bathroom, in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_5</td>
<td>Humidity in bathroom, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T6</td>
<td>Temperature outside the building (north side), in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_6</td>
<td>Humidity outside the building (north side), in %</td>
<td>float64</td>
</tr>
<tr>
<td>T7</td>
<td>Temperature in ironing room , in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_7</td>
<td>Humidity in ironing room, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T8</td>
<td>Temperature in teenager room 2, in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_8</td>
<td>Humidity in teenager room 2, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T9</td>
<td>Temperature in parents room, in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>RH_9</td>
<td>Humidity in parents room, in %</td>
<td>float64</td>
</tr>
<tr>
<td>T_out</td>
<td>Temperature outside (from Chievres weather station), in Celsius</td>
<td>float64</td>
</tr>
<tr>
<td>Press_mm_hg</td>
<td>Pressure (from Chievres weather station), in mm Hg</td>
<td>float64</td>
</tr>
<tr>
<td>RH_out</td>
<td>Humidity outside (from Chievres weather station), in %</td>
<td>float64</td>
</tr>
<tr>
<tr>
<td>Windspeed</td>
<td>Wind speed (from Chievres weather station), in m/s</td>
<td>float64</td>
</tr>
<tr>
<td>Visibility</td>
<td>Visibility (from Chievres weather station), in km</td>
<td>float64</td>
</tr>
<tr>
<td>Tdewpoint</td>
<td>Tdewpoint (from Chievres weather station), in °C</td>
<td>float64</td>
</tr>
<tr>
<td>rv1</td>
<td>Random variable 1, nondimensional</td>
<td>float64</td>
</tr>
<tr>
<td>rv2</td>
<td>Random variable 2, nondimensional</td>
<td>float64</td>
</tr>
<tr>
</tbody>
</table>


## How to Use The Repository

You need to have [`Python 3`](https://www.python.org/) on your system. Then you can clone this repo and being at the repo's `root :: repository_name> ...`

1. Clone this repository: `git clone https://github.com/Azie88/Regression-Energy-Data`
2. On your IDE, create A Virtual Environment and Install the required packages for the project:

- Windows:
        
        python -m venv venv; 
        venv\Scripts\activate; 
        python -m pip install -q --upgrade pip; 
        python -m pip install -qr requirements.txt  

- Linux & MacOs:
        
        python3 -m venv venv; 
        source venv/bin/activate; 
        python -m pip install -q --upgrade pip; 
        python -m pip install -qr requirements.txt  

The two long command-lines have the same structure. They pipe multiple commands using the symbol ` ; ` but you can manually execute them one after the other.

- **Create the Python's virtual environment** that isolates the required libraries of the project to avoid conflicts;
- **Activate the Python's virtual environment** so that the Python kernel & libraries will be those of the isolated environment;
- **Upgrade Pip, the installed libraries/packages manager** to have the up-to-date version that will work correctly;
- **Install the required libraries/packages** listed in the `requirements.txt` file so that they can be imported into the python script and notebook without any issue.

**NB:** For MacOs users, please install `Xcode` if you have an issue.

3. Explore the Jupyter notebook for detailed steps and code execution.

## Author :writing_hand:

Andrew Obando

<a href="https://www.linkedin.com/in/andrewobando/"><img align="left" src="https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white" alt="Andrew Obando | LinkedIn"/></a>
<a href="https://medium.com/@obandoandrew8">
![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)
</a>

-----

Feel free to star ⭐ this repository if you find it helpful!
