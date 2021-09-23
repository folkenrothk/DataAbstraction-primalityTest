# Primality Testing

## Kate Folkenroth

## Program Output

### Use six fenced code blocks to provide output from different runs of `primality` with different inputs

TODO: Pick three different input values and run then each with
(a) the exhaustive algorithm
and
(b) the efficient algorithm

TODO: Overall, provide a total of six commands and six fenced code blocks
TODO: Three outputs should be from the efficient algorithm and three should be with the exhaustive algorithm
TODO: Run the exhaustive and efficient algorithm with the same inputs

#### Three outputs from running the exhaustive algorithm
`poetry run primality --number TODO --approach exhaustive`

```
```

`poetry run primality --number TODO --approach exhaustive`

```
```

`poetry run primality --number 49979687 --approach exhaustive`

```

```

#### Three outputs from running the efficient algorithm

`poetry run primality --number TODO --approach efficient`

```
```

`poetry run primality --number TODO --approach efficient`

```

```

`poetry run primality --number 49979687 --approach efficient`

```
😄 Attempting to determine if 49979687 is a prime number!

1, 49979687
✨ What divisors were found? None
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 49979687!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 09:14:18  Samples:  1
 /_//_/// /_\ / //_// / //_'/ //     Duration: 0.010     CPU time: 0.000
/   _/                      v4.0.3

Program: primality --number 49979687 --approach efficient --profile

0.001 primality  primality\main.py:112
└─ 0.001 stop  pyinstrument\profiler.py:136
      [3 frames hidden]  pyinstrument
         0.001 unsubscribe  pyinstrument\stack_sampler.py:77
```

## Performance Analysis

TODO: Provide one paragraph that states which algorithm is fastest, by how much
it is faster, and how you knew that the it was faster, referencing the data in
the aforementioned command outputs to support your response.

```
poetry run primality --number 49979687 --approach efficient --profile
😄 Attempting to determine if 49979687 is a prime number!

1, 49979687
✨ What divisors were found? None
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 49979687!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 09:14:18  Samples:  1
 /_//_/// /_\ / //_// / //_'/ //     Duration: 0.010     CPU time: 0.000
/   _/                      v4.0.3

Program: primality --number 49979687 --approach efficient --profile

0.001 primality  primality\main.py:112
└─ 0.001 stop  pyinstrument\profiler.py:136
      [3 frames hidden]  pyinstrument
         0.001 unsubscribe  pyinstrument\stack_sampler.py:77


```

```
poetry run primality --number 49979687 --approach exhaustive --profile
😄 Attempting to determine if 49979687 is a prime number!

<class 'int'>, 1, 49979687
✨ What divisors were found? None
✨ Was this a prime number? Yes

🔬 Here's profile data from performing primality testing on 49979687!

  _     ._   __/__   _ _  _  _ _/_   Recorded: 09:14:46  Samples:  1
 /_//_/// /_\ / //_// / //_'/ //     Duration: 5.028     CPU time: 5.031
/   _/                      v4.0.3

Program: primality --number 49979687 --approach exhaustive --profile

5.029 primality  primality\main.py:112
└─ 5.029 primality_test_exhaustive  primality\main.py:51
```
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

### Based on your experiences with this project, what is one way in which you want to improve?

From here, I wish to improve on my basic command knowledge of python. I think I need to look at some more documentation and take time on my own to translate my Java knowledge to Python. With this basic knowledge, I think the future projects will be easier and improve my ability to continue building my knowledge on more difficult concepts. 
