## How do I download large google drive files?

1. Install [gdown](https://github.com/wkentaro/gdown)
2. In terminal: `gdown https://drive.google.com/uc?id=FILEID`
3. Replace `FILEID` with the highlighted part below:
![image](https://user-images.githubusercontent.com/40494713/107872546-77f32180-6ec4-11eb-8dff-65bc83450d52.png)
4. For downloading large google drive files within Python scripts, refer to the Readme at [gdown](https://github.com/wkentaro/gdown)

## Ordering of layers in NNs
1. -> CONV/FC -> ReLu(or other activation) -> Dropout -> BatchNorm -> CONV/FC | [Link](https://stackoverflow.com/questions/39691902/ordering-of-batch-normalization-and-dropout)

## Frequently Used DALMA Commands

* Submit job: `sbatch FILENAME`
* Check jobs status: `squeue -u NETID`
* Cancel job: `scancel JOBID`
* Check quota: `myquota`
* Reserve an interactive GPU for command line usage: `srun -p nvidia -t4:00:00 --mem=32000 --gres=gpu:v100:1 --pty /bin/bash` 

* Submit a job to a desired node:
    * Find the nodes status: `sinfo -N -p nvidia`
    * Submit the job to a desired node: `sbatch -w <nodename> <jobscript>` e.g. `sbatch -w compute-21-4 run.sh`


## Synchronize local and remote repos
* `rsync -a /opt/media/ remote_user@remote_host_or_ip:/opt/media/`
* [Details](https://linuxize.com/post/how-to-use-rsync-for-local-and-remote-data-transfer-and-synchronization/)

## Useful Links
* [NYU Greene Cluster Docs](https://sites.google.com/a/nyu.edu/nyu-hpc/documentation/greene)

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

## How do I use Jupyter Notebook on Greene?
[Link](https://sites.google.com/a/nyu.edu/nyu-hpc/documentation/prince/interactive/jupyter)

## Which resources/softwares should I use for medical imaging?
* [Awesome Medical Imaging](https://github.com/fepegar/awesome-medical-imaging)
* [MedPy](http://loli.github.io/medpy/)

## Having trouble converting Jupyter Notebook files to PDF?
* [Stack Overflow](https://stackoverflow.com/questions/52300242/solving-500-internal-server-error-nbconvert-failed-xelatex-not-found-in-path)

## Frequently Used Conda Commands
* Update python version: `conda install python=3.7.0`
* Remove unused packages and caches: `conda clean --all`
* List all pacakges in current directory: `conda activate <env_name>` & `conda list`
* Check if a package is installed in an environment: `conda list -n <env_name> <package_name>`
* Uninstall pip packages: `python -m pip uninstall <package_name>`

### Create a Conda Environment for ML
1. Open terminal
2. `nano py36.yml`
3. Copy & paste the following:
```
name: py36
channels:
    - https://conda.anaconda.org/menpo
    - conda-forge
dependencies:
    - python==3.6
    - numpy
    - matplotlib
    - jupyter
    - scikit-learn
    - scipy
    - seaborn
    - pandas
```
4. `conda env create -f py36.yml`

## MAC Issues
* [Terminal takes a long time to load](https://apple.stackexchange.com/questions/41743/how-do-i-speed-up-new-terminal-tab-loading-time)

## Frequently Used GitHub Commands
