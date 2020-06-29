# The central, Gaussian or normal distribution

$\leftarrow$ [Back to Chapters](./index.html)





## Exercise 7.1
TO DO

<!---

Possible interpretations: 

1) We literally take $\epsilon_n=\sum_1^n \varepsilon_i$ with $\varepsilon_i\sim \epsilon$ and i.i.d. Then $\langle \epsilon_n^2 \rangle=n \langle \epsilon^2\rangle$. 



2) We suppose $\epsilon=\sum_{i=1}^{n}\epsilon_i$ of i.i.d. random noises $\epsilon_i$, with $\epsilon_i$ therefore satisfying $\langle \epsilon_i \rangle=0$ and  $n\langle \epsilon_i^2 \rangle=\langle \epsilon^2 \rangle$. 

--->


## Exercise 7.2

Consider the family of distributions $p_{\mu, \sigma}(v)$. 

We want to express fact that convolution of $p_{\mu, \sigma}(v)$ with $q(v)$ still belongs to the same family. I will prefer to work with parameter $\nu=\sigma^2$ instead. To avoid confusion the variable $v$ will be replaced by $x$. So we work with the family $p_{\mu, \nu}(x)$.

Let $\mu_q=\langle \epsilon\rangle_q$ be the mean and $\nu_q=\langle \epsilon^2\rangle_q-\langle \epsilon\rangle_q^2$ the variance of $q$. Then the new distribution must be $p_{\mu+\mu_q, \nu+\nu_q}(x)$. At the same time the expansion 7.20 becomes 

$$p_{\mu+\mu_q, \nu+\nu_q}(x)=p_{\mu, \nu}(x)-\mu_q \frac{\partial}{\partial x} p_{\mu, \nu}(x)+\frac{1}{2}(\nu_q+\mu_q^2)\frac{\partial^2}{\partial^2 x} p_{\mu, \nu}(x)+\ldots$$

Taylor expanding around $\mu, \nu$

$$p_{\mu+\mu_q, \nu+\nu_q}(x)= p_{\mu, \nu}(x)+\mu_q\frac{\partial}{\partial \mu}p_{\mu, \nu}(x)+ \nu_q\frac{\partial}{\partial \nu}p_{\mu, \nu}(x)+ $$

$$\frac{1}{2} \mu_q^2 \frac{\partial^2}{\partial^2 \mu}p_{\mu, \nu}(x) +\frac{1}{2}\nu_q^2 \frac{\partial^2}{\partial^2 \nu}p_{\mu, \nu}(x)+  \mu_q \nu_q \frac{\partial^2}{\partial \mu \partial \nu} p_{\mu, \nu}(x)$$

$$ $$

Now **if** we wanted this to be true for arbitrary (small) $\mu_q, \nu_q$ we would have equality of Taylor coefficients:

 $$-\frac{\partial}{\partial x}p_{\mu, \nu}(x)=\frac{\partial}{\partial \mu}p_{\mu, \nu}(x)$$
 
 $$\frac{1}{2}\frac{\partial^2}{\partial^2 x} p_{\mu, \nu}(x)=\frac{\partial}{\partial \nu}p_{\mu, \nu}(x)= \frac{1}{2} \frac{\partial^2}{\partial^2 \mu}p_{\mu, \nu}(x)$$
 
 where the first equation says that $p_{\mu, \nu}(x)$ is a function of $x-\mu$ and not of $\mu$ and $x$ separately, $p_{\mu, \nu}(x)=f_\nu(x-\mu)$. From this $\frac{\partial^2}{\partial^2 x} p_{\mu, \nu}(x)=\frac{\partial^2}{\partial^2 \mu} p_{\mu, \nu}(x)$ follows, and we simply recover the more general Gaussina family $p_{\mu,\nu}(x)=\frac{1}{\sqrt{2 \pi \nu}} \exp\{-\frac{(x-\mu)^2}{2 \nu}\}$ as in 7.23.
 
 However, **if** we instead think of $\mu$ and $\nu$ as  $\mu(t)$ and $\nu(t)$ so that the family $p_t(x)=p_{\mu(t), \nu(t)}(x)$ is a single-parameter family, then the expansions become expansions in terms of $t$:
 with $\mu_q(t)=\mu_q'(0)t+o(t^2)$, $\nu_q(t)=\nu_q'(0)t+o(t^2)$
 
 $$p_{\mu+\mu_q(t), \nu+\nu_q(t)}(x)=p_{\mu, \nu}(x)+[-\mu_q'(0) \frac{\partial}{\partial x} p_{\mu, \nu}(x)+\frac{1}{2}\nu_q'(0)\frac{\partial^2}{\partial^2 x} p_{\mu, \nu}(x)]t+$$
 
 $$p_{\mu+\mu_q(t), \nu+\nu_q(t)}(x)=p_{\mu, \nu}(x)+\frac{\partial}{\partial t}p_{\mu, \nu}(x) t+o(t^2)$$

<!--
$$p_{\mu+\mu_q(t), \nu+\nu_q(t)}(x)= p_{\mu, \nu}(x)+[\mu_q'\frac{\partial}{\partial \mu}p_{\mu, \nu}(x)+ \nu_q'\frac{\partial}{\partial \nu}p_{\mu, \nu}(x)]t+ o(t^2)$$

--->
 
 Equating Taylor coefficients:
 
 $$ \frac{\partial}{\partial t}p_{t}(x)= -\mu_q' \frac{\partial}{\partial x} p_{t}(x)+\frac{1}{2}\nu_q'\frac{\partial^2}{\partial^2 x} p_{t}(x)$$
 
 
 This is a [Fokker-Plank equation](https://en.wikipedia.org/wiki/Fokker%E2%80%93Planck_equation), albeit a very special one, with $\mu(x,t)=\mu'(0)$, $\sigma^2(x,t)=\nu'(0)$, corresponding to the stochastic process where the drift $\mu$  and diffusion coefficient  $\nu/2$ are both constant. Denote $\mu'(0)=m$ and $\nu'(0)=v$.
 
 Changing coordinates to $y(x,t)=x-mt$ aka $x(y,t)=y+mt$, we have
 $$p_t(x(y,t))=p_t(y+mt)=:q_t(y)$$
 
 and compute by chin rule
 
 $$\frac{\partial}{\partial t}q_{t}(y)=\frac{\partial}{\partial t}p_{t}(x(y,t))=\frac{\partial}{\partial t}p_{t}(y+mt)+ m  \frac{\partial}{\partial x}p_{t}(y+mt)$$
 
 while 
 $$\frac{1}{2}v\frac{\partial^2}{\partial^2 y} q_{t}(y)=\frac{1}{2}v\frac{\partial^2}{\partial^2 y} p_{t}(x(y,t))=\frac{1}{2}v\frac{\partial^2}{\partial^2 x} p_{t}(y+mt) $$
 
 So the substitution we made reduces the Fokker-Plank equation we have (with drift) to the diffusion equation (without drift) i.e. 7.22 (with $\sigma^2=t$), which by 7.23 has solution $q_t(y)=\frac{1}{\sqrt{2\pi t }}\exp\{-\frac{y^2}{2t}\}$, or, after substitution 
 
 $$p_t(x)=\frac{1}{\sqrt{2\pi t }}\exp\{-\frac{(x-mt)^2}{2t}\}$$
 
 This has variance $\sigma^2=t$ so we can rewrite it as $p(x)=\frac{1}{\sqrt{2\pi \sigma^2 }}\exp\{-\frac{(x-m\sigma^2)^2}{2\sigma^2}\}$, as in the formulation of the exercise.
 
 <!---
 
 $$=\mu_q'\frac{\partial}{\partial \mu}p_{\mu, \nu}(x)+ \nu_q'\frac{\partial}{\partial \nu}p_{\mu, \nu}(x)$$
 
 --->
 

 
 
 ##  Exercise 7.3 preliminary remarks.
 

 
 I interpret this as follows. We are now considering evolution of beliefs about noise-generating process, and want to update this based on data and see that as the amount of data grows our posterior beliefs about the noise-generating process will imply beliefs about frequencies of noise that will converge to those produced by true frequencies $f(e)$. 
 
In order to talk about the above meaningfully in mathematical sense, one needs to define some space of noise-genera processes in such a way that formulating a prior probability over it is possible, and also define in what sense the posterior beliefs about frequencies "converge". 

Since we only observe real-valued noise data (and no other type of information about the noise-generating processes) the space of noise-generating processes can be taken to be the set of real-valued stochastic processes. Now this is still very large. Now one could either 1) take only noise-generating processes that generate noise in i.i.d. way 2) focus only on the beliefs about "frequencies" i.e. how often various values (close to) various $e$s are observed - or both.


The intuition is that those processes that produce incorrect frequency of $e$s will be suppressed in he update (due to a mechanism like that in the Borel's law of large numbers), leaving only the process that do have the correct frequencies in the "posterior distribution over processes", whatever that means. To illustrate some of the difficulties, consider the simple case of discrete time and processes that just i.i.d. sample from some probability distribution. Consider a distribution which moreover has a density $p$. Then a particular dataset $e_1, \ldots, e_n$ has likelihood $\prod_{i=1}^{N} p(e_i)$. At each finite $N$ the closer our distribution $p$ is to the empirical distribution(of $\frac{1}{N}\sum_i \delta{e_i}$) the higher the likelihood; this seems problematic. Perhaps one has to discretize the set of possible $e$s and then take limit, or simply use some more sophisticated analysis.


 
 ## Footnote 12
 