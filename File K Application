import numpy as np
from scipy.optimize import root

# Satellite coordinates (X, Y, Z) in km
sat1 = np.array([0, 0, 6371])
sat2 = np.array([10000, 0, 0])
sat3 = np.array([0, 10000, 0])

# Measured distances to each satellite in km
d1 = 20000
d2 = 15000
d3 = 18000

def gps_equations(p):
    x, y, z = p
    
    # Corrected indices for sat1, sat2, and sat3 across x, y, and z axes
    return [
        (x - sat1[0])**2 + (y - sat1[1])**2 + (z - sat1[2])**2 - d1**2,
        (x - sat2[0])**2 + (y - sat2[1])**2 + (z - sat2[2])**2 - d2**2,
        (x - sat3[0])**2 + (y - sat3[1])**2 + (z - sat3[2])**2 - d3**2
    ]

# Initial guess near the surface of the Earth
initial_guess = [1000, 1000, 1000]

solution = root(gps_equations, initial_guess)

print("Success:", solution.success)
print("Estimated Coordinates (x, y, z):", solution.x)
print("Residual errors:", gps_equations(solution.x))
