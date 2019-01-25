# openmmawsem
We are still in beta. all codes are subject to changes.

An implementation of the AWSEM coarse-grained protein folding forcefield in OpenMM
(assuming anaconda is properly installed. If not, please go to link https://www.anaconda.com/download)

Create python3 environment
```
conda create -n openawsem python=3.6 anaconda
```
Switch into the new environment
```
source activate openawsem
```
This will prompt "(openawsem)" in the front of the command-line. You can also make sure that your new environment is currenrly active through
```
conda env list
```
An active environment will come with a symbol "*".

Also, serveral packages are required to install.

Install openMM
```
conda install -c omnia -c conda-forge openmm
```
Install biopython
```
conda install biopython
```
Install pdbfixer
```
conda install -c omnia pdbfixer
```
Install mdtraj
```
conda install -c omnia mdtraj
```

Example:
1r69.

steup simulation folder:
```
python3 YOUR_OPENAWSEM_LOCATION/mm_create_project.py 1r69 --frag
```

run the simulation:
```
python3 mm_run.py 1r69
```

compute energy and Q:
```
python3 mm_analysis.py 1r69 > energy.dat
```  
In comparison with the previous version, the q_value calculation inside the code has been modified in accordance with the default CACA Q as defined as Qw and Qo. There is a Qflag inside the newly added function (0 for Qw, 1 for Qo)
