# bms
bms algorithm projects
Course 2 (Equivalent Circuit Cell Model Simulation)
-Acceptable score was achieved after adding extra 1mOhm resistors and 1mF capacitors to the Thevenin Equivalent Circuit.
-The Rint equivalent circuit (resistor only) resulted in unacceptably high voltage rms error (~19 mV)
-R0 and R1 need to be within ~5mOhms of each other
-C1 (third entry in rcValues) at 31mOhms reduced the error significantly to ~7.2 mV.
-Adding more branches (RC) with values of 1mOhm and 1mF respectively, gradually reduced the error to ~5.9 mV.
-Trial and error was used to determine whether any extra branches had a 1mOhm resistor, 1mF capacitor, or both.

Course 3 (Battery State-Of-Charge (SOC) Estimation) Part 1, Part 2
-To tune the EKF and SPKF (extended kalman filter, sigma point kalman filter), I had to modify three covariance values for voltage-sensor, current-sensor noises and initial SOC error
-Very low, but not equal values for SigmaW, SigmaV, and SigmaZ0 reduced the RMS SOC estimation error and SOC estimation error bounds to acceptable values
-SigmaW, SigmaV, and SigmaZ0 had to be similar to each other (0.002, 0.001, 0.002).

Course 4 (Battery State-Of-Health (SOH) Estimation)
-Tuned 3 XLS agorithms (WTLS, TLS, and AWTLS values)
-Normally, high dz values (48) with gamma values of 0.99 (forgetting factor) produced acceptable rms error values
-However, the TLS algorithm tuned with those values above caused some of the data to fall out of the 3-sigma error bounds (not acceptable)
-Tuned TLS to dz=25 and gamma=0.998, then the rms error values were still acceptable but now fell within 3-sigma error bounds.
