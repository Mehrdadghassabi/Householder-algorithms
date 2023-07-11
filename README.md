# Householder-methods
in numerical analysis <a href=https://en.wikipedia.org/wiki/Householder%27s_method>Householder methods</a>
are a class of <a href=https://en.wikipedia.org/wiki/Root-finding_algorithms>root finding algorithms</a>,
with this update formula where d denotes the number of algorithm in the householder class: 
![7a5b04531fa3e4601f2d6c503c0f980636b4f417](https://github.com/Mehrdadghassabi/Householder-methods/assets/53050138/9aa27e41-9fbf-45ee-8454-9856f754335b)


but there is another way to use Householder methods not using the mentioned formula!!
writing <a href=https://en.wikipedia.org/wiki/Taylor_series>Taylor_serie</a> of the given function with d sentences (where d denotes the number of algorithm in
the householder class) around $`x_n`$ with $`x_n+1`$ as the variable, solving it as algebraic equation would give us the update formula!!
lets take an example, consider $`cos(x)`$ as the function that we want to find its roots writting taylor serie with $`n=1`$ .
we would have:

$`(f(x_n)/0!)+ (f'(x_n)/1!)*(x_n+1 - x_n) = 0`$

$`(cos(x)/0!)+ (-sin(x)/1!)*(x_n+1 - x_n) = 0`$

$`cos(x) - sin(x)*x_n+1 + sin(x)*x_n`$

$`x_n+1 =(-cos(x) - sin(x)*x_n)/(-sin(x))`$

$`x_n+1 =x_n + cot(x) `$
