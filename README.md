"# MusicLabCopenhegan_MotionAlignment" 
Repo to organise and align the MusicLab mobile app recordings from the MusicLab Copenhagen concert experiment with the DSQ. The app recorded accelerometer, gyroscope, and geolocation data as permited, bundled into one minute segments and gathered on the Nettskjema research questionnaire platform. 

Participants were either in the live concert hall with the performers and remotely watching over livestream, so their responses are organised into two sets: Hall and Remote. Though some sensor recordings were collected by the app long before and after the performance, this dataset focuses on the data collected from around the intended concert starttime (2021-10-26 17:30:00) to a half hour after concert end (2021-10-26 20:30:00 in UTC 0). Only devices that can be associated with inperson participant codes are included in the Hall data set. Only recordings with locations outside of the Copenhagen hall are included in the Remote datasets, as assessed on the geolocation data with original accuracy. The resultant aligned dataset of Hall and Remote only include those device recordings that included at least one descernable sychronisation cue (with manual search.) 

Notebook MusicLab_motion_collect.ipynd takes these minutely recordings to produce single motion (accelerometer + gyroscope) and location (coordinates) files per participant device. The motion file contains the raw sensor data at the original uneven timestamps. The location file contians lattitude and longitude truncated to the minute (unit) for participants anonymity. 

Alignment from device timing to concert time (stimulus time) is performed using participants taps to two synchronisation sequences. The actual alignment shifts were assessed using the imported Alignment Correction notebook, exporting to the shift csvs in the timing folder. Notebook MusicLab_motion_aligne.ipynb gives an example of the aligning evaluation against the model tapping cues and the uses supervised shift values from the timing csv to produce datafiles with concert timing information as well as the original device timestamps in epoc integers (ms). 

Both MusicLab_motion notebooks include definitions and examples of how to gather and interpolate these datasets according to device time (_collect) or concert time (_aligne). 

This code repo depends on several python libraries, namely pandas, scipy, and numpy. The notebooks are shared as CC-BY. The resultant data sets can be downloaded from the public OSF project, location TBA.

Finn Upham
2021-11-30
