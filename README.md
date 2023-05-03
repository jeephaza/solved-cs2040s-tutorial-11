Download Link: https://assignmentchef.com/product/solved-cs2040s-tutorial-11
<br>
<h1>Problem 1.         MST</h1>

Perform Prim’s, Kruskal’s, and Boruvka’s MST algorithm on the graph above.

<h1>Problem 2.          Faster MST</h1>

Henry The Hacker has some ideas for a faster MST algorithm!

<strong>Problem 2.a. </strong>Recently, he read about <em>Fibonacci Heaps</em>. A Fibonacci heap is a priority queue that implements insert, delete, and decreaseKey in <em>O</em>(1) amortized time, and implements extractMin in <em>O</em>(log<em>n</em>) amortized time, assuming <em>n </em>elements in the heap. If you run Prim’s Algorithm on a graph of <em>V </em>nodes and <em>E </em>edges using a Fibonacci Heap, what is the running time?

<strong>Problem 2.b.           </strong>Henry suggest the following algorithm:

<ol>

 <li>Run <em>O</em>(loglog<em>V </em>) Boruvka’s steps (and save all blue edges).</li>

 <li><em>Contract </em>each blue connected component, i.e., build a new graph where each node corresponds to a connected component, and each edge corresponds to an edge between two connected components.</li>

 <li>Run Prim’s algorithm with a Fibonacci Heap on the new graph.</li>

</ol>

What is the running time of this algorithm?

<strong>Problem 2.c. </strong>Which of these two new variants for finding an MST would you prefer? When is the version from Part(a) better than the version from Part(b) and vice versa?

<h1>Problem 3.            Divide-and-Conquer MST <em>(Optional)</em></h1>

Henry The Hacker has invented a new divide-and-conquer algorithm for finding a minimum spanning tree! The algorithm is super simple! It only involves 4 steps:

<ol>

 <li>Find the median edge weight <em>w<sub>e</sub></em>.</li>

 <li>Partition the edges using the edges into those ≤ <em>w<sub>e </sub></em>and those <em>&gt; w<sub>e </sub></em>into two graphs <em>G<sub>a </sub></em>and <em>G<sub>b</sub></em>.</li>

 <li>Recursively find the MST for <em>G<sub>a </sub></em>and <em>G<sub>b</sub></em>, yielding trees <em>T<sub>a </sub></em>and <em>T<sub>b</sub></em>.</li>

 <li>Combine the edges from <em>T<sub>a </sub></em>and <em>T<sub>b</sub></em>, and recursively find the MST for the resulting graph.</li>

</ol>

After a little bit of thought, Henry realizes that he can speed it up by stopping the recursion early (i.e., not going down to a base case of 1). Instead, if the number of edges in the graph <em>E &lt; </em>4<em>V </em>, then the recursion terminates and he uses Prim’s algorithm to find the MST.

How well do you think this algorithm works? (What would happen if it continued to a base case of 1 edge?)

<h1>Problem 4.         Power Plant</h1>

Given a network of power plants, houses and potential cables to be laid, along with its associated cost, find the cheapest way to connect every house to at least one power plant. The connections can be routed through other houses if required.

In the diagram above, the top graph shows the initial layout of the power plants (modelled as red nodes), houses (modelled as gray nodes) and cables (modelled as bidirectional edges with its associated cost). The highlighted edges shown in the bottom graph shows an optimal way to connect every house to at least one power plant. Come up with an algorithm to find the minimum required cost. You may assume that there exists at least one way to do so.

<h1>Problem 5.          Traffic Reduction</h1>

In order to reduce traffics, the Singapore government has passed a new law – cars are not allowed to go in circles. If you drive around in a circle, you will be charged a fine. Your job is to deploy a set of cameras to monitor the roads and catch drivers that are violating the new law.

For this problem, you are given a road map of Singapore as a connected, undirected graph <em>G </em>= (<em>V,E</em>). For each road (i.e., edge) <em>e</em>, you are given the cost <em>w</em>(<em>e</em>) of building a camera station that can detect when the same car passes twice. Your job is to find a minimal set of roads (i.e., edges) such that you can detect any car that makes a circle.

<h1>Problem 6.         Espionage</h1>

You are a spy, currently on a mission to obtain intel on the final examination that will be unleashed upon this world by the dreaded <em>Htes Treblig </em>within the next 25 days. At the moment, you have a message to send to HQ in the form of a <strong>weighted tree </strong>of <em>N </em>vertices, where all of the edge weights are positive integers.

To ensure your message is not at risk of being intercepted, you need to encrypt your message. The way you decide to do this is by inserting additional edges (with integer weights) to your tree. The resulting graph, which represents the encrypted message, must satisfy the following properties:

<ul>

 <li>The resulting graph is a <strong>complete graph </strong>of <em>N </em>vertices (i.e. every pair of vertices in the graph must have exactly 1 edge between them).</li>

 <li>The initial tree is <strong>the unique Minimum Spanning Tree </strong>of the resulting graph.</li>

</ul>

Inserting edges with large weights will make the encryption process more complicated, so you would like to avoid them wherever possible. The cost of the encryption process is defined as the sum of the weights of the additional edges that are inserted into the graph during the encryption process.

Given the initial message, which consists of the number of vertices in the tree, <em>N</em>, and a list of <em>N </em>− 1 edges of the tree, <strong>output the minimum possible cost </strong>of encrypting this message.

For example, let the initial message be the tree on the left, consisting of <em>N </em>= 4 vertices. The graph on the right represents the optimal way to encrypt the message with a total cost of 17+17+13 = 47. Therefore, the expected output is 47.

<h1>Problem 7.         Road Trip</h1>

Relevant Kattis Problems:

<ul>

 <li>https://open.kattis.com/problems/adventuremoving4</li>

 <li>https://open.kattis.com/problems/highwayhassle</li>

 <li>https://open.kattis.com/problems/roadtrip</li>

</ul>

You are going on a road trip. You get in your trusty car and drive to Panglossia, where you will spend a nice vacation by the beach.

You have already found the best route from your home to Panglossia (using Dijkstra’s Algorithm). Next, you need to determine where you can buy petrol along the way. On the road between your home and Panglossia, there are a set of <em>n </em>petrol stations, the last of which is in Panglossia itself. Assume that your trip is complete when you reach the last station.

By searching on the internet, you find for each station, its location on the road and the cost of petrol. That is, the input to the problem is <em>n </em>stations, <em>s</em><sub>0</sub><em>,s</em><sub>1</sub><em>,…,s<sub>n</sub></em><sub>−1</sub>, along with <em>c</em>(<em>s<sub>i</sub></em>), which specifies the cost of petrol at station <em>s<sub>i</sub></em>, and <em>d</em>(<em>s<sub>i</sub></em>), which specifies the distance from station <em>s</em><sub>0 </sub>to station <em>s<sub>i</sub></em>.

The tank of your car has a capacity of <em>L </em>liters. You begin your trip at home with a full tank of petrol. Your car uses exactly 1 liter per kilometer. Along the way, you must ensure that your car always has petrol (though you may arrive at a station just as you run out of petrol). Note that you do not need to fill your tank at a station. You can buy any amount of petrol, as long as it’s within the capacity of your tank.

Your job is to determine <strong>how much petrol to buy at each station </strong>along the way so as to minimize the cost of your trip.

You may assume, for simplicity, that <em>L </em>and all the given distances are integers, i.e., all the quantities are integers.

Here are two examples, a simple one and a more complicated one.

<strong>Example 1:         </strong>Your tank holds 6 liters, and there are 3 stations:

5km: $1

6km: $2

7km: $4

In this case, the best solution costs one dollar, where you purchase one liter of petrol at the first station at a cost of 1 per liter.

<strong>Example 2:         </strong>Your tank holds 20 liters, and there are 10 stations:

7km: $3

17km: $5

20km: $2

23km: $1

39km: $5

48km: $4

66km: $9

83km: $9

88km: $4

92km: $1

In this case, the best solution is to purchase petrol at each station as follows, for a total cost of 327 dollars:

0

0

3

20

5

20

15

5

4

0

<strong>Hint: </strong>To solve this problem, think about how to calculate the cost <em>DP</em>(<em>s<sub>j</sub>,k</em>), the minimum cost to get from station <em>s<sub>j </sub></em>to the destination, assuming you start at station <em>s<sub>j </sub></em>with <em>k </em>liters of petrol left.