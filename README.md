# utl-maximum-likelihood-estimate-of--therate-parameter-lamda-of-a-Poisson-distribution-sympy
Maximum likelihood estimate of the rate parameter lamda of a Poisson distribution sympy 
    %let pgm=utl-maximum-likelihood-estimate-of--therate-parameter-lamda-of-a-Poisson-distribution-sympy;

    Maximum likelihood estimate of the rate parameter lamda of a Poisson distribution sympy

    I hope I have done this correctly

    Estimate the rate parameter lamda of a Poisson distribution using MLE sympy

                         _     _
    Poisson(x) = \ X    | _ \   |
                 /\  exp|_  /\ _|  for X= 0,1,2..
                -----------------
                      X!

    log of Poisson =  x*log(lamda) - lamda + log(1/factorial(x))

    Derivative of the log Poisson

    d(log od poisson)
    -----------------  = (x/lamda -1)
      d lamda

    Solving for maximum liklihood estimate for the most likely value(x)

       x/lamda -1 = 0

       x=lamda (mean)

    github
    https://tinyurl.com/mu6tpndy
    https://github.com/rogerjdeangelis/utl-maximum-likelihood-estimate-of--therate-parameter-lamda-of-a-Poisson-distribution-sympy

    Related Repo
    https://github.com/rogerjdeangelis/utl-maximum-liklihood-regresssion-wps-python-sympy

    Related sympy repos

    https://github.com/rogerjdeangelis/utl-calculating-the-cube-root-of-minus-one-with-drop-down-to-python-symbolic-math-sympy
    https://github.com/rogerjdeangelis/utl-distance-between-a-point-and-curve-in-sql-and-wps-pythony-r-sympy
    https://github.com/rogerjdeangelis/utl-maximum-liklihood-regresssion-wps-python-sympy
    https://github.com/rogerjdeangelis/utl-python-sympy-projection-of-the-intersection-of-two-parabolic-surfaces-onto-the-xy-plane-AI
    https://github.com/rogerjdeangelis/utl-r-python-compute-the-area-between-two-curves-AI-sympy-trapezoid
    https://github.com/rogerjdeangelis/utl-solve-a-system-of-simutaneous-equations-r-python-sympy
    https://github.com/rogerjdeangelis/utl-symbolic-algebraic-simplification-of-a-polynomial-expressions-sympy
    https://github.com/rogerjdeangelis/utl-sympy-technique-for-symbolic-integration-of-bivariate-density-function

    /********************************************************************************************************************************************************/
    /*                                     |                                                          |                                                     */
    /*                                     |                                                          |                                                     */
    /*           INPUT                     |                      PROCESS                             |                     OUTPUT                          */
    /*                      _     _        |                                                          |                                                     */
    /* Poisson(x) = \ X    | _ \   |       | %utl_pybegin;                                            | Ther maximum likelihood estimate for the            */
    /*              /\  exp|_  /\ _|       | parmcards4;                                              | mean of the Poisson is Lamda                        */
    /*             -----------------       | import sympy as sp                                       |                                                     */
    /*                   X!                | import sympy.stats as st                                 |  Poisson=lamda**x * exp(-lam)) / factorial(mu)      */
    /* for X= 0,1,2..                      | import numpy as np                                       |                                                     */
    /*                                     | lam, mu = sp.symbols('lam mu', positive=True)            |  Log of Poisson                                     */
    /* Lets generate 30 random poisson     | pmf = (lam**mu * sp.exp(-lam)) / sp.factorial(mu)        |  Loglikelihood=-lam+mu*log(lam)+log(1/factorial(mu))*/
    /* realizations with                   | print(f"Poisson=lamda**x * exp(-lam)) / factorial(mu)")  |                                                     */
    /* lamda=5                             | loglik = sp.log(pmf)                                     |  Derivative of log likelihood = (-lam + mu)/lam     */
    /*                                     | si=sp.expand(loglik)                                     |                                                     */
    /* We use this generated data          | print(f"log likelihood = {si}")                          |  Solve extrema derivative=0 (-lam + mu)/lam = 0     */
    /* to check that the mean              | score = sp.diff(loglik, lam)                             |                                                     */
    /* of generated data is indeed the     | simp=sp.simplify(score);                                 |  MLE for poisson: lamda                             */
    /* MLE estimate                        | print(f"Derivative of log likelihood={simp}")            |                                                     */
    /*                                     | lam_hat = sp.solve(score, lam)[0]                        |  Check to see if 30 random observations             */
    /* data=[ 2,8,8,6,4,3,6,7,4,9,7,0,5,   | print(f"Solve extrema derivative {sp.simplify(score)}=0")|  yeild a mean of 5 (same as lamda)                  */
    /*  8,3,6,6,3,6,10,2,7,2,4,3,4,2,4,3,8]| print(f"MLE for poisson: lamda")                         |                                                     */
    /* mu = sum(data) / 30                 | data=[2,8,8,6,4,3,6,7,4,9,7,0,5,8,3,6,                   |  30 random Poisson realizations                     */
    /*                                     |  6,3,6,10,2,7,2,4,3,4,2,4,3,8]                           |  data=[2,8,8,6,4,3,6,7,4,9,7,0,5,8,3,6,             */
    /* * dreate random sample              | print(f"30 random Poisson realizations {data}")          |   6,3,6,10,2,7,2,4,3,4,2,4,3,8]                     */
    /* %utl_pybegin;                       | mu = sum(data) /30                                       |                                                     */
    /* parmcards4;                         | print(f"\nData simulation with true lam=5")              |  Data simulation with true lam=5                    */
    /* import numpy as np                  | print(f"Estimated lamda: {mu}")                          |                                                     */
    /* data=np.random.poisson(lam=5        | ;;;;                                                     |  Estimated mean=lamda: 5.0                          */
    /*   ,size=30)                         |                                                          |                                                     */
    /* print(data)                         |                                                          |                                                     */
    /* ;;;;                                |                                                          |                                                     */
    /* %utl_pyend;                         |                                                          |                                                     */
    /*                                     |                                                          |                                                     */
    /********************************************************************************************************************************************************/


    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */
                         _     _
    Poisson(x) = \ X    | _ \   |
                 /\  exp|_  /\ _|
                -----------------
                      X!
    for X= 0,1,2..

    Lets generate 30 random poisson v
    ariables with
    lamda=5

    We use this generated data
    to check that if the mean
    of generated data is indeed the
    MLE estimate

    data=[ 2,8,8,6,4,3,6,7,4,9,7,0,5,
     8,3,6,6,3,6,10,2,7,2,4,3,4,2,4,3,8]
    mu = sum(data) / 30

    /*
     _ __  _ __ ___   ___ ___  ___ ___
    | `_ \| `__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
    */

    %utl_pybegin;
    parmcards4;
    import sympy as sp
    import sympy.stats as st
    import numpy as np
    lam, mu = sp.symbols('lam mu', positive=True)
    pmf = (lam**mu * sp.exp(-lam)) / sp.factorial(mu)
    print(f"Poisson=lamda**x * exp(-lam)) / factorial(mu)")
    loglik = sp.log(pmf)
    si=sp.expand(loglik)
    print(f"log likelihood = {si}")
    score = sp.diff(loglik, lam)
    simp=sp.simplify(score);
    print(f"Derivative of log likelihood={simp}")
    lam_hat = sp.solve(score, lam)[0]
    print(f"Solve extrema derivative {sp.simplify(score)}=0")
    print(f"MLE for poisson: lamda")
    data=[2,8,8,6,4,3,6,7,4,9,7,0,5,8,3,6,
     6,3,6,10,2,7,2,4,3,4,2,4,3,8]
    print(f"30 random Poisson realizations {data}")
    mu = sum(data) /30
    print(f"\nData simulation with true lam=5")
    print(f"Estimated lamda: {mu}")
    ;;;;
    %utl_pyend;

    /*           _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| `_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    */

    Poisson=lamda**x * exp(-lam)) / factorial(mu)

    Log of Poisson
    Loglikelihood=-lam+mu*log(lam)+log(1/factorial(mu))

    Derivative of log likelihood = (-lam + mu)/lam

    Solve extrema derivative=0 (-lam + mu)/lam = 0

    MLE for poisson: lamda

    Check to see if 30 random observations
    yeild a mean of 5 (same as lamda)

    30 random Poisson realizations
    data=[2,8,8,6,4,3,6,7,4,9,7,0,5,8,3,6,
     6,3,6,10,2,7,2,4,3,4,2,4,3,8]

    Data simulation with true lam=5

    Estimated mean=lamda: 5.0

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
