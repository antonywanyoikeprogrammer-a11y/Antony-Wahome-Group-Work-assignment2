import numpy as np
from scipy.optimize import root

# Find intersections of:
# Circle: x^2 + y^2 = 4
# Parabola: y = x^2 - 1
def equations(z):
    x, y = z
    return [
        x**2 + y**2 - 4,
        y - (x**2 - 1)
    ]

# Define your initial guess and solve (hidden under the tooltip)
guess = [1, 1] 
solution = root(equations, guess)

print("Initial guess:", guess)
print("Intersection:", solution.x)
print("Residuals:", equations(solution.x))
print("Converged:", solution.success)
print()
