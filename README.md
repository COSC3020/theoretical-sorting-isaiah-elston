[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/9YUeXH71)
# Theoretical Sorting

A Computer Science researcher claims to have come up with a sorting algorithm
that can sort arbitrary elements in $O(n)$ time based on comparisons of two
elements at a time. This would be asymptotically faster than any known general
sorting algorithm. The algorithm itself is proprietary and will be sold by a
company.

How would you verify this claim? You may assume that you have access to a
black-box implementation of the sorting algorithm, i.e. you cannot examine the
source code, but you can use it to sort any list you like. Explain in detail
your method for investigating whether X is correct, including any expected
results you would get.

Also give a theoretical argument for why X could or could not be correct, based
on the complexity of the general sorting problem we covered in class.

Add your answers to this markdown file.

## Answer

Assuming there is no way I could access the code of $\mathrm{X}$, I would only be able to test it using testing frameworks and recording the results. I would try to do something similar to what Dr. Kotthoff did in slide \#37 of the Sorting lecture materials. I would test $\mathrm{X}$ by passing numerous randomly generated inputs into it and then plotting the input size against the time it takes to sort the input. For more concise testing, I would run tests where I constrain the input sizes to follow certain patterns, such as already sorted, reverse sorted, or all elements are the same. Thereafter, I would make sure to test different input *types* such as integers, strings, floats, lists, etcetera. Finally, I would explicitly test any edge cases that I could think of, such as an empty list. 

After using testing frameworks to rigorously throw every varying condition that I could think of at $\mathrm{X}$, I would compile all of the test results and cross-reference them. Of course, no amount of random inputs can guarantee with 100\% certainty that $\mathrm{X}$ always sorts in linear time, but the plots would most definitely depict some form of a trend. The more test cases I run, the more confident I would be in the results, and if the visible trend is **not** linear, then I would be confident that I disproved the claim. If the trend never denoted anything aside from a linear pattern, then I would be more inclined to believe the claim. After I have tested every data-type, input size, and edge case that I could think of, I would effectively prove that $\mathrm{X}$ sorts any *conceivable* input in linear time. The recorded test results would certainly act as **empirical** evidence either supporting or refuting the time complexity of $\mathrm{X}$.

As for the likelihood of $\mathrm{X} \in \mathrm{\Theta}(n)$ for **any** arbitrary input size, I can reference slides \#40 through \#45 of the Sorting materials to come to a pretty definitive conclusion. We know that any arbitrary sorting problem can be modeled as a tree where each node represents a comparison, and each edge represents the possible comparisons that follow thereafter. By modeling the sorting process this way, we can visualize precisely how many distinct comparisons *need* be made in order to ensure that an input is *guaranteed* to be sorted. As it turns out, the Stirling approximation *(See slide \#45)* uses that tree model to empirically prove that a sorting algorithm must make at least $\Omega(n \log(n))$ comparisons in order to guarantee that an input is sorted.

It follows that $\mathrm{X} \in \mathrm{\Theta}(n)$ for **any** arbitrary input size is **theoretically impossible**. If that were true, the developers of $\mathrm{X}$ would have effectively disproved the Stirling approximation, and revolutionized mathematics as we currently know it. Considering that, I am certain that my rigorous testing would *eventually* depict some non-linear pattern in the relationship between input size and sorting time, and I would be able to confidently disprove the claim that $\mathrm{X}$ sorts in linear time. If the result were never non-linear, then I would have to reconsider my entire understanding of the universe.
