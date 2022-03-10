# TRes Equations

Let's say you have 2 dimensional data X, Y and you do a linear prediction with parameters Beta to get a Y_hat. 

Y_hat = beta X

You can determine the ordinary residuals to it with 

e_i = y_hat, i - y_i

Naturally, we would like to standardise these residuals, so we can choose to Studentise them (i.e. divide them by their standard deviation)

r_i = e_i/sigma(e)

It turns out that there is a formulat for computing these values based on the leverage (diagonal of the hat matrix) and the SSE (sum of squared errors). That equation is

r_i = e_i/sqrt(SSE(1-h_ii))

These residuals are termed as internally studentized residuals. But let's say that we would like to compute externally studentized ones. Well those ones can be determined by

d_i = y_hat, di - y_i

where the prediction is determined by fitting on the data set that has the ith point discarded. then the studentised residuals for these can be found via a similar formula as before

t_i = d_i/sigma(d)=d_i/sqrt(SSE_i(1-h_ii))

Now it can be a super big pain to have to refit your curve each time to determine what the deleted residuals are. Luckily there is a way to equate external residuals with internal onees:

t_i = r_i sqrt(n-p-1/(n-p-1r_i^2))

This formula can then be rearranged to give the following equation

t_i = r_i sqrt(n-p-1/(n-p-1e_i^2/SSE(1-h_ii))

t_i = r_i sqrt(n-p-1 SSE(1-h_ii)/(n-p-1)SSE(1-h_ii)-e_i^2 = e_i sqrt(n-p-1/(n-p-1)SSE(1-h_ii)-e_i^2)

References:
* https://www.stat.purdue.edu/~ghobbs/STAT_512/Lecture_Notes/Regression/Topic_17.pdf
* https://online.stat.psu.edu/stat501/lesson/11/11.4#:~:text=Studentized%20deleted%20residuals%20(or%20externally%20studentized%20residuals)&text=That%20is%2C%20a%20studentized%20deleted,standard%20deviation%20(first%20formula).
* https://www.youtube.com/watch?v=ZV6OfGgroc0

