% NAME: Aleksandra Kłos

%% TOPIC: Quantum Electron Orbitals (2D animation)
% Visualising electron orbitals in atoms, helping to show the quantum 
% behavior of electrons
% According to quantum physics theory, the particles can behave as a wave 
% Thus, I will present them in this manner 

%% SOURCES: 
% https://edtechbooks.org/general_college_chemistry/orbitals_quantum_numbers
% https://www.cond-mat.de/teaching/QM/JSim/wpack.html
% https://en.wikipedia.org/wiki/Wave_packet

%% CODE 

% parameters for the first orbital
sigma1 = 1;   % wave packet width (width of Gaussian wave packet - bigger value: wider wave packet)
k01 = 2;      % initial wave vector (controls initial momentum of wave packet)
x0_1 = -5;    % initial position (determines where wave packets are located in space)

% parameters for the second orbital
k02 = -2;     % initial wave vector (controls initial momentum of wave packet)
x0_2 = 5;     % initial position (determines where wave packets are located in space)

% creating a grid
x = linspace(-10, 10, 300); % plotting line orbitals
t = linspace(0, 10, 300); % time values

% initialising the figure
figure;

for ti = 1:length(t) % calculating wave packets at time t(ti)

    % (x - x0) - k * t(ti) --> displacement of the wave packet in time and space in x-axis
    % ((x - x0) - k * t(ti)).^2 --> square of displacement - measures the distance from the center of the wave packet
    % 2 * sigma^2 --> controls the width of the wave packet (smaller sigma, narrower and more localized wave packet)
    % 1i * k * (x - x0) --> phase factor that introduces a time-dependent phase to the wave packet - responsible for the wave packet's motion in time and space
    % 1i -> imaginary unit  k --> wave vector (determines spatial frequency)  (x - x0) --> spatial position  t(ti) --> time

    psi1 = exp(-((x - x0_1) - k01 * t(ti)).^2 / (2 * sigma1^2) + 1i * k01 * (x - x0_1)); % 1st orbital wavepacket

    % time-dependent variation for the red orbital (2nd orbital)
    sigma2 = 0.5 + 0.2 * sin(2 * pi * t(ti)); % vary the width with time
    x0_2 = 5 + 2 * sin(2 * pi * t(ti));      % vary the initial position with time

    psi2 = exp(-((x - x0_2) - k02 * t(ti)).^2 / (2 * sigma2^2) + 1i * k02 * (x - x0_2)); % 2nd orbital wavepacket

    % combining wave packets - to create the total wave function
    psi = psi1 + psi2;

    % plotting the absolute squared value of the wave function - Probability Density of the wave functions
    plot(x, abs(psi).^2, 'b');
    hold on;
    plot(x, abs(psi2).^2, 'r');
    title(['Time = ', num2str(t(ti))]);
    xlabel('Position (x)');
    ylabel('Probability Density (|ψ(t,x)|2)');
    xlim([-10, 10]);
    ylim([0, 1]);

    % adding a legend
    legend('Orbital 1', 'Orbital 2');

    % pausing to create the animation effect
    pause(0.2);

    if ti < length(t) % if the current frame is not the last frame
        clf; % clearing the figure for the next frame
    end
end
