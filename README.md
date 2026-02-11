# Lab 04 - SOP/POS and KMaps

In this lab, you’ve learned how to apply KMaps, Sum Of Products and Products of
sums to simplify digital logic equations. Then, you’ve proven out that they work
using an implemented design on your Basys3 boards.

## Rubric

| Item | Description | Value |
| ---- | ----------- | ----- |
| Summary Answers | Your writings about what you learned in this lab. | 25% |
| Question 1 | Your answers to the question | 25% |
| Question 2 | Your answers to the question | 25% |
| Question 3 | Your answers to the question | 25% |

# Group 59: Luke Wallack, Shane Roy

## Lab Summary

We learned how to derive a naive equation from a given truth table, 
and use a k-map to simplify our naive equation into POS and SOP form. 
We also learned how to translate these equations into verilog code in Vivado. 
Also, we learned how to navigate through the schematic in the implemented 
design in Vivado, which was pretty cool.

## Lab Questions

### Why are the groups of 1’s (or 0’s) that we select in the KMap able to go across edges?
In a k-map, you can make groups as long as the paired inputs bits 
do not differ in more than one value. Because of this, we are able
to group across edges, which in this case allowed us to create multiple
large groups in our sum of products equation.

### Why are the names Sum of Products and Products of Sums?
The name "sum of products" comes from the fact that in boolean algebra,
the "+" (sum) operator is equivalent to OR, and the multiplication (products)
operator is equivalent to AND. In sum of products, we get our equation by
summing up all of our minterms, which consist of our inputs multiplied by each other (products),
hence the name summ of products. For products of sums, it is the opposite, as we are
multiplying all of our maxterms together, which consist of sums of our inputs.

### Open the test.v file – how are we able to check that the signals match using XOR?
We are able to check that the signals match using the XOR operator by comparing
each of our individual equations (naive, SOP, POS) to the expected output. The XOR
operator is used in the test file first to check if the POS and SOP form are the
same (since they should have the same outputs for any given index). If they differ,
then the test will fail. Then, the XOR operator is used to check if the maxterm output
is different from the naive output, and if it is, then the test will also fail.
By using the XOR operator in this way, we are able to make sure that the signals match for
the maxterm, minterm, and naive output.