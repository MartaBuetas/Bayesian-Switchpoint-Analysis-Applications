# Temporal series analysis via Bayesian Inference: Bayesian Switchpoint Analysis

Here I share the code I developed for my Physics Bachelor Thesis at the University of Zaragoza.

```
Buetas, M. (2022) Analysis of temporal series through Bayesian Inference. University of Zaragoza.
```

## An introduction to BSA

I have worked on the BSA technique based on Bayesian inference. It is used to estimate the changepoints that occurred during a stochastic process and therefore to understand its behavior. 

The Bayesian Switchpoint Analysis is a multidisciplinary tool with an active area of research. Currently, it can be easily implemented due to computing capacity improvements.

Following several measurements or observations over time, a temporal series **d** is obtained. We read this data set as a result of a stochastic process, a realization from a distribution. This distribution is called the likelihood ($\mathbb{P}$=(**d**|$\Theta$)) and it is a measure of how likely is to obtain the temporal series we had (given the parameters $\Theta$). We aim to infer the set of parameters that maximizes the likelihood, which is equivalent to optimizing our model.

## Jupyter Notebooks description

I have followed a common outline for the examples I am sharing. Firstly, data has been managed with the Pandas library. Lately, I have defined the model with PyMC3, initializing each parameter distribution and the likelihood shape. Finally, I have generated samples with Monte Carlo Markov Chains (MCMC). I have checked their right convergence to a stationary solution. This solution corresponds to the posterior distribution $\mathbb{P}(\Theta$|**d**), that is to say, given the observed data points, the probability to get the parameters set $\Theta$.

In detail, BSA looks for the distribution of the parameter $\tau$ (which corresponds to the moment of the changepoint). I conclude with plausible explanations for the final model.

I have used Jupyter Notebooks, which are independent for each example. It will be needed to have installed PyMC3, Theano, and Arviz.
A short description of each Notebook's content:

 - "BIZI": Original local application to the public transport system BIZI in Zaragoza (Spain). Due to laws and other changes in the city, from the beginning of the service in May 2008, users have been changing their behavior. I have implemented this Bayesian technique to infer when these changes occurred and to deduce the cause, from my experience as a citizen. To run the notebook it is necessary to download the data from the [original source](https://openurbanlab.com/2019/12/02/ojo-al-dato-los-datos-de-el-periscopio-2019/) and introduce them in the `bizi` folder.
 
 - "WELL-LOG": Well-logging data are measurements of the nuclear magnetic response from underground rocks. When there is a change of layer, a discontinuity in the signal is registered. Using BSA and the measured signal, I find the switch points where there are changes between two different layers. The data, available in `data/well.dat`, were obtained from the book [Numerical Bayesian Methods Applied to Signal Processing](https://link.springer.com/book/10.1007/978-1-4612-0717-7).
 
 - "CoalMiningDisasters": I have reproduced a classic example. Here I use the technique to look for the switch point in the number of annual disasters in United Kingdom coal mines from 1851 to 1962. I found a correlation between the results and external sources. The data, available in `data/mining.csv`, were obtained from the article [Hierarchical Bayesian Analysis of Changepoint Problems](https://www.jstor.org/stable/2347570).
 
 - "STEPS": During the development of this project, I had a little accident with my foot. This caused changes in my behavior. From my smart watch steps data, I could find the changepoints when those changes happened. They showed consistency with reality. The data is available in `data/steps.csv`.
 
Author: Marta Buetas Arcas

---

# An??lisis de series temporales via Inferencia Bayesiana: Bayesian Switchpoint Analysis

Os comparto el c??digo que desarroll?? para mi Trabajo de Fin de Grado del Grado en F??sica de la Universidad de Zaragoza. 

```
Buetas, M. (2022) An??lisis de series temporales v??a inferencia Bayesiana. Universidad de Zaragoza.
```

## Introducci??n de la t??cnica

He trabajado con la t??cnica de inferencia Bayesiana BSA (Bayesian Switchpoint Analysis) que se usa para estimar los cambios que se han producido en la evoluci??n de un proceso estoc??stico y, as??, entender su comportamiento. Supone un ??rea activa de investigaci??n con aplicaciones muy transversales y que actualmente resultan mucho m??s f??cil de implementar gracias a las mejoras en nuestra capacidad de computaci??n. 

Tras realizar una serie de observaciones o medidas a lo largo de cierto tiempo, tendremos una serie temporal de datos **d**. Interpretaremos este conjunto de datos como un resultado de un proceso estoc??stico, es decir, una realizaci??n de una distribuci??n. Esta distribuci??n de probabilidad ser?? la verosimilitud o "likelihood" ($\mathbb{P}$=(**d**|$\Theta$)), una medida de c??mo de probable es obtener la serie temporal de la que disponemos, dados unos par??metros $\Theta$. Nuestro objetivo ser?? inferir los par??metros que maximicen la verosimilitud, lo que equivaldr?? a optimizar nuestro modelo. 

## Explicaci??n de los Notebooks

Para los ejemplos que presento aqu??, he seguido un esquema general com??n. En primer lugar, los datos los he gestionado y organizado con la librer??a Pandas de Python. Posteriormente, he definido el modelo con PyMC3, inicializando las distribuciones de cada par??metro implicado y la distribuci??n de verosimilitud. Finalmente, he generado las muestras con Cadenas de Markov Monte Carlo (MCMC). He comprobado su correcta convergencia a una soluci??n estacionaria. Esta soluci??n ser?? la distribuci??n posterior de los par??metros $\mathbb{P}(\Theta$|**d**), es decir, dados unos datos observados, la probabilidad de que los par??metros sean $\Theta$. 

En concreto, el BSA se centra en la obtenci??n de la distribuci??n del par??metro $\tau$ (que corresponde al instante en el que se da el cambio). Concluir?? con las explicaciones plausibles que dan forma al modelo obtenido.

Para la aplicaci??n pr??ctica de la t??cnica he usado Notebooks de Jupyter. Los Notebooks son independientes para cada ejemplo. Har?? falta tener instalado PyMC3, Theano y Arviz.

Aqu?? una breve explicaci??n del contenido de cada Notebook:

 - "BIZI": Aplicaci??n local de forma original al sistema de transporte urbano Bizi de Zaragoza (Espa??a). Desde el comienzo del servicio en mayo de 2008, a causa de leyes y otros cambios en la ciudad, los usuarios han ido variando su comportamiento. He aplicado esta t??cnica Bayesiana para inferir cu??ndo ocurrieron estos cambios y deducir, con nuestra experiencia como ciudadanos, el por qu??. Para ejecutar el notebook es necesario descargar los datos de la [fuente original](https://openurbanlab.com/2019/12/02/ojo-al-dato-los-datos-de-el-periscopio-2019/) e introducirlos en la carpeta `bizi`.
 
 - "WELL-LOG": Los datos de perfilaje de pozos o "well-logging" consisten en medidas de la respuesta magn??tica nuclear de las rocas subterr??neas. Cuando hay un cambio de estrato, se produce una discontinuidad en la se??al. Utilizo el BSA para encontrar los switchpoints en los que hay cambios entre estratos, a partir de la se??al medida. Los datos, disponibles dentro de la carpeta `data/well.dat`, han sido obtenidos del libro [Numerical Bayesian Methods Applied to Signal Processing](https://link.springer.com/book/10.1007/978-1-4612-0717-7).
 
 - "CoalMiningDisasters": He reproducido un ejemplo cl??sico buscando un switchpoint en el n??mero de accidentes anuales en las minas de Reino Unido entre 1851 y 1962. Se encuentran correlaciones en los resultados con fuentes externas a los datos. Los datos, disponibles dentro de la carpeta `data/mining.csv`, han sido obtenidos del art??culo [Hierarchical Bayesian Analysis of Changepoint Problems](https://www.jstor.org/stable/2347570).
 
 - "STEPS": Durante el proceso de este trabajo tuve un peque??o accidente en el pie que provoc?? cambios en mi comportamiento. A partir de los datos de los pasos diarios de mi reloj inteligente, encuentro los instantes en los que estos cambios ocurren, consistentes con lo observado en la realidad. Los datos est??n disponibles en `data/steps.csv`.

Autora: Marta Buetas Arcas
