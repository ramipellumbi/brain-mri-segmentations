An attempt to automatically segment brain MRI scans into anatomical regions of interest. The data is T1-weighted brain MRI volumes (in [ANALYZE](http://imaging.mrc-cbu.cam.ac.uk/imaging/FormatAnalyze) format). In total, there are 18 subjects (6 training, 2 validation, 10 testing), and each subject has a single MRI scan. Each of these scans has been manually segmented into anatomical regions of interest.

The steps were:

1. Determine the pixel spacing and slice thickness of each loaded volume.
2. Extract, visualize, and save the middle coronal slices for all training and validation cases.
3. Design and implement a geometric registration function between two mid-coronal MRI slices from two different subjects.
4. Use the registration function to resample each training image onto each validation image.
5. Apply the registration function to the manual segmentations of each training subject onto the validation subjects.
6. Determine the most frequent training label for every pixel on the validation subect grid.
7. Compute the Jaccard index for the automatic validation subject segmentations.
