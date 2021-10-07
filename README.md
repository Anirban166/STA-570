# STA-570

# Cheatsheet
- General
  - Prefer Bootstrap confidence intervals than other CIs
  - [Probability Distributions in R](https://www.stat.umn.edu/geyer/old/5101/rlook.html)

- Chapter 1
  - 

- Chapter 2
  -
  
- Chapter 3
  -
   
- Chapter 4
  -

- Chapter 5
  - Margin of Error (M.E.) = z<sub>(1-alpha/2)</sub> = std\.dev/sqrt(n)
  - C.I. = xbar plusminus Margin of Error
  - M.E./(Z<sub>(1-alpha/2)</sub>\*sd) = sqrt(n)
  - => n = (Z<sub>(1-alpha/2)</sub>\*sd)/M.E.)<sup>2</sup>

- Chapter 6
  - Significance testing steps:
  - Step 1: Pick alpha = significance level (for e.g. 95% = 0.05 = 1 = 0.95) = probability of erroneously suggesting change
  - Step 2: What variable and parameters interest you about which population?
  - Step 3: What is the past or popular or reasonable value for parameter above? (for H<sub>0</sub> or the null hypothesis)

- Copy Pasted Class Notes Brit

Ch2 first 3 sections important stuff to know
Outcome
Event
Union
Intersection
Mut exclusive/disjoint
Rules of probability functions
	Total = 1
	all prob between 0 and 1
	can compute independent thing something check text as long disjoint
P(AUB)+P(AnB)=P(A)+P(B)
P(A)=P(AnB)+P(AnB’)
Conditional prob.
	P(A|B)=P(AnB)/P(B) if B prob is not 0
Independent
* P(AnB)=P(A).P(B) ***if he asks whether independent, then you need to check with math!
* Also can use P(A|B)=P(A) using conditional probability
* might only have some info so know both tests

Notes on Board Tues class
Prob, discrete vs continuous, EV, Var, Common disc test,
Computational (as opposed to definitional) formula for var
extras he thought would be useful despite not being in book
Geometric distn
pf binomial ev
pf exponential lambdae^(-lambdax?)ev
pnorm(balh) but it’s almost always better to do mosaic::xpnorm(blah)

Class example 2.4.1
Binomial = a bunch of bernoulli’s
dropping a scientist onto a random forested place on earth 20 times
success is burned; failure is not burned
% burned = pi = 0.00003%
B = total number of burned forests united
n = 20 times
P(B=2) - 20!/(2! |8| = 0.00003%^2 * 0.99997%^B = dbinom(2,20,.00003/100)
 which is equal to 20 choose 2 * .00003%^2 * 0.999997%^20
result will probably be low because 2/20 is 10% and 10% is way higher than 0.00003% so we can expect that the prob of 10% burned should be low.

dbinom(x,n,pi)
x = number of success
n = number trials
pi = probably of success


Computational formula for variance:
V(X) see book for both discrete and continuous
V(X) = summation of (x-mu)^2(p(X=x)
V(X) = integral of (x-mu)^2(f(x)dx
V(X) = E(X^2) = [E(X)]^2
mu = 0(.1) + 1(.2) + 2(.3) + 3(.4)
Shortcuts:
E(X^2)=5
E(X) = 2
_________________
x^2       | 0   1   4  9   |
x            | 0   1   2  3  |
P(X=x)   | .1 .2. .3 .4  |
_______|__________|
On a test be able to calculate variance for a small table like this by hand

V(X) = (0-mu)^2(0.1) + (1-mu)^2(0.2) + (2-mu)^2(0.3) + (3-mu)^2(0.4)


Geometric
Geometric = # of attempts/failures before or until (can define either way) first success
pdf = p(X=x) = (1-p)^x-1 * p^1



ch2
1 b
1.7%
1c
80.2%
1d
37.2%
1e
32.2%/80.2%=0.401
1f




group_by(Type) makes 2 data frames one per type

Start of tues sept 7 start 570 stats (remote)
lock5stat site state key



570 -- sept 14 2021
pnorm takes axes values and spits out area under curve or probability

qnorm takes the area and spits out the values that give that area (reverse of pnorm)


Notes from class board:
Central limit theorem:
X~f(mean, sd, var,..)
X->random variable
f->dist/prob function
mean,sd,var->parameters

when we take a sample from the population, the mean, sd, var, median, etc are called the statistics. They’re random before we see them then once we see them, they’re not random anymore.

x bar is a RV which has a distr (related to f, maybe)
x bar has a mean, sd, var, and so on

We know from Central limit theorem, if x is normally distributed, then x bar is also going to be normal but it’ll be narrower:
x bar ~ N(mu x bar = mu x , sigma squared bar = sigma squared x divided by n)
Moreover, even if x isn’t normal,
x bar (dot over~) N(mu x bar = mu x , sigma squared bar = sigma squared x divided by n)
as long as n is big enough (usually about 30 assuming that X looks relatively normal to begin with)

Why the “maybe related to f” example:
let x be bin(1,.1) and x2 have the same distr
x1=0,1,or2
x2=0,1,or2
but x bar could be 0,1,2,.5,1.5
which is not binomially distributed 

expected value of a binomial distribution is n*pi
variance of a binomial distribution is n*pi(1-pi)

Not in textbook but good fyi: rule of thumb for binomial: if n*pi and n(1-pi) >= 5, then bar  dot over ~ N(mu, sigma squared)


Bootstrapping:
take a sample, replicate it a bunch
ie maybe grabbed 3 samples from population
now have like bunch of copies of 1,2,3 in a new bootstrap “population”
we hope that the bootstrap pop looks similar to the actual pop
if we conducted a simple random sample, then we have hope for having the bootstrap population look similar to the actual population
we take maybe 3 bootstrap samples each of same number as original sample (ie 3) and should look like the original sample

sta570 9/21/21

1a xpnorm(230, 222,5) where 5 is the sd
1b E(xbar)=E(x)=mu=222
1c var(xbar)=v(x)/n=25/6
1d sd(xbar)=sqrt of var(bar)=5/sqrt(6)
1e x~n(222,5) -> xbar~N(222,5/sqrt(6))
    xpnorm(230,222,5/(sqrt6))
3d P(XBar is within 1 mL of mu)
     mu=298
     P(XBar is between 297 and 299)
     xpnorm(c(297,299),…)
     can do 2 probabilities at once using c(297,299) which is a concatenate func
     fill in the mean and then standard deviation

instead of “norm” or “N” we replace with “t” distribution

pnorm is the probability for a normal distribution

first letter tells you what to do, and the next tells you what distribution

degrees of freedom tells you how thick the tails are
every estimated parameter is a loss of degree of freedom
normal distribution is like a t distribution with infinite degrees of freedom
asymptotic means that as n->infinity then t looks like a normal distribution and so as long as n is big, then these rules apply

upper means which t distribution
lower is the 0.95 for example
can do t_4^0.95=qt(0.95,df=4) give us the value gives us 90%

t_4^.9(0.9,4) gives us 80%

like how qnorm gives us the cutoff value on the x-axis
z_0.975=1.96=qnorm(0.975)


STA 570 sept 28
3x5in exam cheat sheet (index card for memory jogger and not info dump!)

sample size class question:
if we know sigma
example: amount of wiggle room that you want to afford yourself in the CI (ie thrones like you don’t wanna have 14 extra throne chairs. you might only want to be within 1 throne)
Use the ME to construct the CI
ME=z_{}*sig/sqrtn
CI = xbar +- ME
solve for sqrt of n to find the sample size desired
if n is not an integer, then just round up to nearest whole number
usually..^^^
if we don’t, then we use t (df=n-1) instead of z and s instead of sigma
or if we know that n is very large (but theoretically you should use t if you don’t know sigma but it doesn’t matter if n is big enough because t looks so similar z when n is large)

although in book, we theoretical and bootstrap CI, adam says he prefers bootstrap CI because you’ll find distribution for xbar and that makes no assumptions and its more true to the parent population. you can make bootstrap CI even if n is only 6 so that’s why bootstrap is most useful

Hypothesis Tests:
you can answer the machine calibration question using CIs even through it can be a hypothesis problem

step -1.
* discuss errors and desired power or budget (will go over Thursday)

step 0. (kind of fake first step)
* PART 1: Pick alpha=significance level= probability of erroneously enacting or suggesting change or rejecting the null if the null is true

* PART 2: What variable and parameter interest you about which population?

* PART 3: What is the past or popular or reasonable value for the parameter above? Better know what the other people believe before we propose any changes

step 1.
* Decide on the null hypothesis H0 or Hnaught: t-tests H0: mu=mu0 and write it in words. What parameter and population and some other thing too
* Collect data before this point but don’t examine before you pick alternative or even technically alpha
* HA = H1 = alternative hypothesis: H1: mu > mu0, mu < mu0, mu neq mu0 “what you believe might be true, or what value would signal a need for change” For example, the bottle filling example, we have 2 sides because we don’t want the soda level to be too low bc people will complain and too high might cause the bottle to explode or something
* PART 2: examine the data

step 2.
* compute Test Statistic: TS = (xbar-mu0)/(s/sqrtn)
* big values weird/alarming (xbar is the sample average which is our random variable)
* if it were z, then we would do the z-score. but we don’t because we usually don’t know sigma
* so for this example, the TS = t_{n-1=df}^{TS}

step 3.
* Decide if the test statistic is weird or not if the H0 was true
* P(observing this TS if the H0 was true) = p-value
* If p<alpha, then our sample was weird or “the previous people” were wrong and we reject H0 in favor of H1
* pt(TS, df=n-1)  if t or pnorm if z for rstudio which means left of the test statistic
* CAN also do: qt(0.95, df=n-1) which tells us the value with 95% to the left
* where 0.95 is 1-alpha which is the cutoff value and when we compute TS, we can see if it’s too big or not. If TS is bigger in magnitude than this special t value, then our data is weird or the old people are wrong, so we reject the null
* p-value is better to interpret on a spectrum

step 4.
* draw conclusion statistically and in context. State your conclusion in words 

STA 570 Sept 30 Thurs
Review
0. prelim
1. formulate hyp H0 vs H1 (for now assume 2 sided H1:mu neq mu0)
2. TS: (xbar-mu0)/(s/sqrtn)
3. to determine how weird the TS would be if H0 was true
    1. Can compute p-value
        1. where the number line represents all values that TS could be
        2. p-value is the probability of observing a TS at least as extreme as ours
        3. =2*pt(-TS,df=n-1) because we want both sides shaded (default is left)
            1. lower.tail=FALSE (right) which is 1-left
        4. p-value lets you see the spectrum and say like “0.00001 is rare” vs “0.001” and both are small but one is more rare
        5. for publications use p-value
    2. find a critical t value to compare the TS to (aka t* or t special)
        1. using the qt function
        2. alpha values on the edges with area alpha/2
        3. qt(alpha/2,df=n-1)
4. Measure weirdness: compare p-value to alpha or TS to t*
    1. if p-value < alpha, then we saw something weird (maybe weird data) or the old people were wrong
    2. if TS is more extreme than t*, then same conclusion as above |TS|>t*
5. Report reject or fail to reject H0 and what does this mean?

if CI=(Lower,Upper)
if mu0 is not in (lower, upper), then reject H0 or else we fail to reject H0

To choose alpha,
alpha = probability of rejecting H0 incorrectly or inappropriately = P(reject H0 | H0 is true)

beta is failing to reject H0 given that H0 is actually false. and beta is a function of H1

power(H1) = 1-beta = probability that we reject H0 when its false
function of sample size, alpha, sigma, delta=mu0-mu1
power goes up…
increases n
decreases beta and increases alpha increases power
decreases sigma
increases delta ( 2 mus difference/distance)



