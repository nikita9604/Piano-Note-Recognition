## Piano Note Recognition Software using [MATLAB](https://www.mathworks.com/products/matlab.html)

In this, we designed and implemented an effective and user-friendly musical note recognition software using MATLAB which can identify the exact note by finding the frequency of the input note. This project is implemented by using Fourier Analysis, Windowing technique to seperate and match the note as per the given one, along with plotting of the note in the graph in time and frequency domain.

### Design

The musical piece is fed to the system which processes the audio signal. The frequency and pitch of the signal is determined thereby identifying the type of musical note by comparing it with the standard musical notes available.

### Software Analysis

There are 6 stages involved :

1. The input is the sequence of desired musical note (digitally recorded) whose frequency is to be found.

2. The signal is analyzed using Matlab. The series of notes are initially plotted in the time domain.

3. We designed a <B>Windowing Technique</B> that determines the window of each note in the sequence. This technique first involved a method to determine when a note begins and ends. The program takes in a double array specified by the data and outputs a vector of division points that correspond to separate and distinct notes. In other words, trying to find when one note stops and another starts. The returned vector will include the midpoint of the end of note and the beginning of the next. It can be easily noticed in a note sequence that there is a visible drop in energy between notes i.e. a small gap from one note to another note. This fact is used in determining the actual window of a note.

4.  The analysis of the signal in the frequency domain is done here. Now as that the windows of each note have been determined in the step above mentioned, each individual note is converted to the frequency domain. Hence, here comes the application of fast fourier series to get the frequency domain of our input signal. <I>(The <B>Fast Fourier Transform (FFT)</B> is a discrete Fourier transform algorithm which reduces the number of computations needed for points from to , where log is the base-2 logarithm.)</I>

5. The <B>Fundamental Frequency</B> of each note is identified in this step. <I>(A standard musical note played by standard instruments is described by a fundamental frequency, which is the maximum frequency, along with other smaller harmonics)</I>. Therefore, to determine the fundamental frequency, we find the maximum frequency for each signal.

6. Now to determine the actual note, we find the pitch of the note using the method mentioned below. Based on the frequency of the pitches, the program determines whether the input frequency is above or below this range.

  - Frequency < Middle C octave range - It multiplies the input frequency by 2, adds one to a counter that keeps track of how many times the process has recurred and then calls the process on the input frequency times 2.

  - Frequency > Middle C octave range - It divides the input frequency by 2 and goes through the same process but now it divides by 2 instead of multiplying.

  - Frequency ~ Middle C octave range - It determines what pitch it is based on some accepted ranges/values for pitches and return the pitch. Finally, the program returns the pitch and the octave above or below the middle C octave. (Positive for octaves above, negative for octaves below).

### Conclusion

We sccessfully designed and implemented an effective and user-friendly frequency estimation system with Fourier Analysis. The target users of the system are not only the people practicing music, but also professional musicians who cannot waste their time figuring out the notes of an audio sample.
