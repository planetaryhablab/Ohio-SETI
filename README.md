# Arecibo Wow! Ohio SETI Data

The Ohio SETI project ran from 1973 to 1998 from the Ohio State University Radio Observatory (OSURO), nicknamed Big Ear. It is the longest-running SETI project so far. The [Arecibo Wow!](HTTP:phl.upr.edu/wow) project is transcribing and calibrating its available data from scans of the original computer printouts. The dataset included here has the famous Wow! Signal detected August 15, 1977, around 10 PM EST. It has the original data, as read from the printout, plus corrected B1950 and J2000 coordinates, MJD and LST time, observed frequencies, and flux estimates, among other variables. This reanalysis will be described in the second Arecibo Wow! paper in November 2024.

# Directory Content

- oseti_19770815_220410.jpg - scan of original Wow! Signal printout for reference
- oseti_19770815_220410.txt - original data in TXT format (no header)
- oseti_19770815_220410.csv - original data in CVS format (with header)
- oseti_19770815_220410.extended.pdf - original data in PDF format plus CNT and OBJECT fields (with header)
- oseti_19770815_220410.sav - reanalysis data in IDL Save format (description below)

# Data Format

Data is saved in the IDL Save format. Use [SciPy's `readsave`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.io.readsav.html) to read data into Python.

| Variable | Type | Content | Description |
| -------- | ---- | ------- | ----------- |
| OBSERVATORY | STRING | 'Ohio State University Radio Observatory (OSURO)' | observatory name |
| TELESCOPE   | STRING | 'Big Ear' | telescope name |
| LOCATION    | STRING | 'Delaware, Ohio' | observatory location |
| PROJECT     | STRING | 'Ohio SETI'   | project name |
| OBS_COORD   | DOUBLE | Array[2]      | observatory coordinates |
| Start Date  | STRING | '19770815'    | observation start date |
| Start Time  | STRING | '220410'      | observation start time |
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
| CFREQ_VEL   | DOUBLE | Array[82]     | central frequency velocity (km/s) |
| TIME        | DOUBLE | Array[82]     | time (hours) |
| MJD         | FLOAT  | Array[82]     | Modified Julian Date (days) |
| LST         | DOUBLE | Array[82]     | Local Sidereal Time (hours) |
| CHAN        | LONG   | Array[50]     | channel number |
| SNR         | DOUBLE | Array[50, 82] | signal to noise ratio converted to numbers (50 channels x 82 rows) |
| FLUX        | DOUBLE | Array[50, 82] | estimated flux density (Jy) [assuming max signal was 54 Jy] |
| FREQ_CHAN   | FLOAT  | Array[50, 82] | observed frequency for each channel (MHz) |
| FREQ_CHAN_VEL   | DOUBLE  | Array[50, 82] | observed frequency velocity for each channel (km/s) |
| OBJECT      | STRING | Array[82] | Ohio Sky Survey object in the beam path (beam/peak flux density Jy) |

# Acknowledments

Thanks to MichaelHotaling for the data's original [transcription](https://github.com/MichaelHotaling/The-Wow-Signal).

# Citation

Méndez, A., Ortiz-Ceballos, K., Zuluaga, J. I., & Palencia-Torres, K. D. (2024). Arecibo Wow! II (in preparation).

Méndez, A., Ortiz-Ceballos, K., & Zuluaga, J. I. (2024). Arecibo Wow! I: An Astrophysical Explanation for the Wow! Signal. arXiv preprint [arXiv:2408.08513](https://arxiv.org/abs/2408.08513).

# License

Ohio SETI Data © 2024 by PHL @ UPR Arecibo is licensed under Creative Commons Attribution 4.0 International. To view a copy of this license, visit https://creativecommons.org/licenses/by/4.0/

Contact [abel.mendez@upr.edu](mailto:abel.mendez@upr.edu) for questions or suggestions.

_v0a (October 14, 2024)_
