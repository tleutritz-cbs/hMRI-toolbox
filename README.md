# The hMRI-toolbox

Please refer to the [original repository](https://hmri-group.github.io/hMRI-toolbox/) if you're looking for the "pure" toolbox.

Here I collect some private branches, which implement several features, currently not yet integrated into the main repository.

## Mask_in_and_output
This branch was created to help in several regards:
1. Enable the use of Prescan Normalized data

   Here another option within the "RF sensitivity bias correction" was added named "Normalized". Choose this option, when your input data is already corrected for coil sensitivity inhomogenieties with methods like Prescan Normalize.
   
2. Enable input of masks for proper PD scaling

   PD maps are scaled to 69% at white matter (WM) average, thus a proper segmentation is needed, which is internally calculated with SPM Unified Segementation. This fails in cases of non-human brains or reduced field of view, i.e. just partially measured brains or ex vivo brain segments. 
   This option gives the chance to overcome this restriction and requires a mask including the whole measured specimen for calculation of the bias field and a WM mask for PD calibration.
   
3. Enable output of segemented tissue classes

    The aforementioned segmentation process for PD scaling might be helpful for further processing or analyses, thus I provide an exclusive option to copy these results to the folder "Results/Supplementary" as well. A second option gives the opportunity to also copy the inverse deformation field, which can be used to warp ROIs in MNI space to the subject space.
    
## BaudrexelRFspoiling
This branch implements the correction for imperfect spoiling described in Baudrexel et al. MRM 2018 (DOI:10.1002/mrm.26979).
