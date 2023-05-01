Download Link: https://assignmentchef.com/product/solved-assignment-6-chapter-10-page-702-7-with-modifications
<br>



Introduction

The purpose of this assignment is to provide you with experience in working with pointers and dynamic memory allocation. The problem description is as follows. Additional specifications are shown in blue text.

<strong>This assignment is not implemented using classes. It is written in a single program</strong>




<table width="696">

 <tbody>

  <tr>

   <td width="696"><strong>7. Movie Statistics</strong>Write a program that can be used to gather statistical data about the number of movies college students see in a month. The program should ask the user how many students were surveyed and dynamically allocate an array of that size. The program should then allow the user to enter the number of movies each student has seen. The program should then calculate the average of the values entered. Create the following functions:●        <strong>printArray</strong>. This function should take in the dynamically created array (i.e. pointer to dynamically created array) and the size of the array as parameters. It should print out the contents of the array.●        <strong>getAverage</strong>. This function should take in the dynamically created array (i.e. pointer to dynamically created array) and the size of the array as parameters.  It should return the average as a double value.●        <strong>sortArray</strong>. This function should take in the dynamically created array (i.e. pointer to dynamically created array) and the size of the array as parameters. It sorts the array sent into it and returns nothing.●        <strong>getMaximum</strong>. This function should take in the dynamically created array (i.e. pointer to dynamically created array) and the size of the array as parameters. It should return the maximum value within the array as an int value. Make sure that user enters positive numbers for # of students and number of movies seen by each student</td>

  </tr>

 </tbody>

</table>




Note that you only have to calculate average, not median and mode of the values entered.

<strong>This assignment does not require you to create classes. Code the assignment in a single cpp file.</strong>

<strong> </strong>

<h2>Approach 1 – Use “regular” pointers</h2>

In this approach, an integer pointer variable is declared. An array (sized at the number entered by the user) is created and the memory address of this array is placed in the pointer variable. With this approach, <strong>remember to deallocate the dynamically created array.</strong>




<h2>Approach 2 – use Smart Pointers</h2>

You may use unique_ptr to declare a smart pointer to hold the address of the dynamically created array. The syntax to declare such a pointer and to set it to point to an array is as follows:

<table width="345">

 <tbody>

  <tr>

   <td width="23">12</td>

   <td width="322">unique_ptr&lt;int[]&gt; dynamic_array;dynamic_array = make_unique&lt;int[]&gt;(5);</td>

  </tr>

 </tbody>

</table>

The statements shown above create a 5 element array dynamically and place the address of this array in the dynamic pointer. In this assignment, a variable is used instead of the numeric literal “5”.




When using smart pointer, remember the following 2, very important, issues:

<ul>

 <li>Smart points MUST be passed into function by reference</li>

 <li>Dynamic arrays managed by unique pointer do not have to be “deleted”.</li>

</ul>




<h2>Sample output from my version of Assignment 5</h2>

User input is shown in bold, blue, highlighted text.







The <strong>main </strong>function’s pseudocode is as follows:




<table width="648">

 <tbody>

  <tr>

   <td width="648">In int main●    ask user for number of student to be surveyed●    ensure that the number is &gt; 0  (Do not check for non-numeric input, test with numbers)●    Setup dynamic array●    ask user to enter movies seen by each of the students●    ensure that number of movies seen by each student is &gt; 0 (Do not check for non-numeric input, test with numbers) ●    Invoke these functions:●    printArray function, passing in the appropriate arguments●    sortArray function, passing in the appropriate arguments●    printArray functions after the sortArray function has been invoked●    getAverage function, passing in the appropriate arguments, and print out the value returned by this function●    getMaximum function, passing in the appropriate arguments, and print out the value returned by this function</td>

  </tr>

 </tbody>

</table>


