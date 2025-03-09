# Erica-Jeanne-Melendres

import numpy as np
import scipy.stats as sts
import matplotlib.pyplot as plt

mu = np.linspace(1.65, 1.8, num=50)

uniform_distribution = sts.uniform.pdf(mu, loc=1.65, scale=0.15) + 1   
uniform_distribution = uniform_distribution / uniform_distribution.sum()  
beta_distribution = sts.beta.pdf(mu, a=2, b=5, loc=1.65, scale=0.15)   
beta_distribution = beta_distribution / beta_distribution.sum()  l

plt.plot(mu, beta_distribution, label="Beta Distribution")
plt.plot(mu, uniform_distribution, label="Uniform Distribution")
plt.xlabel(r"Value of $\mu$ in meters")
plt.ylabel("Probability Density")
plt.legend()
plt.show()


def likelihood_func(datum, mu):
    likelihood_out = sts.norm.pdf(datum, mu, scale=0.1)  
    return likelihood_out / likelihood_out.sum()  
