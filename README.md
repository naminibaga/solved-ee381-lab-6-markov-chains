Download Link: https://assignmentchef.com/product/solved-ee381-lab-6-markov-chains
<br>
A machine can be in two possible states A and B. The two states A and B are designated by the numbers 1 and 2 respectively.

The state of the machine at time (<em>k</em>+1) is determined by the state of the machine at the previous time step <em>k </em>:

<ul>

 <li>If the state at <em>k</em> is A, then the state at (<em>k</em>+1) will be A with probability <em>p</em><sub>11</sub></li>

 <li>If the state at <em>k</em> is A, then the state at (<em>k</em>+1) will be B with probability <em>p</em><sub>12</sub></li>

 <li>If the state at <em>k</em> is B, then the state at (<em>k</em>+1) will be A with probability <em>p</em><sub>21</sub></li>

 <li>If the state at <em>k</em> is B, then the state at (<em>k</em>+1) will be B with probability <em>p</em><sub>22</sub></li>

</ul>

These state transitions are shown schematically in Figure 1. Also, Figure 2 shows the same information on state transition probabilities in a more compact form.




<strong>      </strong>

<strong>                                           </strong>Clearly: <em>p</em>11 + <em>p</em>12 =1 and <em>p</em>21 + <em>p</em>22 =1.




For this example the transition probabilities have the following values:

<em>p</em><sub>11 </sub>= 0.6     ; <em>p</em><sub>12 </sub>= 0.4       ; <em>p</em><sub>21 </sub>= 0.5       ; <em>p</em><sub>22 </sub>= 0.5




The initial state is randomly distributed between state “A” and state “B”.

The probability of the initial state being “A” is given as: Prob (Initial State = A) = 0.2

The probability of the initial state being “B” is given as: Prob (Initial State = B) = 0.8




The graphs below show several simulation  results for this two-state Markov chain. The chain is run for <em>n</em>=10 time  steps.




<strong>Figure 0.3 </strong>shows a single simulation run of the chain. The initial state of  the chain is “A”. The graph shows the evolution of the chain for the next 15 steps. In this particular simulation the chain goes through the following sequence of states, after the initial state “A”: [<em>A AAAABBBBA</em>]




<strong>Figure 0.4 </strong>shows another single simulation run of the chain. In this case the initial state of  the chain is “B”. The graph shows the evolution of the chain for the next 15 steps. In this particular simulation the chain goes through the following sequence of states, after the initial state “B”:

<h1>[B BABAAAABB]</h1>

<strong>Figure 0.5 </strong>shows the combined results from N=10000 simulation runs of the chain. It is seen that the chain starts at state “A” 20% of the time, and  at state “B” 80% of the time. The graph shows the evolution of the chain for the next 10 steps.

<strong>Figure 0.6 </strong>shows the results of the state evolution using the “State Transition Matrix” approach.

The probabilities are <em>CALCULATED based on the transition matrix</em>. The probabilities they <em>ARE NOT derived as the result of N=10000 simulation runs</em>, as was done in Figure 0.5. It is noted that the results of Figures 0.5 and 0.6 are very similar, almost identical, confirming the  fact that the state transition matrix approach can be used instead of a step-by-step simulation.




PROBLEM 1.  A three-state Markov Chain

Follow the previous code as a guide, and  simulate the Markov chain defined in problem 11.1 of the AMS text by Grinstead &amp; Snell, p. 406 (reference [1]).

For this problem use the provided values of the state transition matrix and the initial probability distribution.

<ol>

 <li>Run each experiment for <em>n</em>=15 time steps. In order to obtain meaningful statistical data perform a total of  <em>N </em>=10,000</li>

 <li>After your experimental simulations are completed, use the State Transition Matrix approach and compare the results.</li>

</ol>

<strong>SUBMIT a report </strong>with the results and your code. You must follow the guidelines given in the syllabus regarding the structure of the report. Points will  be taken off,  if you do not follow the guidelines. The report should contain:

<ul>

 <li>One plot showing one single-simulation run for <em>n</em>=15  steps, similar to Figure 0.3, but for a  three-state chain. Make sure that your plot has the appropriate labels and title.</li>

 <li>A plot with the simulated probabilities for the states R, N, S, similar to Figure 0.5</li>

 <li>A plot with the probabilities obtained through the state transition matrix approach for the three states R, N, S, similar to Figure 0.6</li>

 <li>The code in an Appendix</li>

 <li><strong>Make sure that all the plots are properly labeled </strong></li>

</ul>

<strong> </strong>PROBLEM 2.  The Google PageRank Algorithm

This problem presents an introduction to the algorithm used for ranking web pages for searching purposes. The algorithm was developed by Google’s founders Page and Brin with Motwani and Winograd, and was first published in 1998 (see reference [2]). The <em>PageRank </em>algorithm allowed <em>Google </em>to rise to the top of all web search engines within a matter of months after its implementation, outperforming the established search engines of the time such as <em>AltaVista</em> and <em>Yahoo</em>. The algorithm is based on the theory of Markov chains, utilizing the information on the number of links leading to an existing webpage.

The current problem uses a simplified web in order to show how the algorithm works (see reference [3]). The simplified web consists of 5 pages only, and it is shown schematically in Figure 2.1.

Figure 2.1: A five-page web




A Markov chain model of an <em>impartial surfer</em> visiting web pages is created as following:

<ul>

 <li>At time <em>k</em> the surfer is on page <em>X </em>, where <em>X</em>∈{<em>A B C D E</em>, ,           ,           , }.</li>

 <li>At time (<em>k</em>+1) the surfer will move randomly to another page <em>Y </em>, which must be linked to <em>X </em>.</li>

 <li>The state <em>S</em><em><sub>k</sub></em> of the Markov chain at time <em>k </em>is defined as the page which the surfer is visiting at time <em>k </em>: <em>S</em><em><sub>k </sub></em>∈{<em>A B C D E</em>, , , , }.</li>

 <li>To create the Markov chain model, the algorithm assumes that all pages that can be reached from <em>X</em> have the same probability to be visited by the surfer. Thus:</li>

</ul>

<table width="670">

 <tbody>

  <tr>

   <td width="135">Prob (<em>S</em><em><sub>k</sub></em><sub>+</sub><sub>1 </sub>=<em>Y S</em>| <em><sub>k</sub></em></td>

   <td width="35"><em>X</em>=)</td>

   <td width="273">                              1<sup></sup>(Total number of links leaving page X)        =                              0</td>

   <td width="24">,,</td>

   <td width="202">if  can be reached from <em>Y   X</em> if  cannot be reached from <em>Y   X</em></td>

  </tr>

 </tbody>

</table>




<ul>

 <li>For example: Prob (<em>S</em><em><sub>k</sub></em><sub>+</sub><sub>1 </sub>=<em>A S C</em>| <em><sub>k </sub></em>)=  ;  Prob (<em>S</em><em><sub>k</sub></em><sub>+</sub><sub>1 </sub>=<em>E S</em>| <em><sub>k </sub></em><em>D</em>)= 0 ; etc.</li>

</ul>




<ul>

 <li>Based on these probabilities the State Transition Matrix ( <em>P </em>) of the Markov chain is constructed. The left eigenvector <em>w</em> of <em>P </em>corresponding to the eigenvalue λ=1 (which is a <em>fixed vector</em> of the Markov chain) is computed from: <em>wP w</em>=</li>

 <li>The <em>PageRank</em> algorithm uses the vector <em>w</em> to rank the pages of the five-page web in terms of visiting importance.</li>

</ul>




<strong>To complete this problem follow the steps below: </strong>

<ol>

 <li>Create the 5 5× State Transition Matrix <em>P </em>with the values of the transition probabilities 2. Assume that initially all pages are equally likely to be visited, i.e. use the initial state</li>

</ol>

probability distribution vector: <em>v</em><sub>1 </sub>=[<em>A B C D E</em>]=<sup></sup><sub></sub><sup>1 1 1 1 1</sup><sub>5 5 5 5 5</sub><sub></sub><sup></sup><sub></sub>

<ol start="3">

 <li>Calculate the probability vectors for  <em>n</em>=1,2,K20 steps,<strong> using the State Transition matrix only. </strong>Note that <em>you ARE NOT asked to run the complete simulation</em> of the chain. You are only asked to use the State Transition matrix approach to calculate the probability vectors for <em>n</em></li>

 <li>Rank the pages {<em>A B C D E</em>, , , , }in order of importance based on the results from the previous step</li>

 <li>Create a plot of the calculated state probabilities for each of the five states {<em>A B C D E</em>, ,      ,           , }</li>

</ol>

the number of steps for <em>n</em>=1,2,K20 . This should be similar to the plot in  Figure 0.6

<ol start="6">

 <li>Assume that the surfer always starts at his/her home page, which for the purposes of this problem is page <em>E </em>. Repeat steps (2)-(5) with the new state probability distribution vector: <em>v</em><sub>2 </sub>=[<em>A B C D E</em>]=[0 0 0 0 1]</li>

</ol>




<strong>SUBMIT a report </strong>with the results and your code. You must follow the guidelines given in the syllabus regarding the structure of the report. Points will  be taken off,  if you do not follow the guidelines. The report should contain:

<ul>

 <li>The 5 5× State Transition Matrix <em>P</em></li>

 <li>For the initial state probability distribution vector<em>v</em><sub>1</sub>:

  <ul>

   <li>Submit the page ranking calculated in Step 4. <em>Use Table 1 for your answer. </em>Note: You will need to replicate the table in your Word file, in order to provide the answer in your report. Points will be taken off if you do not use the table. v Submit the plot created in Step 5.</li>

  </ul></li>

 <li>For the initial state probability distribution vector<em>v</em><sub>2</sub>

  <ul>

   <li>Submit the page ranking calculated in Step 4. <em>Use Table 1 for your answer. </em>Note: You will need to replicate the table in your Word file, in order to provide the answer in your report. Points will be taken off if you do not use the table. v Submit the plot created in Step 5.</li>

  </ul></li>

 <li>The code in an Appendix.</li>

 <li>Make sure the plots are <strong>properly labeled</strong></li>

</ul>







<table width="566">

 <tbody>

  <tr>

   <td colspan="3" width="249">Initial probability vector: <em>v</em><sub>1</sub></td>

   <td rowspan="8" width="75">        </td>

   <td colspan="3" width="243">Initial probability vector: <em>v</em><sub>2</sub></td>

  </tr>

  <tr>

   <td width="80">Rank</td>

   <td width="79">Page</td>

   <td width="90">Probability</td>

   <td width="77">Rank</td>

   <td width="76">Page</td>

   <td width="90">Probability</td>

  </tr>

  <tr>

   <td width="80"> </td>

   <td width="79"> </td>

   <td width="90"> </td>

   <td width="77"> </td>

   <td width="76"> </td>

   <td width="90"> </td>

  </tr>

  <tr>

   <td width="80">1</td>

   <td width="79"> </td>

   <td width="90"> </td>

   <td width="77">1</td>

   <td width="76"> </td>

   <td width="90"> </td>

  </tr>

  <tr>

   <td width="80">2</td>

   <td width="79"> </td>

   <td width="90"> </td>

   <td width="77">2</td>

   <td width="76"> </td>

   <td width="90"> </td>

  </tr>

  <tr>

   <td width="80">3</td>

   <td width="79"> </td>

   <td width="90"> </td>

   <td width="77">3</td>

   <td width="76"> </td>

   <td width="90"> </td>

  </tr>

  <tr>

   <td width="80">4</td>

   <td width="79"> </td>

   <td width="90"> </td>

   <td width="77">4</td>

   <td width="76"> </td>

   <td width="90"> </td>

  </tr>

  <tr>

   <td width="80">5</td>

   <td width="79"> </td>

   <td width="90"> </td>

   <td width="77">5</td>

   <td width="76"> </td>

   <td width="90"> </td>

  </tr>

 </tbody>

</table>


