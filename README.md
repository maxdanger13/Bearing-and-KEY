# Bearing-and-KEY
The code below is for a bearing in matlab
% Input values
F = input('Enter applied load (N): ');
L = input('Enter bearing span (mm): ');
n = input('Enter rotational speed (rpm): ');
Sf = input('Enter safety factor: ');

% Constants
C0 = input('Enter basic static load rating (N): '); % Basic static load rating
Cr = input('Enter basic dynamic load rating (N): '); % Basic dynamic load rating
e = 0.4; % Bearing constant
kf = 1; % Load factor
kfkr = 1; % Combined load factor
k = 1; % Other factors (e.g. lubrication, temperature)

% Calculation of bearing dimensions
P = F / (L * kf * kfkr); % Equivalent dynamic load
Fr = P / e; % Equivalent radial load
Fa = P; % Equivalent axial load
X = (Cr / (kf * kfkr * P))^0.3333; % Equivalent dynamic load rating factor
Y = (C0 / (kf * kfkr * P))^0.3333; % Equivalent static load rating factor
C = X * Cr; % Equivalent dynamic load rating
Co = Y * C0; % Equivalent static load rating
d = ((60 * n * L * kf * kfkr * k * Sf) / (C * pi))^0.5; % Minimum required bearing diameter

% Display results
fprintf('Minimum required bearing dimensions:\n')
fprintf('Diameter of bearing = %.2f mm\n', d)

The code below ia for a key in matlab
% Input values
T = input('Enter torque (N-m): ');
P = input('Enter power (W): ');
N = input('Enter rotational speed (rpm): ');
Sf = input('Enter safety factor: ');
b = input('Enter width of key (mm): ');
% Calculation of key dimensions
d = (2*T/(Sf*b))^0.3333; % Diameter of key
h = 2*d; % Height of key
% Display results
fprintf('Minimum required key dimensions:\n')
fprintf('Diameter of key = %.2f mm\n', d)
fprintf('Height of key = %.2f mm\n', h)

code for bearing in python
import math

# Input values
F = float(input("Enter applied load (N): "))
L = float(input("Enter bearing span (mm): "))
n = float(input("Enter rotational speed (rpm): "))
Sf = float(input("Enter safety factor: "))

# Constants
C0 = float(input("Enter basic static load rating (N): ")) # Basic static load rating
Cr = float(input("Enter basic dynamic load rating (N): ")) # Basic dynamic load rating
e = 0.4 # Bearing constant
kf = 1 # Load factor
kfkr = 1 # Combined load factor
k = 1 # Other factors (e.g. lubrication, temperature)

# Calculation of bearing dimensions
P = F / (L * kf * kfkr) # Equivalent dynamic load
Fr = P / e # Equivalent radial load
Fa = P # Equivalent axial load
X = (Cr / (kf * kfkr * P))**(1/3) # Equivalent dynamic load rating factor
Y = (C0 / (kf * kfkr * P))**(1/3) # Equivalent static load rating factor
C = X * Cr # Equivalent dynamic load rating
Co = Y * C0 # Equivalent static load rating
d = math.sqrt((60 * n * L * kf * kfkr * k * Sf) / (C * math.pi)) # Minimum required bearing diameter

# Display results
print("Minimum required bearing dimensions:")
print("Diameter of bearing = {:.2f} mm".format(d))






Code for key in python
import math

# Input values
T = float(input("Enter torque (N-m): "))
P = float(input("Enter power (W): "))
N = float(input("Enter rotational speed (rpm): "))
Sf = float(input("Enter safety factor: "))
b = float(input("Enter width of key (mm): "))

# Calculation of key dimensions
d = (2 * T / (Sf * b))**(1/3) # Diameter of key
h = 2 * d # Height of key

# Display results
print("Minimum required key dimensions:")
print("Diameter of key = {:.2f} mm".format(d))
print("Height of key = {:.2f} mm".format(h))
