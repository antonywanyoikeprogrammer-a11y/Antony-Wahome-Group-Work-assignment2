import numpy as np
# Four corners of a square:c each row is [x, y]
points = np.array([
[0.0, 0.0],
[1.0, 0.0],
[1.0, 1.0],
[0.0, 1.0]
])
print("Original points:\n", points) 
angle = np.deg2rad(45)
rotation = np.array([
[np.cos(angle), -np.sin(angle)],
[np.sin(angle), np.cos(angle)]
])
print("rotation:\n", rotation)
scale = np.array([
[2.0, 0.0],
   [0.0, 1.5] ]) 
print("scale:\n",scale)
transformation = rotation @ scale 
print("Transformation matrix:\n", transformation) 
transformed_points = points @ transformation
print("Transformed points:\n", transformed_points)
