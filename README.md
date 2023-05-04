Download Link: https://assignmentchef.com/product/solved-cse-522-assignment2-part2
<br>
The file GenericTree.java posted under Resources à Assignments defines a generic binary search tree class Tree&lt;T extends Comparable&lt;T&gt;&gt;.  The file also gives the outline of a generic external iterator for this class.  Your task in Part 2a is to complete the iterator definition by writing code for its constructor and the next() and hasNext() methods, as well as one more method explained below.

<em>Implementing the tree iterator.</em>  Refer to TreeIterator.png for a pictorial guidance on how to implement a tree iterator.  The key idea is to maintain a private<em> stack</em> <em>of trees</em> in the iterator class. The stack maintains the invariant that the next value to be returned by next() is contained in the tree node pointed to by the top of the stack.  When the iterator is initially created, its constructor should stack all nodes along the <em>left spine</em> of the tree so that the node containing the smallest value in the tree as at the top of the stack.  Each time next() is called, in addition to retrieving the next value to be returned and popping the stack, the stack should be updated so that its invariant is maintained.  As the sequence diagram A2_Part_2a.seq clarifies, it is helpful to define a private void method stack_left_spine() for this purpose.

The main method is contained in class GenericTree and it makes use of the generic iterator to test whether two sets represented as BSTs are equal.   Complete the definition of the generic tree iterator and run it and check whether your sequence diagram agrees with A2_Part_2a.seq.

There is <strong><em>no submission required for Part 2a</em></strong>, but the iterator you defined in this part will serve as a basis for part 2b described below.

<strong>(2b)</strong>  The file GenericIterators.java posted under Resources à Assignments defines generic versions of AbsTree, Tree, and DupTree discussed in the lectures.    The file also gives the outlines of generic external iterators for these classes,  called AbsTreeIterator, TreeIterator and DupTreeIterator respectively.  Your task in Part 2b is two-fold:




<ul>

 <li>Complete the iterator definitions by writing code for their constructor as well as the next(), hasNext() and stack_left_spine() The behavior of the iterator for Tree nodes is similar to that of Part 2a.   For DupTree nodes,  the next() method should return the value <em>v </em>in a DupTree node as many times as indicated by the count <em>k</em> associated with this node.  (Of course, each invocation of next() returns</li>

</ul>

only one value.)   <em>Hint: In order to implement this behavior, you might think in terms of stacking not just the tree/duptree node but also a count.</em>




The key criterion for Part 2b (i), apart from correct behavior, is that code duplication should be avoided.  In fact it is possible to define next(), hasNext() and stack_left_spine() entirely in AbsTreeIterator so that its subclasses only have to define their respective constructors.




<ul>

 <li>Refer to the two test methods, test1 and test2, which are called from the main method of the driver class, GenericIterators. The method test1 represents two sets in terms of two Trees and checks whether the first set is contained in the second.   The method test2 represents two bags in terms of two DupTrees and similarly checks for containment.   See further below for a clarification of containment.</li>

</ul>




Your task is to complete the definition of the static boolean method containedIn() in class GenericIterators so that it works for sets as well as bags.   This method invokes TreeIterator (for set containment) or  DupTreeIterator (for bag containment).




The key criterion for Part 2b (ii) is that, when the containment property does not hold, the function containedIn() should return false without always traversing both sets/bags.  This is possible because the elements of both sets/bags are Comparable and therefore can be enumerated in order.   The method containedIn() should print out on the Console the values that are compared during its execution.   The desired output is shown in file A2_Part_2b_ii_Console_Output.png.




Run GenericIterators.java to completion and check that your console output agrees with the desired output.   Also, save the object diagram in a file A2_obj2.png using the ‘Objects with Tables’ option.   The sequence diagram is not required.




<strong><em>What to Submit</em></strong>.   Prepare a top-level directory named <em>A2_Part2_UBITId1_UBITId2 </em>if the assignment is done by a team of two students; otherwise, name it as <em>A2_Part2_UBITId</em> if the assignment is done solo.  (Order the <em>UBITId</em>s in alphabetic order, in the former case.)   <em> </em>In this directory, place your source file GenericIterators.java and object diagram A2_obj2.png. Compress the directory and submit the compressed file using the submit_cse522  command.







<strong>End of Assignment 2 </strong>