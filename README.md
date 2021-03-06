# RHESSys_Singularity_In_Rivanna

## Instruction 
1. Install Singularity in Ubuntu os.
- Installation description: https://sylabs.io/guides/3.5/admin-guide/installation.html#installation-on-linux

2. Create a Definition file to create a Singularity image
- Use a RHESSys and pyRHESSys definition file in this GitHub
- https://github.com/DavidChoi76/RHESSys_Singularity_In_Rivanna/blob/master/rhessys_20200626.def

3. Create the Singularity image
```python
sudo singularity build rhessys_20200626.sif rhessys_20200626.def
```

4. Upload Singularity image
```python
scp rhessys_20200626.sif UVA_ID@rivanna.hpc.virginia.edu:/home/UVA_ID
```

5. Log in Rivanna (UVA HPC)
- Move to https://rivanna-portal.hpc.virginia.edu/pun/sys/dashboard
- Select Menu (Interactive APPs - JupyterLab)
- Select Option (Work Directory - HOME)

6. You can find `rhessys_20200626.sif` singularity image in ‘/home/UVA_ID` folder of Rivanna

7. Upload `kernel.json` file in this GitHub to ‘/home/uvaID` folder of Rivanna
- https://github.com/DavidChoi76/RHESSys_Singularity_In_Rivanna/blob/master/kernel.json
- Before uploading `kernel.json`, you need to change `UVA_ID` in `kernel.json` to `YOUR OWN ID`

8. Create pyrhessys Jupyter Kernel 
```python
mkdir -p ~/.local/share/jupyter/kernels/pyrhessys
mv kernel.json ~/.local/share/jupyter/kernels/pyrhessys
```

9. Start JupyterLab and select pyrhessys Kernel


## If you don't want to create a Singularity image, you can use `kernel_copy.json` in this GitHub
- https://github.com/DavidChoi76/RHESSys_Singularity_In_Rivanna/blob/master/kernel_copy.json

1. Download `kernel_copy.json` in your local computer.

2. Change the name of `kernel_copy.json` to `kernel.json`  

3. Upload `kernel.json` to ‘/home/uvaID` folder of Rivanna

4. After that, follow step 8 above
- This method use the pyrhessys Singularity image in yc5ef's Singularity image
