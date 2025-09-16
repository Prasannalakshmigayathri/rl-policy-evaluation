# POLICY EVALUATION

## AIM
To develop a Python program to create our own policy, evaluate and compare it with the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.

## POLICY EVALUATION FUNCTION


```
Reg no: 212222240075
Developed By: Prasannalakshmi G

```
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy

    while True:
        delta = 0
        for s in range(len(P)):
            a = pi[s] if isinstance(pi, dict) else pi(s)
            v = 0
            for prob, next_state, reward, done in P[s][a]:
                v += prob * (reward + gamma * prev_V[next_state])
            delta = max(delta, abs(v - V[s]))
            prev_V[s] = v
        if delta < theta:
            break
    
    return prev_V
```

## OUTPUT:

<img width="847" height="610" alt="image" src="https://github.com/user-attachments/assets/903ccfb8-52c5-4675-b4b6-47f914fe929c" />

<img width="965" height="144" alt="image" src="https://github.com/user-attachments/assets/3afdfbff-b40f-474a-82a4-8f864634f750" />

<img width="702" height="681" alt="image" src="https://github.com/user-attachments/assets/d5b1b963-514c-4002-8f96-35fed1e1686f" />

<img width="881" height="214" alt="image" src="https://github.com/user-attachments/assets/63199ae3-db1a-4c00-9b41-c567fec230de" />

<img width="701" height="208" alt="image" src="https://github.com/user-attachments/assets/64b2111e-9b27-4a4f-8377-d898375ba6d7" />

<img width="627" height="303" alt="image" src="https://github.com/user-attachments/assets/439a998b-28a2-4333-b183-08b0d10eb44c" />

<img width="818" height="235" alt="image" src="https://github.com/user-attachments/assets/9a43334c-d7a8-41de-9c7d-1dfd01bfa698" />

<img width="562" height="232" alt="image" src="https://github.com/user-attachments/assets/3635cad3-d867-48a1-956a-8c3b1a71c616" />



## RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.
