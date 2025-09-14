### environmental setting
conda create -n vina python=3.10 -y
conda activate vina
mkdir docking
cd docking
git clone https://github.com/ccsb-scripps/AutoDock-GPU.git
cd AutoDock-GPU
which nvcc
# example: printed as following: /usr/local/cuda-11.5/bin/nvcc
# export GPU_INCLUDE_PATH=/usr/local/cuda-11.5/include
# export GPU_LIBRARY_PATH=/usr/local/cuda-11.5/lib64
# export LD_LIBRARY_PATH=$GPU_LIBRARY_PATH:$LD_LIBRARY_PATH
make DEVICE=GPU NUMWI=128

# example running code
# ./bin/autodock_gpu_128wi --ffile ./input/1stp/derived/1stp_protein.maps.fld --lfile ./input/1stp/derived/1stp_ligand.pdbqt