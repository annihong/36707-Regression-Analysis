## Questions to answer:
### 1. Understand what nodes and arrows in a causal DAG mean, and how you could draw a DAG for a simple situation

- Nodes represent different variables and arrows represent the direction of causal effects. A -> B -> C: A is B's parent and B is A's child, C is A's desandant, A is C's ancestor. 
- ?

### 2.Where does the causal DAG come from? Is it something we know, something we assume, or something we easily can estimate from data?

- Causal DAG comes from analyst's assumption about the data generating process (confirmed by the data?). 
- *exclusion restriction:* it is a stronger assumption to assume the *absence* of an arrow and saying that there is no causal effect between the two variables.   
- Advantage of using causal DAGs:
    1. identification ?
    2. testing for assumptions ?

### 3.Understand what the paper means by "conditioning on" a specific variable. (If it helps, think specifically about linear models.)

- It means taking into account/teasing out the variability due to a specific variable. Ways to do it includes restrict the sample base on that variable and then look at the association between other variables. Or in the linear regression case, it is usually done through including the variable in the model as a control. 

### 4. Get an intuition for why conditioning on colliders is bad for causal estimation.

- A -> C <- B, C is the colider in this DAG, A and B independently causes C. Physical attraction and intelligence are reasonably independent, but condition on people with high earning, the two qualities might be positively correlated. People who have both have higher earning. 

### 5. Think about the question: If I want to know the causal effect of X on Y, which variables should I include in my model? Try to think about how the causal criteria in the chapter tell you what variables to include or not include.

**Three types of relationships(?)**

1. Causal: A -> B 
2. Confounding A <- C -> B (omited variable bias)
    - *A and B has no causal association but it appeared to be because of C*
    - example: ambition could cause stress as well as high achivement so it could appear that stress causes high achivement
    - need to condition on C to tease out the true relation between A and B
3. Coliders/Selection Bias A -> C <- B
    - do not include in the model

