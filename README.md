# Arrear Quanto CMS Algorithm

An arrear quanto constant-maturity-swap (CMS) is a swap that pays coupons in a different currency from the notional and in arrears. The underlying swap rate is computed from a forward starting CMS.

Assumes that, under the coupon payment currency (SEK) risk-neutral probability measure, the forward swap rate process corresponding to each swap rate fixing follows Geometric Brownian motion with drift.  Each forward swap rate process is then convexity adjusted, and is furthermore expressed under the notional currency (FRF) risk neutral-probability measure by means of a quanto adjustment.

Let the observation times  , correspond to consecutive quarterly resets, where   corresponds to the start date, and   corresponds to the maturity date.  Then the seller pays
  
at time  , for  ,  where  .  

At time  , where  , we consider a three year CMS, which begins at time   and has three payment times,  ,  where  .  Here the floating  side pays the SEKSTIBOR rate,
 
at time  , where  .  The fixed side pays a constant amount at time  , where  .   The swap rate at time  , which we denote by  , is the constant fixed payment amount that gives the CMS zero value at time  ; that is,
 
where   denotes the price at time   of a Swedish zero coupon bond maturing at time  .  

From the above, the holder receives
 
at time  , for  .

The value of our swap at time zero then equals
 
where
•	  is the price at time zero of a FRF zero coupon bond maturing at time  , 
•	  denotes the FRF risk-neutral probability measure, and
•	the swap notional is denominated in FRF.

Here we have assumed that the FRF short-term interest rate is deterministic.

We note that the common currency unit in Europe is now taken to be the EURO.  Furthermore, the exchange rate from the EURO to an associated currency (e.g., FRF) is fixed, so there is no foreign exchange risk.  Therefore, FP London uses a common curve, EURIBOR, for discounting; that is,   is replaced by the equivalent discount factor
 ,
which is the price at time zero of EURO denominated zero coupon bond with maturity of  .

Let   , for  , denote the forward swap rate at time   for a forward starting SEK CMS, which begins at time   and has payments at times   where  .  FP assumes that, under the SEK risk-neutral probability measure, the process   satisfies a stochastic differential equation (SDE) of the form
 
where 
•	  is standard Brownian motion, and
•	   is the volatility.
Recall that the swap pricing formula, 
 ,
requires the expected swap rate,
 ,						(A.1)
for  .   Since  , FP’s approach towards computing (A.1) is to convexity adjust the initial forward swap rate,  .  

To this end let 
 
be the price of a bond, with three year maturity, where
•	  is an annually paid coupon value, and
•	  is an annualized yield-to-maturity.
FP’s convexity adjusted rate is then given by
 ,

The yield to maturity of a bond is the internal rate of return on a bond held until maturity. In other words, it is the discount rate that will provide the investor with a present value V equal to the price of the bond. The yield to maturity does not account for the actual term structure of interest rates: https://finpricing.com/lib/FiZeroBond.html

We wish to express the process   under the FRF risk-neutral probability measure.  Let   denote the SEK short-term interest rate.  Assume that, under the SEK risk-neutral probability measure, the process   satisfies a SDE of the form
 
where   and   are deterministic, sufficiently regular functions.

Let   denote the exchange rate from one SEK monetary unit to FRF.  Furthermore assume that, under the FRF risk-neutral probability measure, the process   satisfies a SDE of the form
 
where 
•	  is the FRF short-term interest rate, which we assume to be deterministic,
•	  is the volatility, and
•	  is standard Brownian motion.
Then under the FRF risk-neutral probability measure, the process   satisfies the SDE
 
where
•	  is standard Brownian motion, and
•	  is the constant instantaneous correlation coefficient between   and  .

Observe that, under the SEK risk-neutral probability measure, the forward swap rate process,  , is driven by the same Brownian motion,  , as the short-term interest rate process,  .  Then, under the FRF risk-neutral probability measure, the process   satisfies the SDE
 .


