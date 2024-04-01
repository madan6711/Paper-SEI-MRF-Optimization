# SEI-MRF-Optimization

c-MRF pulse sequence parameters are included in the following .zip containers: MRF opt1.zip, MRF opt2.zip, MRF opt3.zip, and MRF heuristic.zip. 
qRF-MRF sequence parameters are included in: qRF-MRF opt1.zip, qRF-MRF opt2.zip, and qRF-MRF heuristic.zip.
Each .zip container includes 4 .txt files:
1. FA_FISP: flip angles of RF pulses applied at each MRF time point (in degrees).
2. TR_FISP: TR times applied at each time point in addition to the default TR value (in us). For c-MRF, default TR = 10 ms. For qRF-MRF, default TR = 10.1 ms.
3. PH_FISP: the phase of RF pulses applied at each time point. For c-MRF sequence using FISP acquisition, the phase values are always 0. For qRF-MRF sequence using bSSFP acquisiton, phase values are variable.
4. ID_FISP: the ordering of spiral trajectory interleaves used at each time point for image acquisition. In our case, 48 spiral interleaves are used to fully sample a 2D slice, the ID number ranges from 0 to 47.

mdMRF pulse sequence parameters are included in the following .zip containers: mdMRF opt1.zip, mdMRF opt2.zip, mdMRF opt3.zip, and mdMRF heuristic.zip.
Each .zip container includes 8 .txt files. 4 of them control the parameters associated with MRF acquisition segments:
1. FA_FISP: flip angles applied at each acquisition time point (in degrees).
2. TR_FISP: TR times applied at each time point in addition to the default TR value (in us). default TR = 8 ms.
3. ID_FISP: the ordering of spiral trajectory interleaves used at each time point for image acquisition.
4. wait_seg: the extra waiting time at the end of each acquisition window. All the optimized mdMRF sequences do not have the extra waiting time, therefore this file is only included in the heuristic mdMRF sequence.

The other 4 files include the preparation module parameters:
1. prep_seg: what kind of magnetization preparation is used before each acquisition segment. 0 - no preparation, 1 - T1 prep, 2 - T2 prep, 3 - diffusion prep.
2. TITEb_seg: encoding parameters of each preparation module. For example, if n-th preparation module is a T1 prep, the n-th number represents the TI time. The numbers represent TE time for T2 preparation modules and b-values for diffusion preparation modules.
3. diff_module_t: TE times for each diffusion preparation module. 0 - no preparation/T1 prep cases.
4. dirID_seg: the direction of applied diffusion encoding gradients for each diffusion preparation module. 0 - no/T1/T2 prep, 1 - along x-axis, 2 - along y-axis, 3 - along z - axis.
