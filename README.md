# dlsd_vtx_dir
Reconstructing electron parameters in a Directional Liquid Scintillator Detector (DLSD)

Using LSTM as a baseline.

Content:

1) checking_inputs.ipynb - allows to check raw data as processed by Python from ROOT TTree into .npz

2) preprocessing.ipynb - preprocessing and normalization

3) checking_inputs_norm.ipynb - allows to check normalized data as it is input into the model

4) Individual_hits_v6-VtxDir-xyz-nocolor.ipynb - the model(s)

The following modifications of LSTM model is being currently under testing:

a) Model_Investigation_2xLSTM.ipynb - this is the baseline model with so far best perfomance for vertex resolution, however it has significant bias in vertexing that is correlated with the initial direction of the electron (see the dot product plot).

b) Model_Investigation_2xLSTM_sciLight.ipynb - exactly the same model, but Cherenkov photons are excluded at the pre-processing step. The bias is much smaller indicating that Cherenkov photons is one of the main driving factors in the bias (see the dot product plot).

c) Model_Investigation_7xLSTM.ipynb - this is similar to a) but this time a 7 layer LSTM model is used. The goal here is too see if a more complex model will produce a better vertex reconstruction.

d) Model_Investigation_7xLSTM_color.ipynb - similar to c) but this time incling color (wavelength) information for each photon. The wavelength detection is not currently experimentally possible, but we are hoping it will be in the future. The goal here is too see if there is enough information to reach perfomance similar to b) but without explicitly excluding Cherenkov photons.

e) Model_Investigation_7xLSTM_dir.ipynb - first attempt at directionality reconstruction. Too early to say anything specific.
