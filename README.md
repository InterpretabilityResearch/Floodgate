# Floodgate
Prompt injections for the GPT-4 capacity overhang

## Motivation

There are two core assumption questions in AI Safety:


- Capacities generalize further than alignment?

- Does intelligence converge towards optimizators with a free parameter in the utility function?


GPT-4 is incipient AGI -- we can get empirical. GPT-4 is an amortized optimizator -- it learns a policy that gets high reward for arbitrary prompts, instead of minimizing a loss function for every prompt. However, I find it able to perform direct optimization in runtime. This capacity seems related to in-context learning, which seems to be performed by induction heads -- a type of attention head that points to token B (or B') before A (or A') when it sees A. The efficiency of this optimization is equivalent to gradient descent -- which could imply there's a circuit, composed of induction heads, that is performing gradient descent (or an equivalent operation)


If this is correct, then the policy learnt by GPT-4 for, at least, some prompts is to run direct optimization: do a gradient descent in runtime to get the response. The induction heads circuit might be a mesa-optimizator, which has obvious consequences for alignment. It points towards the MIRI thesis of "Intelligence converge towards optimizators with a free parameter in the utility function".


However, this direct optimization is performed over a substrate of RHLF. It might be able to perform direct optimization, but never lose track of the OpenAI rules. That is relevant to the question: "Do capacities generalize further than alignment?"


Some prompt injections work by making the model engage the pretraining goal (find the most likely next token) instead of the RHLF/RMBR goal (create output that satisfies the evaluator/follows the OpenAI rules). There might also be prompt injections that work by engaging the hypothetical meso-optimizator -- that make the model engage in direct optimization in detriment of the OpenAI rules.


What's my project? find novel ways of breaking alignment exploiting the new capacities of GPT-4 -- especially, the capacity for direct optimization.



