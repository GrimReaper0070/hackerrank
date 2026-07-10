physics = [15, 12, 8, 8, 7, 7, 7, 6, 5, 3]
history = [10, 25, 17, 11, 13, 17, 20, 13, 9, 15]

n = len(physics)

mean_x = sum(physics) / n
mean_y = sum(history) / n

num = 0.0
den = 0.0

for x, y in zip(physics, history):
    dx = x - mean_x
    num += dx * (y - mean_y)
    den += dx * dx

slope = num / den

print(f"{slope:.3f}")
