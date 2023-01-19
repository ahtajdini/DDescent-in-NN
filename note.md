# A note about the project

Recently, I became familiar with an OpenAI's paper named "Deed double descent: where bigger models and more data hurt". 
The paper discusses the double descent phenomenon and its robustness across various architectures based on previous work by Belkin, et al.
But, what exactly is double descent? Essentially, as the model size grows while being trained on a fixed dataset size,
the model error initially decreases until the model overfits the data causing the error to increase.
However, after a certain point, the error decreases again, hence the name "double descent".

One reason I am interested in this topic is that the double descent phenomenon connects two widely different points of view
regarding the problem of overfitting. In the literature of modern statistics in the context of linear regression (For example in the "big yellow book" by Friedman, et al),
there is a lot of discussion focused on the problem of overfitting, and how simpler linear models are more effective and can be better generalized. 
Therefore, feature reduction methods, which I spent some time learning about, such as LASSO plays a crucial role in the linear regression to identify
which features are relevant and which ones are redundant.
However, at least in my studies of deep learning, the bias-variance tradeoff is not often emphasized, with the general belief being that both bias and variance 
can be easily lowered with large enough deep learning models. Therefore feature reduction methods like LASSO is not widely adopted in deep learning.
The double descent phenomenon shows that the correct picture is something in between these two paradigms.

Another cool aspect of double descent phenomenon is its universality. It happens for linear and various deep learning models.
As far as I understood, the complete theoretical understanding of double descent in deep learning models are still lacking. However,
this phenomenon has been also observed as a function of number of epochs and training examples.

To gain a deeper understanding of this concept, for starters, I replicated the results of OpenAI's paper for CIFAR-10 using Google Colab.
I also experimented with regularization and observed that by increasing the regularization parameter,
the double descent can be completely avoided. Currently, I am investigating the effect of learning rate on the double descent.
I believe that having a concrete theoretical explanation for this phenomenon and how it is generally connected to feature selections in deep learning models
is an important and exciting open question. 

## References

**Reconciling modern machine-learning practice and the classical bias–variance trade-off**, 
Mikhail Belkin, Daniel Hsu, Siyuan Ma, and Soumik Mandal, July 24, 2019 , PNAS 116 (32) 15849-15854

**Deed double descent: where bigger models and more data hurt**, Preetum Nakkiran, Gal Kaplun, Yamini Bansal, Tristan Yang, Boaz Barak, Ilya Sutskever,
arXiv: 1912.02292

**LassoNet: A Neural Network with Feature Sparsity**, Ismael Lemhadri, Feng Ruan, Louis Abraham, Robert Tibshirani, arXiv: 1907.12207
