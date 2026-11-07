from scipy.optimize import root_scalar

# Physical constants for the floating sphere
BALL_RADIUS = 1.0     # 1 meter radius
SPHERE_DENSITY = 0.5  # Density relative to water (0.5 means it floats halfway)

def buoyancy_volume(x):
    """
    The function f(x) derived from Archimedes' principle.
    We want to find where f(x) = 0.
    """
    return x**3 - 3 * BALL_RADIUS * x**2 + 4 * BALL_RADIUS**3 * SPHERE_DENSITY

def d_buoyancy_volume(x):
    """
    The derivative f'(x) used by Newton-Raphson to find the slope.
    Derivative of (x^3 - 3x^2 + 2) is (3x^2 - 6x).
    """
    return 3 * x**2 - 6 * BALL_RADIUS * x
 
# Newton-Raphson Method
# We start with an initial guess (x0) of 0.8 meters deep.
sphere_depth = root_scalar(
    buoyancy_volume,
    fprime=d_buoyancy_volume,
    x0=0.8,
    method="newton",
    xtol=1e-12
)

# Output results
print(f"Floating depth using Newton-Raphson: {sphere_depth.root:.6f} meters")
print(f"Function balance at solution: {buoyancy_volume(sphere_depth.root):.6f}")
