# Householder-methods
in numerical analysis <a href=https://en.wikipedia.org/wiki/Householder%27s_method>Householder methods</a>
are a class of <a href=https://en.wikipedia.org/wiki/Root-finding_algorithms>root finding algorithms</a>,
with this update formula where d denotes the number of algorithm in the householder class: 
![7a5b04531fa3e4601f2d6c503c0f980636b4f417](https://github.com/Mehrdadghassabi/Householder-methods/assets/53050138/9aa27e41-9fbf-45ee-8454-9856f754335b)


but there is another way to use Householder methods not using the mentioned formula!!
writing <a href=https://en.wikipedia.org/wiki/Taylor_series>Taylor_serie</a> of the given function with d sentences (where d denotes the number of algorithm in
the householder class) around $`x_n`$ with $`x_{n+1}`$ as the variable, solving it as algebraic equation would give us the update formula!!
## Example
lets take an example, consider $`cos(x)`$ as the function that we want to find its roots with different householder method
### householder number 1 (<a href=https://en.wikipedia.org/wiki/Newton%27s_method>newton raphson method</a>)
writting taylor serie with $`d=1`$ we would have:

$`\frac{f(x_n)}{0!}+ \frac{f'(x_n)}{1!}(x_{n+1} - x_n) = 0`$

$`\frac{cos(x_n)}{0!}+ \frac{-sin(x_n)}{1!}(x_{n+1} - x_n) = 0`$

$`cos(x_n) - sin(x_n)x_{n+1} + sin(x_n)x_n = 0`$

$`x_{n+1} =\frac{-cos(x_n) - sin(x_n)x_n}{-sin(x_n)} = 0`$

$`x_{n+1} =x_n + cot(x_n) `$

here in <a href=https://github.com/Mehrdadghassabi/Householder-methods/blob/main/householder_method.ipynb>this</a> jupyter notebook file
I implemented a function to solve $`cos(x) = 0`$ equation with a given initial guess and number of generation
if you want to solve another equation replace these lines with your function and its derivatives.
```
    f = math.cos(guess)
    fprim = -math.sin(guess)
```
and here it is the result of running with 10 generation & initial guess equal to one(in radian),
notice that the sequence approaches to the nearest answer to the initial guess.


![Screenshot from 2023-07-11 23-12-09](https://github.com/Mehrdadghassabi/Householder-methods/assets/53050138/56cc49e5-2ebe-488a-9323-cdd6e71b03a4)

### householder number 2 (<a href=https://en.wikipedia.org/wiki/Halley%27s_method>Halley method</a>)
lets write taylor serie with $`d=2`$

$`\frac{f(x_n)}{0!} + \frac{f'(x_n)}{1!}(x_{n+1} - x_n) + \frac{f''(x_n)}{2!}(x_{n+1} - x_n) = 0`$

$`\frac{cos(x_n)}{0!} + \frac{-sin(x_n)}{1!}(x_{n+1} - x_n)  + \frac{-cos(x_n)}{2!}(x_{n+1} - x_n)^2 = 0`$

$`(\frac{1}{2}cos(x_n))x_{n+1}^2 + (-sin(x_n)+cos(x_n))x_{n+1} +(-\frac{1}{2}cos(x_n)x_n^2 + sin(x_n)x_n + cos(x_n)) = 0`$

lets solve this equation using <a href=https://en.wikipedia.org/wiki/Quadratic_equation>delta</a> method, with

$`a = \frac{1}{2}cos(x_n)`$

$`b = -sin(x_n)+cos(x_n)`$

$`c = -\frac{1}{2}cos(x_n)x_n^2 + sin(x_n)x_n + cos(x_n)`$

$`\Delta = (-sin(x_n)+cos(x_n))^2 - 4(\frac{1}{2}cos(x_n))(-\frac{1}{2}cos(x_n)x_n^2 + sin(x_n)x_n + cos(x_n))`$

$`x_{n+1} = \frac{(sin(x_n)-cos(x_n) \pm \sqrt{\Delta})}{cos(x_n)}`$

and here it is the result of running with 10 generation & initial guess equal to one(in radian),
compare it with newton raphson result diagram!


![Screenshot from 2023-07-12 01-42-32](https://github.com/Mehrdadghassabi/Householder-methods/assets/53050138/2311844c-8a31-48c9-a3c0-b6edc65a2fe9)
