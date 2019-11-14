---
title: 'Models and Simulation'
subtitle: 'A New Model for Security Cooperation'
date: 2019-11-13 00:00:00
featured_image: '/images/nsa_tank.jpg'
---

![](/images/nsa_tank.jpg)

Zachary Hadley, PhD Candidate 

AGS Paris 

## Panel Event Count (PEC) Model
In order to maintain consistency and clarity throughout the following section,
common statistical terms are used to describe the research design, maximum likelihood
estimation (MLE), and Markov chain Monte Carlo (MCMC) simulation. Outcome
variable (i.e., dependent variable) describes the observed values that are a product of
the social system. Let Y stand for a $n × 1$ column vector of all observed outcomes
from the social system. Explanatory variables are measurements of the social system.
They are the inputs into the statistical “black box.” Let n be the number of total
observations and, k, the total number of explanatory variables. X is defined as a
n × k matrix where each row, $Xi = (xi1, xi2, ..., xik)$, represents the k observed values
for the ith observation. Summary statistics describe features of the data and point
estimates are used to learn about the data through inference. These raw estimates are
converted into predicted values via simulation to draw substantive conclusions about
state rationales (King, Tomz, & Wittenberg, 2000).

## Empirical domain
The social system is defined spatio-temporally between 1999 and 2016, centered
on peace operations within Africa. The social system includes: (i) UN-led missions
authorized by the UN and under UN command and control; (ii) UN-authorized missions
conducted by other regional organizations; and (iii) non-UN missions that were neither
authorized nor conducted by the UN but conducted by regional organizations.

## Measurement of Variables
The outcome variable, TCC/PCC contribution, is operationalized as an event
count, where (Yi = 1, ..., n), if a state contributes peacekeepers to a given number of
peacekeeping operations, and (Yi = 0), if otherwise. The variable indexes observations
as the total number of peacekeeping operations supported during a calendar-year. This
is adjudicated by monthly official UN reports. Contributions are defined as troop and
civilian police contributions. UN Military Observers and Experts-on-Mission are not
considered active contributors to peacekeeping missions due to their small numbers
and restrictive legal authorities.5 These observations are purged from the event count.
The following conditions are assumed generally true: (i) state decisions regarding
commitments are independent of decisions regarding actual force contributions; (ii)
member states assess other states contributions relative to their own in determining
total contributions; and (iii) once member states commit to a peacekeeping operation,
they tend stay committed over the duration of an operation.

Publicly available indices are used as measurements for the explanatory variables.6 The explanatory variables are anchored to theory frequently encountered
within peacekeeping literature. In order to assess the marginal effect of regional
integration on TCC/PCC contribution, I control for explanatory variables frequently encountered in the literature. Although parsimony is a desirable property
for any model, the selection of covariates is theory-driven to control for potential
confounders. Experts-on-Mission and UN Military Observers (UNMOG) traditionally serve as observers
for the UN and serve as the "eyes and ears” of the Security Council. They do not fill roles and
responsibilities in direct support of their respective host nations.
6See Appendix B for summary statistics and methodologies.


Regional integration: The primary variable of interest is defined as an
economic rationale. I hypothesized that African states which demonstrate stronger
economic ties and trade integration will be more likely to support UN peacekeeping
operations than states which exhibit greater degrees of economic closure. Regional
integration includes a “spaghetti bowl” of potential dimensions including: (i) trade
agreements (RTAs); (ii) security partnerships and alliances, (iii) regional infrastructure
projects, (iv) financial integration, and (v) the free movement of people across borders.
Five core indicators are selected to build a composite measurement of integration
(World Bank, 2013). Due to limited observational data prior to 2013, I approximate
the African Regional Integration Index (ARII) by including the following variables:
(i) the Logistics Performance Index (LPI) to measure regional infrastructure; (ii) the
World Bank Trading-across-Borders index focused on institutional barriers to trade;
(iii) intra-regional imports as a percentage of total gross domestic product (GDP); (iv)
exports as a percentage of total GDP; and (v) foreign direct investment as a percentage
of total GDP. The five interval-level indicators are normalized using min-max scaling.
The indicators are assessed separately to extract greater insights from the data.
Militarization: This is considered a security rationale, which measures
the weight and importance of a state’s security sector relative to civil society as a
whole (BICC-GMI, 2017). High levels of militarization may indicate a politically
powerful security sector that leverages influence over foreign policy outcomes. The
militarization variable is a non-negative interval measurement. The score is computed
as the average of three indicators from the Bonn International Center for Conversion,
Global Militarization Index (BICC-GMI).

National_capability: National material capabilities is considered as a security rationale. It complements the militarization variable by providing a measure
of military strength relative to other African states. Of note, the Composite Index of

National Capability (CINC v. 5.0) provides observational data up to the year 2012. Multiple imputation (MI) is used to deal with missing observations from 2013-2016. The score is calculated as the average for a given state on each of the six indicators, which are equally weighted. The result is a percentage for each African state ranked
relative to all other states on an interval scale.

Governance: This variable is used to measure the political rationale for peacekeeping by assessing the relationship between government performance and foreign
policy outcomes. The Ibrahim Index for African Governance (IIAG) is calculated as a
composite score of four dimensions available per country-year from 2000 to 2016. MI
is used to impute missing observations for missing year, ti = 1999. The result is an
interval level measurement, which is normalized using min-max scaling.

Political_accountability: This variable will assess the political rationale
through a measure of political accountability. If peacekeeping is contentious, political
will is required to martial bureaucratic and public support for an intervention. Yet
because political will is difficult to measure, I assume that political accountability
provides a useful proxy. The variable is operationalized as an interval measure using
the Varieties of Democracy Accountability Index (V-Dem), which includes three subindicators: (i) the presence of credible elections; (ii) institutional checks and balances;
and (iii) the influence of civil society and media activity.

Polity: This variable is a measure of the normative rationale. The measurement is subset as two regime types: (i) a democratic polity, democratic_polity,
and (ii) autocratic polity, autocratic_polity, to capture the unique features of each
regime type. The measure is used to assess the propensity for peacekeeping through a
set of shared normative values. The polity score is derived from a set of four indicators
that are compiled as an interval measurement.

Regional_leadership: This variable will measure the institutional rationale through a measurement of the relationship between peacekeeping contributions and
state participation in regional institutions including: (i) UN Security Council nonpermanent members, (ii) African Union chairmanships, and (iii) AU Peace and Security
Council member states. The variable is an interval measurement that indexes the
total number of regional institutions that an African state participates in within a
given year.

Foreign_military_post: This variable will assess the role of bilateral security
partnerships with NATO and European Union allies. This measure is operationalized
by assessing the presence of enduring foreign military posts present within African
states. Bilateral partner nations include: US, UK, Belgium, Netherlands, Canada,
Germany, Italy, and France. The variable is dummy-coded (xij = 1) if an African
state has a foreign military post and (xij = 0), if otherwise.

# Generalized Event Count (GEC) Model
Initially, I specified a generalized linear model (GLM) with a Bernoulli distribution and a log link function. I aggregated a state’s propensity to support peacekeeping
as a simple binary outcome where, (Yi = 1), if a state contributes peacekeepers in a
given year and (Yi = 0), if otherwise. Although a valid approach, additional spatiotemporal dynamics became apparent as I compiled the dataset. For example, a state’s
level of contributions in a given year appears influenced by its contributions in the
previous year. The number of supported missions were also conditional on intervention
effects (e.g., regime collapse, civil war, or economic shocks). As a result, I re-specified
the model using event counts to derive greater information about the underlying
data generating process. The outcome variable, Yi
, indexes the number of observed
peacekeeping contribution per calendar year. The explanatory variables, Xi
, measure

continuous processes such as the level of regional integration, military capacity, and
overall governance as well as a dichotomous variable to assess the presence of foreign
military posts. Because the processes that produce these variables are unobservable, I
make the assumption that discrete event counts provide insights into the unobserved
data generating processes.
The Poisson model requires two main assumptions. An independence assumption holds that the probability of an event occurring at time t is independent of all
previous history.7 The principle of homogeneity holds that the rate of event occurrence
λt
, is constant over period t. If these two assumptions hold then the data can be
modeled using a standard Poisson distribution with mean, $$E[Yt
] ≡ λt
.
Yt ∼ fp(yt
|λt) = e
λtλ
yt
t
yt
!$$

(1)
However, these assumptions are tenuous for panel data. First, I assume that a
state is more likely to continue supporting a UN mission at time, t, after an initial
intervention has occurred – the independence assumption does not hold. Time lags
are incorporated into the model to account for serial correlation. Likewise, the
assumption of homogeneity is unlikely. In the previous section I assumed that the
explanatory variables vary over time, resulting in a heterogeneous probability of
event occurrence (King, 1989). The Poisson distribution requires that the decision to
contribute peacekeepers has an equal probability of occurrence and is independent
where, σ
2 = 1.
As a result, the Poisson model may be too restrictive for the data. I relax both
assumptions by re-specifying the variance of Yi given Xi as
7The Markov independence assumption states that the probability of an event occurring at
time t, is only dependent upon the previous observation, t − 1.
24
V (Yi) = λiσ
2
. (2)
The variance may take any value greater than zero. I derive a probability
distribution with parameters λi and σ
2 known as the Generalized Event Count (GEC)
model (King, 1989).8 Three potential dispersions are possible: (i) 0 < σ2 < 1, where
the variance is under-dispersed relative to mean, λi
; (ii) σ
2 = 1, where the variance
equals the mean; and (iii) σ
2 > 1, where the variance is over-dispersed relative to the
mean. Without the need for additional assumptions, this single probability distribution
accounts for heterogeneity, independence, and contagion.9
I am not required to set σ
2
at an arbitrary fixed value.
Maximum likelihood is selected over Bayesian and Neyman-Pearson alternatives.
Although Bayesian inference is capable of generating many quantities of interest,
a flat prior and lack of justification limits its usefulness here. Neyman-Pearson
hypothesis testing requires stronger assumptions regarding the distribution of the
data than are required of ML. I considered its limitations as a reasonable trade-off.
Recognizing the small-n bias of likelihood, the number of observations (n = 864) will
benefit from asymptotic qualities of MLE including consistent and efficient estimators.
As a substitute for inverse probability, likelihood provides a measure of relative
uncertainty. It is the probability of the hypothetical model given the observed
data, P(model|data) ≡ P(θ|y). We know that by the law of large numbers and
the central limit theorem that the information will be asymptotically normal and a
consistent estimator for the variance. With simulation, we can calculate the uncertainty
surrounding the estimators (King, 1989).
8See Appendix D for a full derivation of the GEC model.
9Contagion occurs when the expected number of events at one time is dependent on the
realized number of events from a previous observation (King, 1989, pg. 768).
25
Non-Parametric Pre-Processing
The following section details the non-parameric methods used to prepare the
data for regression analysis and simulations. The dataset is pre-processed using
multiple imputation to correct imbalances and diagnostics test are performed to assess
underlying panel effects.
Missing Data
A total of 804 cell values (8.5 percent) are missing from a dataset composed
of 9,504 total values. Multiple imputation (MI) is used to impute m values for each
missing observation in the data matrix and create m completed data sets. For my
purposes, m = 5. Across these completed data sets, the observed values remain
unchanged, but the missing cells are filled in with a distribution of imputations that
reflect uncertainty about the missing data (Honaker, King, & Blackwell, 2011). MI
requires that we assume the missing data is missing at random (MAR) and are not the
result of underlying data generating process. An expectation-maximization algorithm
which incorporates bootstrapping is used to draw from a posterior multivariate normal
distribution (Honaker & King, 2010). All variables in the imputation model are
also present in the regression analysis except for lpi_score due to the presence of
significant collinearity that prohibits convergence.
The imputation model accounts for time effects with the inclusion of a squared
polynomial integer. Lags and leads are included on the outcome variable, TCC/PCC
contribution, since I assume that current values depend on previous values. Because
the outcome is an event count, I take its square root. The model includes a column
variable which indicates time series by year and a cross-section variable indicated by
cow_code. A ridge prior of 0.01 is multiplied by the total number of rows to reduce the
26
Table 2: Comparison of pre and post-imputation datasets.
Pre-imputation Post-imputation
Variable N Mean Median N Mean Median
autoc_polity 818 2.16 1.00 864 2.17 1.00
democ_polity 818 3.69 3.00 864 3.65 3.00
exports_%gdp 810 0.22 0.19 864 0.23 0.19
fdi_%gdp 847 0.11 0.09 864 0.11 0.09
foreign_mil_post 864 0.23 0.00 864 0.23 0.00
governance 816 0.40 0.41 864 0.40 0.40
imports_%gdp 810 0.15 0.13 864 0.15 0.13
militarization 796 0.36 0.35 864 0.36 0.35
national_capability 659 0.14 0.06 864 0.14 0.06
political_accountability 864 0.61 0.62 864 0.61 0.62
trade_across_borders 548 0.53 0.58 864 0.46 0.53
regional_leadership 864 0.37 0.00 864 0.37 0.00
covariances without affecting the means and variances. A comparison of the original
dataset and an imputed dataset is provided in Table 2.
Regressions are run on each imputed dataset. The point estimates and standard
errors are pooled using Rubin’s rule to capture the estimation uncertainty surrounding
the imputed values (Rubin, 1987). Let us define q¯ as the average of the m separate
estimates, qj (j = 1, ..., m) :
q¯ =
1
m
Xm
j=1
qj
. (3)
The variance of the point estimates is calculated as the average of the estimated
variances from within each completed data set plus the sample variance in the point
estimates across all data sets. The standard error of the point estimates is the square
root of:
27
Table 3: Summary of GEC model diagnostics.
Statistic df Pr(>|t|) Method Result
73.35 < 2.2e-16 Durbin-Wu-Hausman Fixed-effect model
282.23 1 < 2.2e-16 Breusch-Pagan (LM) Time-fixed effects
21.65 17 < 1.2e-54 F-test Individual effects
2212.00 1 < 2.2e-16 Breusch-Pagan (LM) Panel effects
-2.52 0.012 Pesaran CD Cross-sectional dependence
401.30 18 < 2.2e-16 Breusch-Godfrey Serial correlation
4.30 1 0.038 Likelihood Ratio Test Poisson (FE)
SE(q)
2 =
1
m
Xm
j=1
SE(qj )
2 + S
2
q

1 +
1
m

. (4)
The standard errors reflect the uncertainty surrounding the imputed values
and the dataset is balanced without a need for ad-hoc corrections such as list-wise
deletion or arbitrary best guesses.
Model Fit and Diagnostics
Standard diagnostic tests are used to evaluate the data for fixed and random
effects, cross-sectional dependence, serial correlation, and heteroskedasticity. I begin
by assessing whether a fixed-effect or random-effect model is more appropriate for the
data using a Hausman test. Fixed-effect models control for unobserved, time-invariant
characteristics and focus on explanatory variables that vary with time. These may
include such as characteristics as religion, language, or cultural values that influence the
observed Yi outcomes. Alternatively, a random-effect model assumes that the observed
variation across individual states is random and uncorrelated with the explanatory
variables. The results of the Hausman test suggest that a fixed-effect model is more
appropriate for the data.
Time effects are used to control for unexpected variation and interventions
28
(e.g., polity collapse, war, or epidemics). The results from the Lagrange Multiplier
(Breusch-Pagan) test indicate the presence of time-fixed effects, which will be controlled
for in the model. Next, an F-test is used to assess the inclusion of an individual-fixed
effect. The results suggest the presence of both time and individual effects. As a
result, a “two-ways” effect is incorporated into the model. The Breusch-Pagan (LM)
is used to test if a pooled OLS regression can be used in lieu of an event count model.
Because the variance across observations is greater than zero, a panel effect may exist.
As the dataset consists of t = 18, the results of a Pesaran CD test indicate the
presence of cross-sectional dependency. Tests for heteroskedasticity include the use of
a residuals vs. fitted values plot for the Poisson (FE) model is shown in Appendix I.
Overall, heteroskedasticity appears minimal with the GLM smoothing line consistent
near zero on the horizontal x-axis. It is possible that the excess number of zero values
affects the overall balance. However, overall the dispersion appears relatively balanced.
Serial correlation is assessed with a Breusch-Godfrey test. The results reinforce
the assumption that serial correlation is present in the data. The presence of clustered
observations, as a result of grouped state observations, suggests significant correlations.
Because the fixed-effects model alone cannot correct within-cluster correlation, clusterrobust standard errors are applied to address potential heteroskedasticity and serial
correlation to increase model robustness (Arellano, 1987).
Finally, I considered the use of zero-inflated models due to the large number of
observed zero counts. From a theoretical perspective, I lack the necessary justification
for their use. Proceeding from first principles, zero-inflated models posit that the
excess zeros are the result of two separate data generating processes. Non-random
structural zeros are the result of latent unobserved variables. These are considered
separate from random zeros – a product of the social system. As such, zero-inflated
models treat excess zeros separate from random zeros. A priori, I assume that African
29
states do not have structural characteristics that ensure they will never contribute
to peacekeeping operations. Observed zero counts are the result of underlying state
rationales. As a result, I select a fixed-effect model to control for time-invariant
characteristics of individual African states and include cluster-robust standard errors
to control for heteroskedasticity and serial correlation.

## GEC Model Results
Table 4 provides a comparison of Poisson and negative binomial models. The
results are pooled from the imputed datasets (m = 5) to reflect the uncertainty
surrounding the estimated values.10
Table 4: Comparison of regression models, m = 5.
Poisson (FE) Poisson (CL) NB1 (FE)
governance 4.27 (0.72)∗∗∗ 4.27 (0.91)∗∗∗ 5.26 (1.00)∗∗∗
militarization −2.16 (0.74)∗∗ −2.16 (1.25) −1.96 (0.59)∗∗
pol_accountability 0.52 (0.38) 0.52 (0.48)
national_capability −0.25 (1.02) −0.25 (1.25)
autoc_polity 0.00 (0.05) 0.00 (0.05) 0.00 (0.05)
democ_polity −0.06 (0.03) −0.06 (0.03) −0.04 (0.03)
trade_across_borders 0.56 (0.15)∗∗∗ 0.56 (0.23)∗
0.59 (0.17)∗∗
imports_%gdp 2.11 (1.06)∗
2.11 (1.26) 2.18 (1.05)
exports_%gdp −0.04 (0.60) −0.04 (0.65) 0.10 (0.43)
fdi_%gdp −0.36 (0.61) −0.36 (0.82) −0.71 (0.75)
regional_leadership 0.14 (0.04)∗∗ 0.14 (0.04)∗∗ 0.13 (0.04)∗
foreign_mil_post 0.14 (0.35) 0.14 (0.24) 0.29 (0.35)
intercept 15.41 (223.66)
Log-Likelihood −1034.97 −1034.97 −1035.29
Num. obs 864 864 774
∗∗∗p < 0.001,
∗∗p < 0.01,
∗p < 0.05; FE = fixed effects, CL = cluster-robust, NB1 = negative binomial
The results suggest that the statistical significance of governance,
10See Appendix C for individual regression results for each imputed dataset.
30
trade_across_borders, and regional_leadership are consistent across the models.
Variables including militarization, imports_gdp, and democratic_polity
may also be of substantive interest. Variables political_accountability and
national_capability are dropped from the NB1 (FE) model. This is due to lack
of concavity in the optimization algorithm. Different methods of optimization were
attempted including BFGS and Newton-Raphson, as well as Box-Cox transformations
on the variables. It is possible that a numerical solution does not exist for the
data. However, dropping the two variables allowed for convergence on the remaining
variables. The result is reflected by n = 774.
Earlier assumptions regarding the fixed-effect Poisson model appear justified.11
The results of a likelihood ratio test suggests that a conditional Poisson (FE) with
robust-standard errors provides a marginally better fit than a NB1 (FE) model. A
fixed-effect negative binomial model does not control for all stable covariates, which
often leading to inconsistent estimates (Allison & Waterman, 2002). Due to the
number of dropped observations and a lack of substantial over-dispersion, I select a
Poisson (FE) with cluster-robust standard errors for simulation.
Interpreting the results Poisson model coefficients is difficult without the use
of simulation. Covariates in non-linear models depend upon each other. However,
a linear approximation is possible using an exponentiated coefficient. Interpreted
broadly, given a unit change in xj
,
yˆ ≈ yˆ(e
βj
). (5)
Thus the effect of increasing governance by one unit is to increase
ln(yˆ) by yˆ (exp4.27) ≈ 11 events – clearly nonsense. The effect of increasing
11For a comparison with a Poisson random-effects model see Appendix C.
31
trade_across_borders by one unit is ≈ 1.5 events and regional_leadership is
≈ 0.4 events. However, the key point is that these three variables appear to have an
positive effect on the rate of peacekeeping contributions. We can cautiously associate
higher levels of governance, trade_across_borders, and regional_leadership
with a greater probability of peacekeeping contributions in a given year.
GEC Model Assessment
Revisiting the hypotheses from chapter two, a number of interesting observations
emerge. The first hypothesis, H1, posited that states with higher levels of regional
integration are associated with greater support for peacekeeping. However, as a
composite measure of economic indicators, regional_integration is too general to
provide substantial information about the underlying data generating process. The
results suggest that greater nuance is required to assess economic rationales. Trade
integration operationalized as trade_across_borders provides a useful snapshot of
a state’s overall level of trade openness. Excluding regional trade agreements (RTAs),
states with lower costs on imports and exports, documentary and border compliance,
and transportation infrastructure provide greater evidence of market openness than
low tariffs alone. Market openness leads to increased economic exposure, which may
inform the priorities of the state with respect to security. If trade integration is
conditional on regional stability, then the economic rationale from a trade perspective
provides insight into peacekeeping contributions. Traditional economic indicators that
measure the overall health of a domestic economy were not significant. While a trend
may exist, large standard errors make interpretation of the gross domestic product
(GDP) measures problematic.
The second hypothesis, H2, focused on the political rationale, which was
operationalized through measures of governance and political_accountability.
32
The results suggest a relationship between good governance and peacekeeping that is
robust across models. The provision of public goods, services, and policy is indicative
of a healthy civil society and a functional government. Of note, safety and the
rule of law as sub-indicators of the IIAG index measure a government’s ability to
ensure its own national security. I assume that functional bureaucracies are more
likely to produce coherent foreign policy. Proceeding further, such states which view
regional stability as fundamental to national security may be more likely to provide
peacekeepers. Where the two conditions are met, I suspect a greater likelihood for
peacekeeping. However, anomalies exist. For example, Nigeria scores low on the IIAG
index despite being a reliable partner and regional power. Botswana, which scores
consistently high on good governance, has supported few UN peacekeeping missions.
Surprisingly, Political_accountability as a measure of horizontal and vertical political accountability does not independently provide support for the model.
Governments with limited vertical accountability and greater autonomy may face fewer
political costs for providing peacekeepers. The lack of horizontal accountability may
streamline foreign policy by centralizing the decision-making apparatus and limiting
bureaucratic constraints. However, I suspect a relationship exists between good governance and political accountability. I test for an interaction effect between governance
and political_accountability.
12 The results suggest that a significant interaction
effect exists between the two variables. If a state exhibits both good governance and
political accountability, then there is a positive relationship with contributions.
The security rationale was tested by the third hypothesis, H3, and partially
holds with respect to militarization. The specification of cluster-robust standard
errors to account for autocorrelation and heteroskedasticity greatly increases the
variance. However, the results are no less interesting. It is important to consider
12See Appendix C for regression results within inclusion of interaction term.
33
that high levels of militarization do not guarantee the regional projection of state
power. States with high levels of militarization may focus their security apparatus
domestically to ensure regime stability. The top five African states with the highest
BICC-GMI values in 2014 included Morocco, Egypt, Angola, Eritrea, and Mauritania.
Of those, only Morocco and Egypt are reliable UN contributors. I test the observed
values for high leverage and large residuals.13 Egypt, Guinea, and Mauritius contain a
significant number of potential outliers – greater than half of all observations. The
states are dropped and I rerun the Poisson fixed-effect regression model. Although the
variance increased with respect to militarization, the coefficient remains statistically
significant. The inclusion of cluster-robust standard errors provides similar results to
Table 4.
The second security variable national_capability measures “hard power” national assets. I tested the assumption that states with significant military capabilities
will be more likely to provide contributions. For example, regional powers including
Egypt, South Africa, and Nigeria have demonstrated consistent support for peacekeeping during the past two decades. Yet across the observations, national_capability
as a measure of the security rationale is inconclusive. Additionally, there appears to
be no significant differences among African states in terms of basing arrangements
with EU and NATO partners. However, this result does not negate the possibility
for domestic benefits from foreign military basing within Africa. It merely implies
that security rationales operationalized through these two variables are not a reliable
indicator for potential contributions.
The fourth hypothesis, H4, focused on the institutional rationale and was
operationalized through a measurement of domestic influence within decision-making
13Using Cook’s distances, a total of eighty-three individual observations may contain high
leverage or large residuals.
34
organs at the UN, AU, and AU-PSC. Across the models, regional_leadership
retains statistical significance. Intuitively, this makes sense. We should expect
domestic leaders to have a vested interest in seeing the successful implementation of
their domestic policy objectives at the regional level. Access to privileged information,
resources, and policy formation provide clear incentives to support regional institutions.
Following the logic of the two-level games, decision-makers may be exposed to greater
international pressure during their leadership tenure in regional institutions. The case
studies will assess this dynamic over time as states rotate through leadership billets.
For now, the results suggest support for the fourth hypothesis.
The fifth hypothesis, H5, explored the impact of normative rationales on peacekeeping. The argument states that democratic countries are more willing to support
peacekeeping because a shared set of normative values. These might include support
for international institutions, the promotion of democratic values, and a traditional
commitment to peacebuilding and conflict-prevention. The measure was operationalized through an assessment of regime polities. It was assumed that democratic and
autocratic polities have specific traits that inform their preferences towards military
intervention. As a result, two variables were used to assess the potential for both
unidirectional and bidirectional trends towards contributions. The results provide no
clear evidence of a trend by regime type. Although normative rationales may inform
individual state contributions, at an aggregate level the hypothesis is not supported
by a measure of regime types.
Simulation and Quantities of Interest
Markov chain Monte Carlo (MCMC) simulation is used to calculate uncertainty
surrounding the coefficients and variance. I derive quantities of interest that account for
35
Table 5: Summary of GEC model assessment.
Hypothesis Rationale Argument Model Support
H1 Economic Increased regional economic integration leads
to greater state support for peacekeeping.
Yes
H2 Political Good governance and/or political
accountability leads to greater state support
for peacekeeping.
Yes
H3 Security Robust military capacity and/or militarization
leads to greater state support for
peacekeeping.
No
H4 Institutional Leadership tenure in regional institutions leads
to greater state support for peacekeeping.
Yes
H5 Normative Democratic polities are more likely to support
peacekeeping than autocratic regimes.
No
both estimation uncertainty and fundamental uncertainty that arise from the stochastic
component of the GEC model. I begin by testing the Poisson model’s robustness by
throwing out the observed data and simulating 10, 000 random values (m = 10, 000)
to compare predicted outcomes against observed events. The results show that a given
African state with mean values across covariates will support, on average, three UN
missions per year with a 0.2 margin of error. The true population average is 2.4 events
per year. The probability of contributions increases by approximately 17 percent as
states approach the 98th percentile on each of the explanatory variables values. There
is a similar downward trend as states move lower on the percentile range.
In order to assess the marginal effect of trade_across_borders, I vary trade
integration over its range of values while holding all other covariates constant. Simulated expected values show that as trade integration increases, the probability that a
state contributes to peacekeeping operations also increases. I calculate the first differences for trade_across_borders to assess the rate of change. The results indicate a
0.975 increase – approximately one additional event – as trade integration varies from
the lowest to the highest predicted value, averaged across the population.
36
Figure 1: Expected number of PKO contributions across trade (m = 10, 000).
Additional simulations are run on governance and regional_leadership.
14
For governance, there is a first difference of five additional events with a standard
deviation of 2.65 as it varies across the range of predicted values. The first difference
for regional_leadership is approximately one additional event with a standard
deviation of 1.22. The results of the simulation suggest that increasing scores on good
governance provides the highest likelihood for peacekeeping contributions – more so
than trade integration or institutional leadership taken together or independently.
Surprisingly, the effects of regime type and military capability are inconclusive.
This may lead to the conclusion that political, economic, and institutional rationales
wield greater influence on peacekeeping contributions than security or normative
rationales. However, statistical significance alone cannot justify causal claims. I used
simulation to assess the uncertainty surrounding the parameter estimates and derived
predicted values and first differences to assess the marginal effect of regional trade
14See Appendix A for marginal effects plots for both variables.
37
integration. The simulation results demonstrated that the GEC model provides an
acceptable approximation for the underlying data generating process. The compiled
dataset and R code used for the analysis is made available for download.15
