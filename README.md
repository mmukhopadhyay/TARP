# TARP

Here we compute RIS-RP and RIS-PCR for normal-linear model

## Usage

input: x : standardized taining design matrix in nXp format

input: y : training response, a n-vector

input: x_test : standardized test design matrix in nXp format

## Examples

	RISRP_res=RIS_PCR(x,y,x_test,alpha=0.95)
	y_hat=RIS_PCR(x,y,x_test,alpha=0.95)
	y_hat=RISRP_res[,1]     # predicted value
	lower_PI=RISRP_res[,2]  # lower 100(1-alpha)% confidence limit
	upper_PI=RISRP_res[,3]  # upper 100(1-alpha)% confidence limit

	plot(y_test,type="l",lwd=3,ylim=c(-10,10),xlab="Predicted and observed values")
	par(new=TRUE)
	plot(y_hat,type="l",lwd=3,ylim=c(-10,10),col="blue",xlab="")
	par(new=TRUE)
	plot(lower_PI,type="l",lwd=3,ylim=c(-10,10),col="red",lty=2,xlab="")
	par(new=TRUE)
	plot(upper_PI,type="l",lwd=3,ylim=c(-10,10),col="red",lty=2,xlab="")
