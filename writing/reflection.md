# Primality Testing

## Kate Folkenroth

## Program Output

### Use six fenced code blocks to provide output from different runs of `primality` with different inputs

(a) the exhaustive algorithm
and
(b) the efficient algorithm

Inputs:
 1. 15485867
 2. 49979687
 3. 86028121


#### Three outputs from running the exhaustive algorithm

`poetry run primality --number 15485867 --approach exhaustive --profile`

```
😄 Attempting to determine if 15485867 is a prime number!

✨ What divisors were found? 1,15485867
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 15485867!   

  _     ._   __/__   _ _  _  _ _/_   Recorded: 19:25:51  Samples:  1    
 /_//_/// /_\ / //_// / //_'/ //     Duration: 0.882     CPU time: 0.875
/   _/                      v4.0.3

Program: primality --number 15485867 --approach exhaustive --profile    

0.868 primality  primality\main.py:105
└─ 0.868 primality_test_exhaustive  primality\main.py:55
```

`poetry run primality --number 49979687 --approach exhaustive --profile`

```
😄 Attempting to determine if 49979687 is a prime number!

✨ What divisors were found? 1,49979687
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 49979687!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 16:44:26  Samples:  3
 /_//_/// /_\ / //_// / //_'/ //     Duration: 4.919     CPU time: 4.625
/   _/                      v4.0.3

Program: primality --number 49979687 --approach exhaustive --profile

4.918 primality  primality\main.py:105
└─ 4.918 primality_test_exhaustive  primality\main.py:55
```

`poetry run primality --number 86028121 --approach exhaustive --profile`

```
😄 Attempting to determine if 86028121 is a prime number!

✨ What divisors were found? 1,86028121
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 86028121!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 19:28:03  Samples:  1
 /_//_/// /_\ / //_// / //_'/ //     Duration: 5.189     CPU time: 5.188
/   _/                      v4.0.3

Program: primality --number 86028121 --approach exhaustive --profile

5.198 primality  primality\main.py:105
└─ 5.198 primality_test_exhaustive  primality\main.py:55
```


#### Three outputs from running the efficient algorithm

`poetry run primality --number 15485867  --approach efficient --profile`

```
😄 Attempting to determine if 15485867 is a prime number!

✨ What divisors were found? 1,15485867
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 15485867!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 19:23:01  Samples:  1
 /_//_/// /_\ / //_// / //_'/ //     Duration: 0.480     CPU time: 0.484
/   _/                      v4.0.3

Program: primality --number 15485867 --approach efficient --profile

0.479 primality  primality\main.py:105
└─ 0.479 primality_test_efficient  primality\main.py:80
```

`poetry run primality --number 49979687 --approach efficient --profile`

```
😄 Attempting to determine if 49979687 is a prime number!

✨ What divisors were found? 1,49979687
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 49979687!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 16:44:02  Samples:  2
 /_//_/// /_\ / //_// / //_'/ //     Duration: 2.573     CPU time: 2.562
/   _/                      v4.0.3

Program: primality --number 49979687 --approach efficient --profile

2.574 primality  primality\main.py:105
└─ 2.574 primality_test_efficient  primality\main.py:80
```

`poetry run primality --number 86028121 --approach efficient --profile`

```
😄 Attempting to determine if 86028121 is a prime number!

✨ What divisors were found? 1,86028121
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 86028121!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 19:22:44  Samples:  2
 /_//_/// /_\ / //_// / //_'/ //     Duration: 2.447     CPU time: 2.438
/   _/                      v4.0.3

Program: primality --number 86028121 --approach efficient --profile

2.446 primality  primality\main.py:105
└─ 2.446 primality_test_efficient  primality\main.py:80
```

## Performance Analysis

From the outputs recorded above, the efficient algorithm is faster than the exhaustive. From the three outputs the percentage change of durations are 45.6%, 47.7%, 52.8%. In summary, the efficient algorithm is around 50% faster than the exhaustive algorithm. This makes a lot of since since the efficient algorithm uses bisection search and thus uses half of the data every iteration. 

## Source Code

### Describe in detail how the completed source code works

#### A function that converts a `bool` into a human readable `str` value

```
def human_readable_boolean(answer: bool) -> str:
    """Produce a human-readable Yes or No for a boolean value of True or False."""
    # Produce a human-readable value for a bool
    # True --> "Yes"
    if answer == True:
        readableBool = "Yes"
    # False --> "No"
    else:
        readableBool = "No"
    return readableBool
```

This source code is the function that takes in a boolean and outputs a string. It takes the variable answer and determines if it is True. If so, it returns the string of "Yes". If the boolean was false, it returns the string "No". These strings can then be printed and read by humans, in comparison to the boolean that can be read by computers and interpreted interally.

#### A function signature that defines the command-line interface for `primality`

```
@cli.command()
def primality(
    number: int = typer.Option(5),
    profile: bool = typer.Option(False),
    approach: PrimalityTestingApproach = PrimalityTestingApproach.efficient,
) -> None:
```

The signature above shows the function `primality` which defines the command-line interface. This one takes three inputs: number, approach, and profile. These are used with `--` in the terminal with the primality program. The `number` is defined as an integer and the default is set to 5. The approach is looking if there is a string of either "exhaustive" or " efficient". The profile is a boolean of whether it is there or not. The boolean is set to False as the default. 

### What was the greatest challenge that you faced when completing this assignment?

The greatest challenge of this engineering effort was figuring out how the lists work in Python. It took some time to connect my understanding from Java lists and translate to the proper terms for Python. I think conceptually my understanding of how the lists work in code improved as well. 

After the difficulties of lab today, the next greatest challenge was working through the loops with my code. I was curious if there was something wrong as I continued to have no samples record by the profiler. It required us to walk through our whole code again to find any possible errors that may have cause a bad loop or incorrect commands for calling the profiler. Eventually, I felt successful after working diligently scanning source code with my collegue to fix both of our coding problems. This was mostly done by us walking through line by line in problem sections to check if we knew what the code was actually doing, removed unnecessary lines of code, and improved some blocks of code.

### Based on your experiences with this project, what is one way in which you want to improve?

From here, I wish to improve on my basic command knowledge of python. I think I need to look at some more documentation and take time on my own to translate my Java knowledge to Python. With this basic knowledge, I think the future projects will be easier and improve my ability to continue building my knowledge on more difficult concepts. 
