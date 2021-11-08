Hi. I made a tool that can be useful in some way for the 'sound designers' part :)
It's a command line utility which allows to convert sound spectra into the .h2p
oscillator presets with the 'SpectroBlend' mode. See the attached file.

To use it you need python3 and Wavosaur. Using Wavosaur's spectrum analyser you
can obtain .fft files, which store sound spectra. Then you can run the tool
(the '-f' parameter specifies the fundamental frequency of the spectrum):

	python3 fft_to_h2p.py -i spectrum.fft -o oscillator_preset.h2p -f 440
