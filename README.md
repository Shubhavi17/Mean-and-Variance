#  Mean and variance of a discrete  distribution


# Aim : 

To find mean and variance of arrival of objects from the feeder using probability distribution


# Software required :  

Python and Visual components tool

# Theory:

The expectation or the mean of a discrete random variable is a weighted average of all possible
values of the random variable. The weights are the probabilities associated with the corresponding values. 
It is calculated as,

![image](https://user-images.githubusercontent.com/103921593/192938463-e34177f4-f188-48a0-bda2-8f6d1d660ed2.png)

The variance of a random variable shows the variability or the scatterings of the random variables.
It shows the distance of a random variable from its mean. It is calcualted as

![image](https://user-images.githubusercontent.com/103921593/192938695-99fedc01-34d5-4d36-84df-5880e766ed0c.png)


# Procedure :

1. Construct frequency distribution for the data

2. Find the  probability distribution from frequency distribution.

3. Calculate mean using 
   
   ![image](https://user-images.githubusercontent.com/103921593/192940431-03b81777-c54d-4286-b4f4-82dfe7666b4c.png)

4. Find  
   
      ![image](https://user-images.githubusercontent.com/103921593/192940255-2d9dd746-6875-4a6d-877b-6da6cdb96ab1.png)

5.  Calculate variance using 
  
      ![image](https://user-images.githubusercontent.com/103921593/192942852-913550a9-fabe-4a55-b956-0487b18bbd97.png)


# Experiment :

![image](https://user-images.githubusercontent.com/103921593/229993174-5b67e57e-3e01-4ac4-9f83-410a932b22bf.png)

# Program :
```
import numpy as np
from scipy.stats import poisson, expon

def estimate_poisson_mean(arrival_times):
    # Estimate lambda (average rate) from the data
    lam = len(arrival_times) / max(arrival_times)
    return lam

def estimate_exponential_mean(arrival_times):
    # Estimate lambda (average rate) from the data
    lam = 1 / np.mean(np.diff(arrival_times))
    return lam

def calculate_mean_variance(arrival_times, distribution):
    if distribution == 'poisson':
        lam = estimate_poisson_mean(arrival_times)
        mean = lam
        variance = lam
    elif distribution == 'exponential':
        lam = estimate_exponential_mean(arrival_times)
        mean = 1 / lam
        variance = 1 / (lam ** 2)
    else:
        raise ValueError("Invalid distribution type. Choose 'poisson' or 'exponential'.")

    return mean, variance

# Example arrival times (replace this with your actual data)
arrival_times = [1, 2, 4, 6, 8, 10]

# Choose the distribution type ('poisson' or 'exponential')
distribution_type = 'exponential'

mean, variance = calculate_mean_variance(arrival_times, distribution_type)
print(f"Estimated Mean: {mean}")
print(f"Estimated Variance: {variance}")
```
```
# Output :

![Screenshot 2024-03-29 194214](https://github.com/Shubhavi17/Mean-and-Variance/assets/150005085/d5052cf6-ad7e-4905-a8b1-8b79fa3e2efb)

# Results :
The mean and variance of arrivals of objects from feeder using probability distribution are calculated.

