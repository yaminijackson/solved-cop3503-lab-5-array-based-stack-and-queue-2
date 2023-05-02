Download Link: https://assignmentchef.com/product/solved-cop3503-lab-5-array-based-stack-and-queue-2
<br>
<h1>Overview</h1>

In this assignment, you will be implementing your own <em>Array-Based Stack</em> (ABS) and <em>Array-Based Queue</em>. A <strong>stack</strong> is a linear data structure which follows the last in, first out (LIFO) property. LIFO means that the data most recently added is the first data to be removed. (Imagine a stack of books, or a stack of papers on a desk—the first one to be removed is the last one placed on top.)  A <strong>queue</strong> is another linear data structure that follows the first in, first out (FIFO) property. FIFO means that the data added first is the first to be removed (like a line in a grocery store– the first person in line is the first to checkout).

<h1>Stack Behavior</h1>

<strong>Push</strong> – Add something to the top of the stack.

<strong>Pop</strong> – Remove something from the top of the stack and return it,




<strong>Example of LIFO operations-the data most recently added is the first to be removed</strong>

<h1>Queue Behavior</h1>

<strong>Enqueue</strong> – Add something to end of the queue.

<strong>Dequeue</strong> – Remove something from the front of the queue.




<strong>Example of FIFO operations-the newest data is last to be removed </strong>

<h1>Description</h1>

Your ABS and ABQ will be template classes, and thus will be able to hold any data type. (Many data structures follow this convention—reuse code whenever you can!) As with previous classes that use dynamic memory, you must be sure to define The Big Three: The Copy Constructor, the Assignment Operator, and the Destructor.

Data will be stored using a dynamically allocated array (hence the <em>array-based </em>stack and queue)<em>.</em> You may use any other variables/function in your class to make implementation easier.

By default, your ABS and ABQ will have a scale factor 2.0f.

<ol>

 <li>Attempting to push() or enqueue() an item onto an ABS/ABQ that is full will resize the current capacity to current_capacity*scale_factor.</li>

 <li>When calling pop() or dequeue(), if the “percent full” (e.g. current size / max capacity) becomes <strong>strictly less</strong> than 1/scale_factor, resized the storage array to current_capacity/scale_factor.</li>

</ol>




<strong>Why increase (or decrease) the size by any amount other than one? </strong>

Short answer: performance!

If you are increasing or decreasing the size of a container, it’s reasonable to assume that you will want to increase or decrease the size again at some point, requiring another round of allocate, copy, delete, etc.

Increasing the capacity by more than you might need (right now) or waiting to reduce the total capacity allows you to avoid costly dynamic allocations, which can improve performance—especially in situations in which this resizing happens frequently. This tradeoff to this approach is that it will use more memory, but this speed-versus-memory conflict is something that programmers have been dealing with for a long time.




<strong>An example of the resizing scheme to be implement on a stack. </strong>

<strong> </strong>

<strong> </strong>

<h1>Stack Functions</h1>

Your ABS must support the following methods:

<strong>Method                                                                           Description </strong>

<table width="590">

 <tbody>

  <tr>

   <td width="279">ABS()</td>

   <td width="311">Default constructor. Maximum capacity should be set to 1, and current size set to 0;</td>

  </tr>

  <tr>

   <td width="279">ABS(int capacity)</td>

   <td width="311">Constructor for an ABS with the specified starting maximum capacity.</td>

  </tr>

  <tr>

   <td width="279">ABS(const ABS &amp;d)</td>

   <td width="311">Copy Constructor</td>

  </tr>

  <tr>

   <td width="279">ABS &amp;operator=(const ABS &amp;d)</td>

   <td width="311">Assignment operator.</td>

  </tr>

  <tr>

   <td width="279">~ABS()</td>

   <td width="311">Destructor </td>

  </tr>

  <tr>

   <td width="279">void push(T data)</td>

   <td width="311">Add a new item to the top of the stack and resize if necessary.</td>

  </tr>

  <tr>

   <td width="279">T pop()</td>

   <td width="311">Remove the item at the top of the stack, resizes if necessary, and return the value removed. Throws -1 if the stack is empty.</td>

  </tr>

  <tr>

   <td width="279">T peek()</td>

   <td width="311">Return the value of the item at the top of the stack, without removing it. Throws -1 if the stack is empty.</td>

  </tr>

  <tr>

   <td width="279">unsigned int getSize()</td>

   <td width="311">Returns the current number of items in the ABS.</td>

  </tr>

  <tr>

   <td width="279">unsigned int getMaxCapacity()</td>

   <td width="311">Returns the current max capacity of the ABS.</td>

  </tr>

  <tr>

   <td width="279">T* getData()</td>

   <td width="311">Returns the array representing the stack.</td>

  </tr>

 </tbody>

</table>










Addition methods may be added as deemed necessary.
















<h1>Queue Functions</h1>

Your ABQ must support the following functions

<strong>Method                                                                           Description </strong>

<table width="590">

 <tbody>

  <tr>

   <td width="279">ABQ()</td>

   <td width="311">Default constructor. Maximum capacity should be set to 1, and current size set to 0;</td>

  </tr>

  <tr>

   <td width="279">ABQ(int capacity)</td>

   <td width="311">Constructor for an ABQ with the specified starting maximum capacity.</td>

  </tr>

  <tr>

   <td width="279">ABQ(const ABS &amp;d)</td>

   <td width="311">Copy Constructor</td>

  </tr>

  <tr>

   <td width="279">ABQ &amp;operator=(const ABQ &amp;d)</td>

   <td width="311">Assignment operator.</td>

  </tr>

  <tr>

   <td width="279">~ABQ()</td>

   <td width="311">Destructor </td>

  </tr>

  <tr>

   <td width="279">void enqueue(T data)</td>

   <td width="311">Add a new item to end of the queue and resizes if necessary.</td>

  </tr>

  <tr>

   <td width="279">T dequeue()</td>

   <td width="311">Remove the item at front of the queue, resizes if necessary, and return the value removed. Throws -1 if the queue is empty.</td>

  </tr>

  <tr>

   <td width="279">T peek()</td>

   <td width="311">Return the value of the item at the front of the queue, without removing it. Throws -1 if the queue is empty.</td>

  </tr>

  <tr>

   <td width="279">unsigned int getSize()</td>

   <td width="311">Returns the current number of items in the ABQ.</td>

  </tr>

  <tr>

   <td width="279">unsigned int getMaxCapacity()</td>

   <td width="311">Returns the current max capacity of the ABQ.</td>

  </tr>

  <tr>

   <td width="279">T* getData()</td>

   <td width="311">Returns the array representing the queue.</td>

  </tr>

 </tbody>

</table>










Addition methods may be added as deemed necessary.










S

<h1>Extra Credit (1%)</h1>

You can earn up to 1% extra credit (toward your final course grade) for this lab by doing everything listed below. DO NOT work on extra credit until your standard lab scored full points. If your standard lab does not score full points, you cannot earn any extra credit.




Update ABS/ABQ

Update your ABS and ABQ to use a scale factor other than 2.0f, and modify any methods that should behave differently as a result:

<ul>

 <li>ABS(int capacity, float scale_factor) : Constructor for an ABS with the specified starting capacity, and a custom scale factor.</li>

 <li>ABQ(int capacity, float scale_factor) : Constructor for an ABQ with the specified starting capacity, and a custom scale factor.</li>

</ul>




Add an extra attribute to your ABS and ABQ, total_resizes, which is a count of how many times the ABS/ABQ has been resized. Add an accessor for this attribute:

<ul>

 <li>unsigned int getTotalResizes(): Returns the total number of times the ABS has been resized.</li>

</ul>




Analysis Report

Create a testing file that can perform the following tasks, each with an ABS/ABQ that starts with a max capacity of 2:

<ul>

 <li>push <em>N</em> items onto an empty ABS.</li>

 <li>pop <em>N </em>items off an ABS with <em>N</em>  items already on it.   enqueue <em>N</em>  items onto an empty ABQ.</li>

 <li>dequeue <em>N </em>items off an ABQ with <em>N</em>  items already on it.   For each of the tasks, record:</li>

 <li>How long it takes to perform the task</li>

</ul>

○ Use the &lt;chrono&gt; or &lt;ctime&gt; libraries

<ul>

 <li>How many resizes were performed during the task</li>

</ul>




Do the tasks for each of the following possible combinations of Scale Factor and N*:

<table width="242">

 <tbody>

  <tr>

   <td width="106"><strong>Scale Factor </strong></td>

   <td width="136"><strong>N </strong></td>

  </tr>

  <tr>

   <td width="106">1.5</td>

   <td width="136">10 000 000</td>

  </tr>

  <tr>

   <td width="106">2.0</td>

   <td width="136">30 000 000</td>

  </tr>

  <tr>

   <td width="106">3.0</td>

   <td width="136">50 000 000</td>

  </tr>

  <tr>

   <td width="106">10.0</td>

   <td width="136">75 000 000</td>

  </tr>

  <tr>

   <td width="106">100.0</td>

   <td width="136">100 000 000</td>

  </tr>

 </tbody>

</table>

Depending on your computer specs, a significantly high N may take a very long time or crash the program. If necessary, you may pick 5 different values of N but be sure to vary their size decently to get the most interesting results.




You should have 100 different sets of data (4 tasks * 5 scale factors * 5 Ns).

Graph the data for each scale factor, with N being the independent variable and time being the dependent variable. Include the number of resizes for each task somewhere on the graph as well.

You should have 10 graphs, one for each scale factor per ABS/ABQ.




Write a 1-2 page analysis of your results. Make note of any trends in the data. Answer the following questions in your report.

<ul>

 <li>How does N affect the time it takes for?</li>

 <li>What are the effects of changing scale factor?</li>

 <li>How do both of these affect the number of times the ABS will be resized?</li>

 <li>What seems to be the best scale factor, and why?</li>

 <li>How can you explain differences between the performances of your ABS and ABQ?</li>

</ul>

<strong>Submission (on Canvas):    </strong>




<ul>

 <li>A <strong>well organized</strong> PDF containing relevant graphs, and your analysis.</li>

 <li>Your updated ABS.h file</li>

</ul>