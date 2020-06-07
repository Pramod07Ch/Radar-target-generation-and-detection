# Radar-target-generation-and-detection
This project is a solution for the Radar Module in the Udacity Sensor Fusion Nanodegree
# Goal of the project
- Configure the FMCW waveform based on the system requirements.
- Define the range and velocity of target and simulate its displacement.
- For the same simulation loop process the transmit and receive signal to determine the beat signal
- Perform Range FFT on the received signal to determine the Range
- Towards the end, perform the CFAR processing on the output of 2nd FFT to display the target.
# Determine the Range
plot for range estimtion where range is calculted from the beat frequency for a traget moving at 100m with -10 m/sec
![output1](images/output1.fig)

# 2D FFT 
![output2](images/output2.fig)

# Implementation steps for the 2D CFAR process
- Tr = 12, Td = 10 For both Range and Doppler Training Cells.
- Gr = 4, Gd = 4 For both Range and Doppler Guard Cells.
- offset = 10 the offset value.
- Slide over each cell to be in Cell Under Test (CUT) on whole matix by  loop over training cells and excluding Guard cells from the edges.
- For each iteration we sum the signal level across the training cells and then average is calculated.
- Add offset to threshold and then compare the signal under CUT against this threshold.
- If the CUT is greater than the threshold, assign a value of 1, else to zero.
!ouput3](images/ouput3.fig)
