# matlab-anonymous-functions
% Define an anonymous function for a cubic polynomial
f = @(x) x.^3 - 6*x.^2 + 11*x - 6; % (x-1)(x-2)(x-3)

% Evaluate at specific points
x_val = 2.5;
result = f(x_val); % Returns 0.125
disp(['f(', num2str(x_val), ') = ', num2str(result)]);

% Plot the function
x = -1:0.1:4;
figure;
plot(x, f(x), 'b-', 'LineWidth', 2);
hold on;
plot(x_val, result, 'ro', 'MarkerSize', 8, 'LineWidth', 2); % Highlight evaluated point
title('Cubic Polynomial: f(x) = x^3 - 6x^2 + 11x - 6');
xlabel('x'); ylabel('f(x)'); grid on;

% Find a root using fzero
root = fzero(f, 1.5); % Start search near x = 1.5
plot(root, 0, 'g*', 'MarkerSize', 10); % Mark root
legend('Function', 'Evaluated Point', 'Root');
disp(['Root found at x = ', num2str(root)]);
