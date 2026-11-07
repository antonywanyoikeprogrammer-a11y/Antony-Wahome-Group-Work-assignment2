import numpy as np
from scipy.interpolate import interp1d
import matplotlib.pyplot as plt

time = np.array([0, 10, 20, 30, 40, 50, 60], dtype=float)
speed = np.array([0, 25, 40, 55, 50, 35, 20], dtype=float)

linear = interp1d(time, speed, kind="linear")

# Estimate for every 5 minutes
five_minute_times = np.arange(0, 60 + 5, 5)

linear_estimates = linear(five_minute_times)

# Estimate speed at 25 minutes
target_time = 25

print(
    f"Linear estimate at 25 minutes: "
    f"{float(linear(target_time)):.2f} km/h"
)

# Plot the original measurements
plt.scatter(time, speed, label="Speed measurements")

# Plot the linear interpolation
plt.plot(
    five_minute_times,
    linear_estimates,
    label="Linear interpolation"
)

plt.xlabel("Time (minutes)")
plt.ylabel("Speed (km/h)")
plt.title("Car Speed Linear Interpolation")
plt.legend()
plt.grid(True)
plt.show()
