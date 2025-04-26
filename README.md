# application-week-7-p0-solved
**TO GET THIS SOLUTION VISIT:** [Application Week 7 P0 Solved](https://www.ankitcodinghub.com/product/application-p0-solved-7/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;124732&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;Application Week 7 P0 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
Regression Estimation and

Inferences

Application of Matlab for Finance

Week 7

Today’s Class

I Ordinary Least Squares (OLS)https://.com

I Rolling Windows Estimation

I Maximum Likelihood Estimator (MLE)

Add

Basic Linear Regression: OLS

Y = X

I Y : T × 1 vector of dependent variables

I X: T × M matrix of regressors (or [1,X] regression with constant)

I Coefficient:https://.comβˆ = (X0X)−1X0Yi.e.,βˆ → min(Y − Xβ)0(Y − Xβ)

I Residual: Xβˆ

I Mean squared error (MSE)/variance of residual: s2 M

I Goodness-of-fit against the benchmark: historical average (Add Y¯)

R

Sum Squares of ResidualYi

= 1 − , Sum Squares of Total T

OLS Regression Code

I b = regress(y,X) estimates the M-by-1 β coefficient estimations of regression y = Xβ and stored in output variable b.

I [b,bint,r,rint,stats] = regress(y,X):

https://.comI b: M-by-1 matrix of the estimations of β

I bint: M-by-2 matrix of the 95% confidence intervals for the coefficient estimates

I r: T-by-1 matrix of the residual

Add I rint: T-by-2 matrix of intervals that can be used to diagnose outliers (if zero is not inside).

I stats: 1-by-4 vector contains the R2 statistic, the F statistic and its p-value, and the estimate of the error variance (MSE).

Exercise 1: Basic Linear Regression

I Estimate the coefficients of the Fama-French Three-Factor model ri

SMB + βiv HML

I rhttps://.comi is the excess return of portfolio i

I rM is the excess return of the market portfolio I

SMB is the size factor

I HML is the value factorAdd

I rM, SMB, HML are stored in sheet Factors inside excel file FF_Data.xlsx.

I Individual portfolio returns are stored in the IndusPort worksheet. Exercise 1: Fama French Model

1 %% Estimate the model on S1, V1

2 % alternative code of reading from excel file

3 [ff_fact, ff_txt]= xlsread(‘FF_Data.xlsx’,’Factors’); 4 [ff_port, ff_port_txt]= xlsread(‘FF_Data.xlsx’,’IndusPort’); 5

6 % Assign X: Mkt−RF, SMB, HML (last col as rf) 9 % https://.comAssign y: Excess returns

7 x = ff_fact(:,1:3); 8 rf = ff_fact(:,4);

10 y = ff_port− rf;

11

12 % Regress with loop for each asset: the coefficients for each asset are 13 % stored in each row of beta

14 [T,K] = size(y); 15 for i = 1: K 16 beta(i,:) = regress(y(:,i),x);

17 endAdd

18 19 % perform the same regression: read beta estimations and the statistics 20 % of the model 21 for i = 1: K 22

[beta(i,:),¬,¬,¬,stats(i,:)] = regress(y(:,i),x); 23 end

Linear Model Regression

res = fitlm(X,y,modelspec)

I res: the LinearModel Object for the responses y to be fit to data matrix

X;

I modelspec: model specification for the linear model with ’constant’, ’linear’, ’interactions’, ’quadratic’.

I Refer relevant items in an objective variable, use the period signhttps://.com

.

I res.Coefficients.Estimate returns the beta coefficient I res.Coefficients.pValue returns the significance of beta Add estimation

I The fitlm function assumes a constant term, to remove it: I Original model y1 + x1 + x2 + x3 I terms = ‘1’

I res = removeTerms(res,terms) I New

model yx1 + x2 + x3 Exercise 1: Fama-French Model

2 y_cnsmr = y(:,1);https://.com

1 %% Regression with lmfit with consumer sector as example 3 res = fitlm(x,y_cnsmr,’linear’) 4 terms = ‘1’ 5 res = removeTerms(res,terms) 6 beta_full = res.Coefficients.Estimate

Add

Rolling and Recursive Regressions

Y

I Time-varying parameters

https://.comYt

I Timely adjusted coefficient shall reflect more updated information; I If coefficient change gradually, then similar coefficient in adjacent time periods (seasonal effect)Add I The rolling estimates is a combination of true coefficients and sampling errors

I True coefficient is trending: estimates display trend and noise

I True coefficient is constant: estimates display random fluctuation and noise

Rolling and Recursive Regressions

I For a given window width τ, using the τ observations (t = 1,…,τ) for estimation

I Advance one observation at a time (t = 2,…,τ + 1) , repeat the estimation

I Plot the estimated coefficient against time to visualize the changeshttps://.com

I For a sample of observations k, it shall be k − τ + 1 estimates of β

Exercises 2Add

I For the same portfolios in the previous exercise, compute rolling βs using 60 consecutive observations

I Do the coefficient for market exposure appear constant?

Exercise 2: Rolling Estimation

Assignment Project Exam

Help1 %% Rolling Regressions for 1 asset

2 % Read Data Data

3 dd = ff_txt(2:end,1);

4 ddnum = datenum(dd,’dd/mm/yyyy’);

5

6 % Read the full sample estimation of beta for Mkt factor

7

8 % Define the Window

9 tau = 60; 10 % Loop from 60 to the end

11 for t=61:T 12 x_roll = x(t−tau:t,:); 13 y_roll = y_cnsmr(t−tau:t); 14 beta_roll(t,:)= regress(y_roll,x_roll); 15 end 16

18 plotdd = ddnum(tau+1:end,1);Add

17 % only plot the exposure to the market risk:

19 plotb_full = beta_full(1)*ones(length(plotdd),1);

20 plotb_roll = beta_roll(tau+1:end,1);

21 % Plot the data

22 plot(plotdd, plotb_full, plotdd, plotb_roll);

23 datetick(‘x’);

24 xlim([plotdd(1), plotdd(end)]);

26 legend(‘Constant eta’,’Rolling eta’,’Location’,’NorthWest’);

Estimated Beta

https://.com Add

Maximum Likelihood

I Maximum likelihood is a popular method to estimate parameters in econometric models. In many cases, closed form estimators are not

available and so non-linear optimizers are required.

I Suppose X = (x1,x2,…,xn) are the samples taken from a random variable X with probability distribution function (pdf) fn(xn;θ), where θ = [µ,σ]0.

I For example:https://.comX N(µ,σ2) : f I The joint density function of the sample is, by independence, equal to the product of the marginal densities, which is also known as the likelihood function

with respect to the parameter set θ, Add n

L(θ;X) = Yfi(xi;θ) = f1(x1;θ)f2(x2;θ.)..fn(xn;θ) i=1

I The Maximum Likelihood Estimator (MLE) is the parameter set θˆ that maximizes the likelihood function L(θ;X) L

Log Maximum Likelihood

I It is often rather difficult to directly maximise the L(θ;X). It is much easier to maximise the log-likelihood function since ln(.) is

a

monotonic function that maximising L(θ;X) is equivalent to maximising lnL(θ;X)

L(θ;X) → max ⇐⇒ lnL(θ;X) → max I The Log-

likelihood function

https://.comn

log L(θ;X) = Xlnfi(xi;θ) i=1 I The crucial is to have

explicit pdf function to maximize. MATLAB contains various options for different distributionAdd n

√

2π 2σ

i=1 n

√1 − n lnσ − 1 X(X − µ)2

= n ln

2π 2σ2

i=1 Log Maximum Likelihood: Exercises

I Use help to find the mle function in MATLAB

I Use the mle function to estimate the mean and variance on the monthly FF consumer sector returns.https://.com

I Compare the estimated value with the mean and variance of the sample

I Note: theAdd mle function only allows one time serie (vector observations) at a time.

Exercise 3: MLE

1 % Maximum Likelihood:

2 % calculate mle of mean and variance of consumer sector excess return

3 parm_est =

4

5

6

7

8

9

10

11

mle(ret_cnsmer) ret_cnsmer = y(:,1);

% Calculate the sample statistics parm_data = [mean(ret_cnsmer) std(ret_cnsmer)];

% Display disp(‘Consumption Industry Returns’) disp(‘MLE estimates of mu, sigma’) disp(parm_est) disp(‘sample estimates of mu, sigma’) disp(parm_data)

Add

Extra: AR, MA and ARMA code

I Autoregressive Model: AR(p)

Yt t

p

i=1

I Moving-Average Model: MA(q)

https://.comq

Yti i=1

I ARMA(p,q) Model (setAdd µ = 0)

p q

Yt i

i=1 i=1

I If Yt is integrated, use the ARIMA(p,D,q) model, where D is the

number of difference order Extra: AR, MA and ARMA code I Code in matlab: arima(p,D,q)

I AR(1): arima(1,0,0)

I MA(2): arima(0,0,2)

I ARMA(2,3): arima(2,0,3)

I The presence of AR process violates the assumption of stationary for the linear regression analysis (to apply the central limit theorem)https://.com

I To test whether the underlying time series is stationary, the Augmented Dicky-Fuller test adftest is applied to test the presence of unit-root in the underlying return sequence.

I res = adftest(y)Add

I res = 0: fail to reject the null hypothesis of a unit root against the autoregressive alternative.

I res = 1: reject the null hypothesis and conclude that the y is stationary.
