(1)

clc;
clear;
close all;

% SNR values (dB)
snr_dB = 0:2:30;

% LTE Bandwidths (MHz)
bandwidth = [5 10 20];

figure;
hold on;
grid on;

for i = 1:length(bandwidth)

    BW = bandwidth(i);

    % Convert SNR to linear scale
    snr = 10.^(snr_dB/10);

    % Shannon Capacity Formula
    throughput = BW .* log2(1 + snr);

    plot(snr_dB, throughput, 'LineWidth',2);

end

xlabel('SNR (dB)');
ylabel('Throughput (Mbps)');
title('LTE Throughput Performance');

legend('5 MHz','10 MHz','20 MHz','Location','northwest');


<img width="1914" height="745" alt="Image" src="https://github.com/user-attachments/assets/9d32ac72-b589-4763-96a4-bed9d10d7ebe" />




(2)

clc;
clear;
close all;

Technology = categorical({'LTE','5G NR'});

Throughput = [150 450];
Latency = [15 1];
SpectralEfficiency = [4 9];

figure;

subplot(3,1,1)
bar(Technology,Throughput)
title('Throughput Comparison')
ylabel('Mbps')
grid on

subplot(3,1,2)
bar(Technology,Latency)
title('Latency Comparison')
ylabel('ms')
grid on

subplot(3,1,3)
bar(Technology,SpectralEfficiency)
title('Spectral Efficiency')
ylabel('Bits/s/Hz')
grid on


<img width="1909" height="753" alt="Image" src="https://github.com/user-attachments/assets/63f78e24-5c04-4f00-828f-d2be8fd88732" />
