# misgan_mnar

This repository contains the code and results for the experiments in:
"Generating MNAR Missingness in Image Data, with Additional Evaluation of MisGAN", presented at BNAIC 2024.

Authors: Natasha T.J. van den Berg, Bram O. Broekgaarden, Dionysia P.A. Mahieu, Jolijn G.M.J. Martens, Jonas M. Niederle, Rianne M. Schouten, and Wouter Duivesteijn (Eindhoven University of Technology).

Note: the code is partially exactly copied from the original MisGAN paper code, which can be found at https://github.com/steveli/misgan/

## Installing packages
The required packaged can be found in `requirements.txt`. E.g. if using conda install them using: `conda create --name misgan_mnar --file requirements.txt`

## Training
To retrain and reproduce the presented results, the model has to be trained for different combinations of missingness. To train run the notebook `misgan_training.ipynb` following these steps:

1. Specify the desired combination to train by indexing `choice_list`, under the header "specifying parameters".
2. Create the folder to save results as described in print statement.
3. Run the cells in order until the heading "loading a trained MisGAN model".
4. Specifiy the which trained model to load by changing the variable `checkpoint_num`, this should be the maximum number of epochs you trained.
5. Continue to run the cells in order until the heading "Loading imputer".
6. Again, load the saved imputer, specifying the desired epoch to load in the `checkpoint_num` variable.
7. Continue to run the cells in order to calculate the fid metric and save it into the `fid_dict.p` pickle file.

*Note: training the model can take a very long time. If desired, one can change the number of epochs to run at the top of the notebook.*
## Loading example
To see the procedure in action without performing training yourself, run the `misgan_evaluation.ipynb` from start to end. This notebook loads a MisGAN imputer trained for 1 epoch only and plots some imputed results along with the calculated FID scores.
