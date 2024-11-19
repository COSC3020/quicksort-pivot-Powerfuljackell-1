# Quicksort Pivots

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice." 

Used prior work at: https://github.com/COSC3020/quicksort-pivot-Powerfuljackell

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

There are 4 scenarios for the median-of-three approach Good = G Big = B Small = S :
    First scenario, where all three values are Good: GGG
    Second, where there are two Good values and one Big: (BGG, GGB, GBG)
    Third, where there are two Good values and one Small: (SGG, GGS, GSG)
    Fourth, where all three are different: (GBS, GSB, SGB, BGS, BSG, SBG)
In each scenario, you can calculate the associated probability base on a 1/2 probability given in the slides
    First: Each value is considered good, and so will have 1/2 the probability for each value or (1/2)^3 = 1/8
    Second and Third: combining the two results in the same outcome, as both too small or too big result in 1/4
    so  ((1/2)^2 * 1/4) * 6 = 3/8
    Fourth, Only one value is considered good, so ((1/2) * (1/4)^2) * 6 = 3/16
Adding each together (3/16 + 1/8 + 3/8) = 11/16 = 0.6875 or 68.75%
This means that in comparison to the 50% possibility of the first value being a good pivot, the Median-of-three method wins out.
