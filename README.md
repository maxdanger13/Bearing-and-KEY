# Bearing-and-KEY
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

