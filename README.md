# Arecibo Wow! Ohio SETI Data

The Ohio SETI project, which ran from 1973 to 1998 from the Ohio State University Radio Observatory (OSURO) and nicknamed Big Ear, is the longest-running SETI project so far. [Arecibo Wow!](HTTP:phl.upr.edu/wow) is transcribing and calibrating its available data from scans of the original computer printouts. The dataset included here has the famous Wow! Signal detected August 15, 1977 around 10PM EST. The dataset has the original data, as read from the printout, plus corrected B1950 and J2000 coordinates, MJD and LST time, observed frequencies, and flux estimates, among other variables. A description of this reanalysis will be available in the second Arecibo Wow! paper in November 2024.

# Directory Content

- wow.jpg - scan of original Wow! Signal printout for reference
- oseti.sav - data extracted and calibrated from the printout

# Data Format

Data is saved in IDL Save files. Use [SciPy's `readsave`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.io.readsav.html) to read data into Python. It will be included in other formats (_e.g._, CSV) in future versions.

| Variable | Type | Content | Description |
| -------- | ---- | ------- | ----------- |
| OBSERVATORY | STRING | 'Ohio State University Radio Observatory (OSURO)' | observatory name |
| TELESCOPE   | STRING | 'Big Ear' | telescope name |
| LOCATION    | STRING | 'Delaware, Ohio' | observatory location |
| PROJECT     | STRING | 'Ohio SETI'   | project name |
| OBS_COORD   | DOUBLE | Array[2]      | observatory coordinates |
| TSYS        | DOUBLE | 100.00000     | system temperature (K) |
| OFREQ       | DOUBLE | 1420.4056     | observation frequency (MHz) |
| REFSYS      | STRING | 'LSR'         | reference system |
| DATE        | STRING | Array[82]     | date (YYYY MM DD) |
| RA_PRINT    | STRING | Array[82]     | right ascension from printout (HH MM SS) |
| DC_PRINT    | STRING | Array[82]     | declination from printout (DD MM) |
| FREQ_PRINT  | FLOAT  | Array[82]     | 2nd L.O. frequency from printout (MHz) |
| GLAT_PRINT  | FLOAT  | Array[82]     | galactic latitude from printout (degrees) |
| GLON_PRINT  | FLOAT  | Array[82]     | galactic longitude from printout (degrees) |
| ESTD_PRINT  | STRING | Array[82]     | time from printout (eastern standard time) |
| SNR_PRINT   | STRING | Array[50, 82] | signal to noise ratio from printout (50 channels x 82 rows) |
| RA_1950_DEC | DOUBLE | Array[82]     | corrected right ascension B1950 FK4 (hours) |
| DC_1950_DEC | DOUBLE | Array[82]     | corrected declination B1950 FK4 (degrees) |
| RA_1950_SEX | STRING | Array[82]     | corrected right ascension B1950 FK4 (HH MM SS) |
| DC_1950_SEX | STRING | Array[82]     | corrected declination B1950 FK4 (DD MM SS) |
| RA_2000_DEC | DOUBLE | Array[82]     | corrected right ascension J2000 FK5 (hours) |
| DC_2000_DEC | DOUBLE | Array[82]     | corrected declination J2000 FK5 (degress) |
| RA_2000_SEX | STRING | Array[82]     | corrected right ascension J2000 FK5 (HH MM SS) |
| DC_2000_SEX | STRING | Array[82]     | corrected declination J2000 FK5 (DD MM SS) |
| CFREQ       | DOUBLE | Array[82]     | central frequency (MHz) |         
| TIME        | DOUBLE | Array[82]     | time (hours) |
| MJD         | FLOAT  | Array[82]     | Modified Julian Date (days) |
| LST         | DOUBLE | Array[82]     | Local Sidereal Time (hours) |
| CHAN        | LONG   | Array[50]     | channel number |
| SNR         | DOUBLE | Array[50, 82] | signal to noise ratio converted to numbers (50 channels x 82 rows) |
| FLUX        | DOUBLE | Array[50, 82] | estimated flux density (Jy) [assuming max signal was 54 Jy] |
| FREQ_CHAN   | FLOAT  | Array[50, 82] | observed frequency for each channel (MHz) |

# Acknowledments

Thanks to MichaelHotaling for the data's original [transcription](https://github.com/MichaelHotaling/The-Wow-Signal).

_v0a (October 8, 2024)_
