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

TODO: Provide the specific command that you ran to produce this output
TODO: Use a fenced code block to provide the output for this command.

TODO: Provide the specific command that you ran to produce this output
TODO: Use a fenced code block to provide the output for this command.

TODO: Provide the specific command that you ran to produce this output
TODO: Use a fenced code block to provide the output for this command.

#### Three outputs from running the efficient algorithm

TODO: Provide the specific command that you ran to produce this output
TODO: Use a fenced code block to provide the output for this command.

TODO: Provide the specific command that you ran to produce this output
TODO: Use a fenced code block to provide the output for this command.

TODO: Provide the specific command that you ran to produce this output
TODO: Use a fenced code block to provide the output for this command.

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

TODO: Use a fenced code block to provide the requested source code
TODO: Write at least one paragraph to explain the request source code

#### A function signature that defines the command-line interface for `primality`

TODO: Use a fenced code block to provide the requested source code
TODO: Write at least one paragraph to explain the request source code

### What was the greatest challenge that you faced when completing this assignment?

TODO: Provide a one-paragraph response that answers this question in your own words.

### Based on your experiences with this project, what is one way in which you want to improve?

TODO: Provide a one-paragraph response that answers this question in your own words.
