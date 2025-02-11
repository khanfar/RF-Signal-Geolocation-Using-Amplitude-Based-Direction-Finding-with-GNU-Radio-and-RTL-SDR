Project Title
"RF Signal Geolocation Using Amplitude-Based Direction Finding with GNU Radio and RTL-SDR"



1. Project Overview
The goal of this project is to locate the position of an RF emitter by analyzing the amplitude of received signals across multiple directional antennas. This will involve:

Capturing RF signals using four RTL-SDR dongles.

Processing the signals in GNU Radio to estimate the direction of arrival (DOA).

Visualizing the results using polar plots and maps.

Intersecting lines of bearing (LOBs) to determine the emitter's location.

This project demonstrates practical applications of software-defined radio (SDR), signal processing, and geolocation techniques.

2. Project Objectives
   
Learn Signal Processing : Gain hands-on experience with GNU Radio and RTL-SDR.

Implement Direction Finding : Use amplitude-based techniques to estimate the DOA of an RF signal.

Visualize Results : Create polar plots and map visualizations to display LOBs and geolocation results.

Demonstrate Real-World Application : Showcase how this system can be used for locating RF emitters in fields like search-and-rescue, spectrum monitoring, or security.

4. Tools and Materials
   
Hardware:

4x RTL-SDR dongles

4x Directional antennas (e.g., Yagi antennas)

Laptop or PC with GNU Radio installed

GPS module (optional, for precise location data)

Software:

GNU Radio Companion (GRC)

Python (with libraries: numpy, matplotlib, folium)
Mapping tools (e.g., Google Maps API or OpenStreetMap)

6. Step-by-Step Plan
   
Phase 1: Setup and Calibration

Hardware Setup :

Arrange two arrays of directional antennas at known locations.

Connect each antenna to an RTL-SDR dongle.

Ensure all RTL-SDRs are synchronized (use GPS or manual time alignment if needed).

Calibration :
Test each antenna to ensure consistent gain and directivity.

Calibrate the system by capturing a known RF signal (e.g., from a test transmitter).

Phase 2: Signal Capture and Processing
GNU Radio Flowgraph :

Design a flowgraph to capture IQ samples from all four RTL-SDRs.

Compute the amplitude (RSS) for each channel.

Export amplitude data to Python for further analysis.

Direction Finding :
Analyze amplitude differences between antennas in each array.

Estimate the DOA using amplitude-based algorithms (e.g., beamforming or phase comparison).
Phase 3: Visualization

Polar Plot :
Use matplotlib to create a polar plot showing amplitude vs. bearing.

Highlight peaks corresponding to LOBs.
Map Visualization :

Use folium to plot the LOBs on a map.

Mark the intersection point as the estimated location of the RF emitter.

Phase 4: Testing and Validation

Test with Known Transmitter :
Place a test RF transmitter at a known location.

Run the system and compare the estimated location with the actual location.

Refine Results :
Adjust for multipath effects and noise.

Improve accuracy by averaging multiple measurements.

8. Presentation Outline
   
Slide 1: Title Slide

Title: "RF Signal Geolocation Using Amplitude-Based Direction Finding"


Slide 2: Introduction



Why is it important? (Applications in search-and-rescue, spectrum monitoring, etc.)
Introduce your project goals.
Slide 3: System Overview

Diagram showing the setup:

Two arrays of directional antennas.

RTL-SDR dongles connected to a laptop.

Signal processing in GNU Radio.

Explain the role of each component.

Slide 4: Methodology

Describe the process:
Capture RF signals using RTL-SDR.

Analyze amplitude differences to estimate DOA.

Visualize results using polar plots and maps.

Include a simplified flowchart of the workflow.

Slide 5: GNU Radio Flowgraph

Show a screenshot of your GNU Radio flowgraph.

Highlight key blocks:

RTL-SDR Source

FFT Block
Amplitude Calculation
Data Export to Python
Slide 6: Polar Plot
Display a sample polar plot showing amplitude vs. bearing.
Explain how peaks correspond to LOBs.
Slide 7: Map Visualization
Show a map with two LOBs intersecting at the estimated location.
Compare the estimated location with the actual location of the test transmitter.
Slide 8: Challenges and Solutions
Discuss challenges you faced (e.g., synchronization, multipath effects).
Explain how you addressed them.
Slide 9: Results and Accuracy
Present the accuracy of your system (e.g., error margin in meters).
Show before-and-after results after refining the system.
Slide 10: Conclusion
Summarize what you learned from the project.
Highlight potential improvements (e.g., using phase-based methods, adding more antennas).
Mention future applications of your system.
Slide 11: Questions
Invite questions from the audience.
10. Deliverables
Working Prototype :
A fully functional system that can locate an RF emitter.
Presentation Slides :
A polished PowerPoint or PDF presentation summarizing your project.
Documentation :
Write a short report detailing your methodology, results, and lessons learned.
Code and Flowgraphs :
Share your GNU Radio flowgraph and Python scripts for visualization.
11. Timeline
Here’s a suggested timeline for completing the project:

Week 1
Research and gather materials. Set up hardware.
Week 2
Design and test GNU Radio flowgraph.
Week 3
Implement amplitude-based direction finding.
Week 4
Develop polar plot and map visualization.
Week 5
Test with a known transmitter and refine results.
Week 6
Prepare presentation and documentation.




----------------------------------------





1. Overview of the Geolocation Process
The goal is to determine the location of an RF emitter by:

Using two or more directional antenna arrays to calculate the direction of arrival (DOA) of the RF signal.

Visualizing the amplitude response at different bearings using polar plots.

Intersecting the calculated LOBs on a map to pinpoint the emitter's location.

2. Required Components
Hardware:
RTL-SDR Dongles : Four RTL-SDR receivers are needed to capture the RF signals.

Directional Antennas : Use directional antennas (e.g., Yagi antennas) for each RTL-SDR to provide spatial selectivity.

Antenna Mounting Setup : Arrange the antennas in two arrays (e.g., one array for azimuth and another for elevation or two separate locations).

GPS Module : Optional, for synchronizing time and location data between the arrays.

Software:
GNU Radio : For signal processing and visualization.

Python/PyQt/Plotly : For creating polar plots and maps.

Mapping Tools : Libraries like folium or matplotlib for displaying geolocation results on a map.

4. Steps to Implement
5. 
Step 1: Signal Capture with RTL-SDR

Connect each RTL-SDR to a directional antenna.

Configure the RTL-SDRs to capture signals at the same frequency and bandwidth.

Use GNU Radio to synchronize the sampling and ensure all receivers are tuned to the same RF signal.
Step 2: Amplitude-Based Direction Finding

Measure the received signal strength (RSS) at each antenna.

Compare the amplitude differences between the antennas in each array to estimate the DOA.

Use algorithms like:

Beamforming : Combine signals from multiple antennas to enhance the signal in a specific direction.

Phase Comparison : If phase information is available, use it to refine the DOA estimation.

Step 3: Polar Plot Visualization

Create a polar plot to display the amplitude response as a function of bearing.

Each peak in the polar plot corresponds to a potential line of bearing (LOB).

Step 4: Calculate Lines of Bearing

For each array, calculate the LOB based on the DOA.

Use trigonometry to convert the DOA into geographic coordinates (latitude and longitude).

Step 5: Geolocation on a Map

Plot the LOBs from both arrays on a map.

The intersection of the LOBs provides the estimated location of the RF emitter.

7. Implementation in GNU Radio

Signal Processing Flowgraph:

Signal Source :

Use four RTL-SDR blocks to capture the RF signals.

Amplitude Measurement :

Compute the RSS for each channel using magnitude or power calculations.

Direction Finding :

Use custom blocks or Python scripts to analyze the amplitude differences and estimate DOA.

Polar Plot :

Export the amplitude data to a Python script for visualization using libraries like matplotlib.

Example Blocks in GNU Radio:

RTL-SDR Source : Capture raw IQ samples from each SDR.

FFT Block : Perform spectral analysis to identify the signal of interest.

Complex to Mag^2 : Convert IQ samples to amplitude/power values.

Custom Python Block : Process amplitude data to calculate DOA and generate polar plots.

9. Visualization
    
Polar Plot:

Use matplotlib to create a polar plot showing amplitude vs. bearing.

Highlight the peaks corresponding to the LOBs.

Map Visualization:

Use folium or plotly to plot the LOBs on a map.

Mark the intersection point as the estimated location of the RF emitter.

11. Challenges and Considerations

Synchronization :

Ensure that all RTL-SDRs are synchronized in time and frequency. This can be challenging without external hardware.

Antenna Calibration :

Calibrate the antennas to account for differences in gain and directivity.

Multipath Effects :

Multipath propagation can distort the amplitude measurements, leading to inaccurate DOA estimates.

Signal-to-Noise Ratio (SNR) :

Ensure sufficient SNR to reliably detect the RF signal.

13. Example Workflow
14. 
Set up two arrays of directional antennas at known locations.

Capture RF signals using GNU Radio and RTL-SDR.

Analyze amplitude differences to estimate DOA for each array.

Generate polar plots to visualize the LOBs.

Plot the LOBs on a map and calculate their intersection.

Refine the location estimate using additional data (e.g., GPS coordinates of the arrays).

16. Tools and Libraries

GNU Radio : Core framework for signal processing.

Python Libraries :

numpy: For numerical computations.

matplotlib: For polar plots.

folium or plotly: For map visualization.

RTL-SDR Tools : rtl_sdr, gr-osmosdr for interfacing with RTL-SDR.

18. Conclusion
    
By combining GNU Radio, RTL-SDR, and directional antennas, you can build a system for geolocating RF signals using amplitude-based direction finding. 

The key steps involve signal capture, amplitude analysis, DOA estimation, and visualization. While the setup has some challenges (e.g., synchronization and calibration), 

it is a feasible project with careful planning and implementation.


-------------------------------------



Basic Workflow

Capture raw IQ samples from the RTL-SDR.

Process the samples (e.g., compute amplitude, filter noise, or perform FFT).

Analyze the processed data to extract useful information (e.g., amplitude differences for DOA estimation).

Export the results for visualization or further analysis.


Step 1: Add RTL-SDR Source Blocks

Drag four RTL-SDR Source blocks onto the canvas.

Set the following parameters for each block:

Sample Rate : 2 MHz (or lower, depending on your system).

Center Frequency : Set to the frequency of interest (e.g., 433 MHz for ISM band).

Gain : Adjust based on your antenna setup (start with 30 dB).

Device Index : Assign unique indices (0, 1, 2, 3) to differentiate the RTL-SDRs.

Step 2: Compute Amplitude

For each RTL-SDR Source, add a Complex to Mag^2 block:

This converts IQ samples to amplitude squared (proportional to power).

Add a Moving Average block after each Complex to Mag^2 block:

Smooth the amplitude data to reduce noise.

Set the length to a reasonable value (e.g., 1000 samples).

Step 3: Combine Data

Use a Stream to Vector block to combine the amplitude data from all four channels into a single vector.

This allows you to process all channels together.

Step 4: Export Data

Add a File Sink block to save the processed data to a file.

Choose a .dat or .csv format for easy import into Python.

Alternatively, use a Message Debug block to print the data to the terminal for debugging.

Step 5: Visualize in Real-Time (Optional)

Add a QT GUI Time Sink block to visualize the amplitude over time.

Connect it to the output of each Moving Average block.

Step 6: Run the Flowgraph

Save your flowgraph and click the Execute button (green play icon).

Verify that the RTL-SDRs are capturing data and the amplitude is being computed correctly.

4. Prototype Output
   
The flowgraph will produce:

Raw amplitude data for each channel (saved to a file or printed to the terminal).

A real-time plot of amplitude vs. time (if using QT GUI Time Sink).

This data can then be analyzed in Python to estimate the DOA and generate polar plots.

5. Next Steps
   
then , you can expand it to include:

FFT Analysis : Add an FFT Sink block to analyze the frequency spectrum.

Direction Finding : Implement amplitude-based algorithms (e.g., beamforming) in Python.

Polar Plot Visualization : Export amplitude data to Python and use matplotlib to create polar plots.

Map Integration : Use folium or plotly to plot LOBs and geolocate the emitter.

Here’s a simplified layout of the flowgraph:

[RTL-SDR Source 1] --> [Complex to Mag^2] --> [Moving Average] --> [Stream to Vector]

[RTL-SDR Source 2] --> [Complex to Mag^2] --> [Moving Average] --> [Stream to Vector]

[RTL-SDR Source 3] --> [Complex to Mag^2] --> [Moving Average] --> [Stream to Vector]

[RTL-SDR Source 4] --> [Complex to Mag^2] --> [Moving Average] --> [Stream to Vector]

[Stream to Vector] --> [File Sink / Message Debug]

Python Libraries :

numpy: For numerical computations.

matplotlib: For polar plots.

folium: For map visualization.

-----------------------------------------------------

Step-by-Step Block Connections

1. RTL-SDR Source Blocks

Add four RTL-SDR Source blocks to the canvas.

Configure each block as follows:
Sample Rate : Set to 2e6 (2 MHz) or lower if needed.
Center Frequency : Set to the frequency of interest (e.g., 433e6 for the ISM band).
Gain : Start with 30 dB and adjust based on your setup.
Device Index : Assign unique indices (0, 1, 2, 3) to differentiate the RTL-SDRs.

3. Complex to Mag^2 Blocks
4. 
Add a Complex to Mag^2 block after each RTL-SDR Source.
This block converts IQ samples into amplitude squared (proportional to power).
Connect the output of each RTL-SDR Source to its corresponding Complex to Mag^2 block .

6. Moving Average Blocks
Add a Moving Average block after each Complex to Mag^2 block .
This block smooths the amplitude data to reduce noise.
Set the Length parameter to a reasonable value (e.g., 1000 samples).
Connect the output of each Complex to Mag^2 block to its corresponding Moving Average block .

8. Stream to Vector Block
   
Add a Stream to Vector block to combine the amplitude data from all four channels.
Set the Vector Length parameter to 4 (one value for each channel).
Connect the outputs of all four Moving Average blocks to the inputs of the Stream to Vector block .

10. File Sink or Message Debug
    
Add a File Sink block or Message Debug block to save or display the processed data.
File Sink : Save the data to a file (e.g., .dat or .csv) for further analysis in Python.
Set the File Path to a location on your system.
Message Debug : Print the data to the terminal for debugging.
Connect the output of the Stream to Vector block to the input of the File Sink or Message Debug block .

12. Optional: QT GUI Time Sink
    
If you want to visualize the amplitude in real-time, add a QT GUI Time Sink block .
Connect the output of each Moving Average block to a separate input of the QT GUI Time Sink block .
Set the number of inputs to 4 (one for each channel).



Explanation of Each Block
RTL-SDR Source :
Captures raw IQ samples from the RTL-SDR dongle.
Acts as the input source for the flowgraph.

Complex to Mag^2 :
Converts complex IQ samples into amplitude squared (power).
Simplifies the signal for amplitude-based analysis.

Moving Average :
Smooths the amplitude data to reduce noise.
Improves the accuracy of amplitude measurements.

Stream to Vector :
Combines the amplitude data from all four channels into a single vector.
Allows you to process all channels together.

File Sink / Message Debug :
Saves the processed data to a file or prints it to the terminal.
Provides output for further analysis in Python.

QT GUI Time Sink (Optional) :
Visualizes the amplitude over time in real-time.
Helps debug and verify the system.


Inspect Output :

Check the output file or terminal for amplitude data.
Use the QT GUI Time Sink to visualize the amplitude in real-time.

Next Steps
Once the flowgraph is working:

Export the amplitude data to Python for further analysis.

Implement amplitude-based direction finding algorithms to estimate DOA.

Generate polar plots and map visualizations to locate the RF emitter.

----------------------------------------

Recommended Antennas for my Project
For amplitude-based direction finding, Yagi-Uda antennas are the most practical choice due to their high gain and narrow beamwidth. Here’s how you can set them up:

Setup for Two Arrays

Array 1 :

Use two Yagi antennas mounted back-to-back or side-by-side.

Arrange them to cover different azimuth angles (e.g., 0° and 90°).

Array 2 :

Repeat the setup at a second location, spaced apart from Array 1.

Ensure both arrays are synchronized and calibrated.

Frequency-Specific Recommendations

433 MHz (ISM Band) : Use a Yagi antenna tuned to 433 MHz.

2.4 GHz (Wi-Fi) : Use a patch antenna or a small Yagi for 2.4 GHz.

900 MHz (Cellular/GSM) : Use a Yagi or log-periodic antenna.

Yagi-Uda Antenna

Description : A highly directional antenna with multiple elements (reflector, driven element, and directors).

Frequency Range : Typically used for HF, VHF, and UHF bands (e.g., 144 MHz, 433 MHz, 900 MHz).

Applications :

Amateur radio.

ISM band (e.g., 433 MHz for IoT devices).

Direction finding and geolocation.

Advantages :

High gain and narrow beamwidth.

Easy to build or purchase.

Example Use Case : If you're working with 433 MHz signals, a Yagi antenna tuned to this frequency would be ideal.


 Additional Considerations
 
Antenna Gain : Higher gain antennas provide better sensitivity but have narrower beamwidths.

Polarization : Match the polarization of the antenna to the signal source (e.g., vertical for most terrestrial signals).

Calibration : Calibrate the antennas to ensure consistent performance across all channels.

