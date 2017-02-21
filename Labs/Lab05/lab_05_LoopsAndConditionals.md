#Lab 05: Loops and Conditionals















<hr>

####Part II. Loops + conditionals + biology

A simple but very famous model of predator-prey dynamics is the "Lotka-Volterra" predator-prey model.  You can read all about it at [https://en.wikipedia.org/wiki/Lotka-Volterra_equations](https://en.wikipedia.org/wiki/Lotka-Volterra_equations) if you are curious.  In discrete time, this model can be represented as follows:

	n[t] <- n[t-1] + (r * n[t-1]) - (a * n[t-1] * p[t-1])
	p[t] <- p[t-1] + (k * a * n[t-1] * p[t-1]) - (m * p[t-1])

In this model, `n[t]` represents the abundance of prey at time `t`, and `p[t]` the abundance of predators at time `t`.  Prey increase in abundance due to exponential growth, represented by the term `(r * n[t-1])`, where `r` is the intrinsic growth rate.  Prey decrease due to consumption by predators, represented by the term `(a * n[t-1] * p[t-1])`, where `a` represents the "attack rate" of predators on prey.  Predators increase in abundance due to consumption of prey, represented by the term `(k * a * n[t-1] * p[t-1])`, where `k` is a conversion constant representing the conversion of consumed prey into biomass of predators.  Predators die at a constant mortality rate, represented by the term `(m * p[t-1])`, where `m` is the intrinsic mortality rate.

Write code that calculates abundances of predators and prey over time according to this model. 

First, set up parameter values.  Use the following: 


	totalGenerations <- 1000
	initPrey <- 100 	# initial prey abundance
	initPred <- 10		# initial predator abundance
	a <- 0.01 		# attack rate
	r <- 0.2 		# growth rate of prey
	m <- 0.05 		# mortality rate of predators
	k <- 0.1 		# conversion constant of prey into predators
	
Second, create a "time" vector, and make two additional vectors to store results, one for the values of `n` over time, and the other to store values of `p`.

Third, write a loop that implements the calculations.

Fourth, in this model it is possible that the predators may kill off all the prey.  Due to the discrete nature of how time is considered in this model (time proceeds in discrete jumps from one generation to the next), it is possible that the calculations as given can result in negative numbers.  So, add some `if` statements to your code to check for negative numbers each generation.  If, for example, a given value of prey abundance is negative, then that value should be set to be zero.
