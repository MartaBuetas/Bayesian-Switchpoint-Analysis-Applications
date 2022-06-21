# Temporal series analysis via Bayesian Inference: Bayesian Switchpoint Analysis

Here I share the code I developed for my Physiscs Bachelor Thesis at the University of Zaragoza.

I have worked on the BSA technique based in Bayesian inference. Tt is used to estimate the changepoints that ocurred during an estochastic process and therefore understand its behaviour. 

Author: Marta Buetas Arcas

# Análisis de series temporales via Inferencia Bayesiana: Bayesian Switchpoint Analysis

Os comparto el código que desarrollé para mi Trabajo de Fin de Grado del Grado en Física de la Universidad de Zaragoza. 

He trabajado con la técnica de inferencia Bayesiana BSA (Bayesian Switchpoint Analysis) que se usa para estimar los cambios que se han producido en la evolución
de un proceso estocástico y, así, entender su comportamiento. Supone un área activa de investigación con aplicaciones muy transversales y que actualmente resultan mucho más fácil de implementar gracias a las mejoras en nuestra capacidad de computación. 

Partiendo de una serie de datos observados $\textbf{d}$, defino un modelo acorde a ellos con el tipo de distribución que genere cada punto.  
  Nuestro objetivo ser´a inferir los par´ametros $\Theta$, a partir de unos datos observados $\textbf{d}$. Para ello, 
Para la aplicación práctica de la técnica he usado Notebooks de Jupyter. Los Notebooks son independientes, hará falta tener instalado PyMC3, Theano y Arviz... 
(mirar apartado 3.1)

he seguido un esquema general com´un en todos los casos. En primer lugar, los datos los he gestionado y organizado con la librer´ıa Pandas de Python.
Posteriormente, he definido el modelo con PyMC3, inicializando las distribuciones de cada par´ametro implicado y la distribuci´on de verosimilitud. Finalmente, he generado las
muestras con Cadenas de Markov Monte Carlo (MCMC). He comprobado su correcta
convergencia a una soluci´on estacionaria, es decir, a la distribuci´on posterior buscada,
para concluir con las explicaciones plausibles que dan forma al modelo obtenido.

Autora: Marta Buetas Arcas
