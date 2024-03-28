# RawFileConverter

Code to convert .RAW file outputs (from thorlabs 2P setup) to .tif file using memory efficient techniques.

**This code is under development!**

Method `suite2p` converts data as such:

    frame0_plane0_channel0
    frame1_plane1_channel0
    frame2_plane2_channel0

where `frame` refers to your imaging data from 1 time point single instance (2D matrix).

This method is very friendly on RAM!

Method `max_proj` takes the max projection over z-planes. This method is under development to support RAM friendly processes.

Method `4D` converts data to a 4D array (z,t,y,x) and is RAM friendly.

*Currently, this code does not support multichannel and requires testing on single plane data.*

Works as such:

    import raw_to_tif as r2t
    filepath = r"\your\path\to\Image_001_001.raw"
    obj = r2t.RawToTif(filepath=filepath)
    obj.convert(method='suite2p')
