
# Sensitivity Analysis

Sensitivity analysis is a crucial technique in linear programming for assessing the impact of changes in the coefficients of the objective function or constraints on the optimal solution. This markdown file explores sensitivity analysis in detail, including its principles, methods, and practical applications.

## Introduction

Sensitivity analysis in linear programming involves studying how changes in problem parameters affect the optimal solution and related quantities such as the objective function value and variable values. It provides insights into the stability and robustness of the solution under different scenarios.

## Principles of Sensitivity Analysis

Sensitivity analysis is based on the principle that small changes in problem parameters should result in proportional changes in the optimal solution. It assesses the sensitivity of the optimal solution to variations in coefficients, right-hand sides, or constraint inequalities.

## Methods of Sensitivity Analysis

1. **Shadow Prices (Dual Prices)**: Shadow prices represent the rate of change in the objective function value with respect to a unit change in the right-hand side of a constraint. Positive shadow prices indicate constraints that are binding, while zero shadow prices suggest non-binding constraints.

2. **Reduced Costs**: Reduced costs indicate the rate of change in the objective function value with respect to a unit increase in the coefficient of a decision variable. A negative reduced cost indicates that increasing the variable's coefficient would improve the objective function value.

3. **Range of Optimality**: The range of optimality for a coefficient or right-hand side value represents the range over which the current optimal solution remains optimal. It is determined by calculating the allowable increase or decrease in the parameter value without changing the optimal basis.

## Illustrative Example

Consider a transportation problem where a company aims to minimize transportation costs while satisfying demand and supply constraints. We'll perform sensitivity analysis to assess the impact of changes in transportation costs and demand/supply quantities on the optimal solution.

## Implementation in Programming Languages

Sensitivity analysis can be implemented in programming languages using libraries like PuLP or Pyomo in Python. Below is a Python code snippet demonstrating sensitivity analysis for a linear programming problem using PuLP.

```python
from pulp import LpProblem, LpVariable, LpMinimize

# Define the problem
problem = LpProblem("Sensitivity Analysis", LpMinimize)

# Define decision variables
x = LpVariable("x", lowBound=0)
y = LpVariable("y", lowBound=0)

# Define objective function
problem += 2*x + 3*y

# Define constraints
problem += 3*x + 4*y >= 6
problem += 5*x + 2*y >= 7

# Solve the problem
problem.solve()

# Sensitivity analysis
print("Shadow Price of Constraint 1:", problem.constraints[1].pi)
print("Shadow Price of Constraint 2:", problem.constraints[2].pi)
print("Reduced Cost of Variable x:", x.dj)
print("Reduced Cost of Variable y:", y.dj)
```

## Practical Considerations and Tips

- Conduct sensitivity analysis after obtaining the optimal solution to understand the solution's stability and robustness.
- Interpret shadow prices and reduced costs carefully in the context of the problem domain.
- Perform scenario analysis by considering different parameter values to assess the solution's sensitivity.

## Real-World Applications

Sensitivity analysis finds applications in various fields such as supply chain management, financial planning, and project management. Examples include assessing the impact of changes in demand, resource availability, and market conditions on operational decisions.

## Conclusion

Sensitivity analysis is a valuable tool in linear programming for evaluating the stability and robustness of optimal solutions. By understanding the principles and methods of sensitivity analysis, practitioners can make informed decisions and adapt their solutions to changing circumstances effectively.
