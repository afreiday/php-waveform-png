PHP MP3 PNG Waveform Generator
===

### About

Generates PNG waveform images for a given MP3 file by converting it to WAV and processing amplitude points and plotting them on a GD canvas.

This code was adapted by [Andrew Freiday](http://andrewfreiday.com).

### Requirements

	- PHP 5+
	- LAME MP3 Encoder (Windows build available [here](http://www.rarewares.org/mp3-lame-bundle.php))
	- Web server (Apache, etc -- unless modified to run as a command line script)

### Usage/Installation

	- Copy to a location on your web server
	- Ensure that the 'lame' command is accessible and executable from that directory (for Windows systems, place the downloaded .exe and .dll as linked above into that same directory, or modify the script)
	- Ensure the directory support write persmissions, or specify an alternate temporary output directory that does
	- Launch the script in your browser (e.g. http://localhost/php-waveform-png.php) and upload your MP3 file along with a selection of output settings (dimensions, colours, etc)

### Other notes

The detail of the waveform can be adjusted by modifying the DETAIL constant at the top of the script. The lower the number, the less data points are skipped, thus resulting in higher detail waveform.

The most time-consuming factor of the script is the LAME encoder, which first converts the uploaded MP3 into a 16 bit, mono, 8 KHz MP3 and finally to a WAV audio file. Unfortunately this doesn't seem to be possible to perform this in one step with the LAME encoder. If this script is to be modified to generate waveforms on the fly for the same MP3 multiple times, I recommend either storing a copy of the final WAV file or modifying the script to keep a dataset of the amplitude points so that the waveform can be redrawn much more quickly.

### License

Please see the LICENSE file.