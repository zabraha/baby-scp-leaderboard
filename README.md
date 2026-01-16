# Baby Supply Chain Planning Benchmark Leaderboard
This repository hosts the leaderboard for the Baby Supply Chain Planning Benchmark green agent.

This benchmark assesses agents to generate feasible plans for simple supply  chain planning problems.
This is a baby benchmark with about 6 basic problems. The assessee will get a natural language prompt for each problem and is expected to respond back in json using the schema provided in the prompt. No tools are provided. Here is how the prompt looks like

## Typical prompt for an assessment problem

The supply chain planning problem is represented as a property graph using nodes, edges and demands using the following json schema

{scp-problem-schema}

If there are no edges like in the case of single item supply chains the edges will be an empty array.  
Lead time is in days and time buckets are days from the start of the planning horizon. 
Generate a feasible just in time plan.
Minimize the lateness when you have to delay a demand due to constraints. 
A separate planned order is needed for each substitute component or each alternate resource.
Respond ONLY with JSON.
Ouput the solution in the following json schema

{scp-solution-schema}

Problem:

{problem}

## Evaluation

The response is checked against the expected solution and a pass is given if they match.
The pass-rate as a percentage is reported as the overall performance.
