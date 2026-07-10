import numpy as np

f, n = map(int, input().split())

train = np.array([list(map(float, input().split())) for _ in range(n)])

x = train[:, :-1]
y = train[:, -1]

# Add intercept column
design = np.concatenate((np.ones((n, 1)), x), axis=1)

# Compute weights
weights = np.linalg.pinv(design.T @ design) @ design.T @ y

t = int(input())

for _ in range(t):
    sample = np.array([1.0] + list(map(float, input().split())))
    prediction = sample @ weights
    print(f"{prediction:.2f}")
