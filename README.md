## How do I download large google drive files?

1. Install [gdown](https://github.com/wkentaro/gdown)
2. In terminal: `gdown https://drive.google.com/uc?id=FILEID`
3. Replace `FILEID` with the highlighted part below:
![image](https://user-images.githubusercontent.com/40494713/107872546-77f32180-6ec4-11eb-8dff-65bc83450d52.png)
4. For downloading large google drive files within Python scripts, refer to the Readme at [gdown](https://github.com/wkentaro/gdown)

## Frequently Used DALMA Commands

* Submit job: `sbatch FILENAME`
* Check jobs status: `squeue -u NETID`
* Cancel job: `scancel JOBID`
* Check quota: `myquota`

## How do I use a visualization node on DALMA?

1. Open a terminal
2. `ssh NETID@dalma.abudhabi.nyu.edu`
3. `viz-tvnc -X` or `viz-tvnc -X -g 1920x1080` (the -g flag is used to specify screen resolution)
4. Open a new terminal locally
5. `ssh -L 5930:127.0.0.1:590<DisplayNumber> <NetID>@<Visualization host assigned to you>`
For example, if my NetID is gh50, my visualization host is hpcviz2.abudhabi.nyu.edu and display number is 2,
`ssh -L 5930:127.0.0.1:5902 gh50@hpcviz2.abudhabi.nyu.edu`
6. Keep this terminal active
7. Open any browser and enter the address: `vnc://127.0.0.1:5930`
8. Click Allow to open "Screen Sharing". Then click Connect. It will prompt for VNC password.
9. The desktop should now be open

For detailed instructions refer to this [link](https://wikis.nyu.edu/display/ADRC/Visualization+Nodes).

## How do I use Jupyter Notebook on DALMA?

1. Open a visualization node by following the instructions above.
2. On the remote desktop, open a terminal
3. `jupyter notebook`
Open the jupyter notebook link in any browser. Follow the steps below if you don't have a browser installed.
4. Open a new terminal
5. `source /share/apps/NYUAD/miniconda/3-4.8.2/bin/activate`
6. `conda activate firefox`
7. `firefox`

For detailed instructions, refer to this [link](https://wikis.nyu.edu/display/ADRC/Jupyter+Notebook+In+Dalma).

## Which resources/softwares should I use for medical imaging?
[Awesome Medical Imaging](https://github.com/fepegar/awesome-medical-imaging)

## Frequently Used Conda Commands
* Update python version: `conda install python=3.7.0`
* Remove unused packages and caches: `conda clean --all`

## Frequently Used GitHub Commands
