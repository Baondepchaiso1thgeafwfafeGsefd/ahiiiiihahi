import numpy as np
import matplotlib.pyplot as plt

# Define the circle radius and square side length
r = 1
s = 2

# Calculate the areas
circle_area = np.pi * r**2
square_area = s**2
area_ratio = circle_area / square_area

print(f"The area of the circle is: {circle_area:.2f}")
print(f"The area of the square is: {square_area:.2f}")
print(f"The ratio of the circle area to the square area is: {area_ratio:.4f}")

# Generate 100 random points within the square
num_points = 100
x = np.random.uniform(-1, 1, num_points)
y = np.random.uniform(-1, 1, num_points)

# Count the number of points within the circle
in_circle = (x**2 + y**2) <= r**2
num_in_circle = np.sum(in_circle)

# Calculate the approximate value of pi
pi_approx = 4 * num_in_circle / num_points

print(f"The approximate value of pi is: {pi_approx:.4f}")

# Plot the points
fig, ax = plt.subplots(figsize=(6, 6))
ax.scatter(x, y, s=10, color='blue', alpha=0.5)
circle = plt.Circle((0, 0), r, fill=False, color='red')
ax.add_artist(circle)
ax.set_xlim([-1.1, 1.1])
ax.set_ylim([-1.1, 1.1])
ax.set_aspect('equal')
ax.set_title(f"Approximating Pi Using Probability (Approximate Pi: {pi_approx:.4f})")
plt.show()
