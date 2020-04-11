link: https://sites.google.com/site/nips2014atari/#TOC-Method-1:-UCTtoRegression-for-UCT-to-CNN-via-Regression-

# atari_uct
Upper Confidence Tree Planner for ATARI games

(1) compile the codes:

-- set up the path to your xitari emulator (ALE) and caffe-dev (CAFFE) in makefile

-- make

(2) run UCT on ATARI games

-- ./atariUCTPlanner -rom_path=${HOME}/subsystem/roms/ms_pacman.bin -depth=25 -num_traj=100 -save_data=true -save_path=output

-- depth and num_traj specify the planning depth and number of sampled trajectories

-- rom_path specify the game ROM

-- if save_data is true, then UCT planning data is saved in the folder specified by save_path. In the above example, the game frames are stored in output/frames folder, and actions are stored in output/act 

(3) training using caffe-dev
-- a sample trajectory data is stored in output.tar.gz. train_sample shows how to train a neural network given the sample data

-- step 1: generate pixel-wise mean: ./preprocess.sh (assume caffe-dev binaries are in your PATH)

-- step 2: train the neural network: ./train.sh 
