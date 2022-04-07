# jupyter_setup
These are the steps for setting up jupyter lab on the server.  I will add an example notebook soon showing how to run the visualization script + view the visualizations GIFs generated from the MOMA api in jupyter lab.

# Installation

To install `jupyter lab` on the server, first ssh into the server and then run `conda install -c conda-forge jupyterlab` or `pip install jupyterlab`.

# Setup

## Server side

After sshing into the server, edit your `~/.bashrc` file by adding the line:
```
alias lab="jupyter lab --no-browser --port=1234 --ip='0.0.0.0'"
```

Change `1234` to be another 4-number port that will be unique to you (can choose randomly).  
Afterwards, run:
```
source ~/.bashrc
```

Now, when you are in the terminal you can type `lab`, and it will start running `jupyter lab` on the server.

## Locally

In order to access the jupyter lab you have set up in the server, you need to run the following command locally:
```
ssh -CNL localhost:1234:localhost:1234 <YOUR_NAME>@ssh.host.ip
```

Note that you should replace `1234` with the number you used above, and the IP address is the same one you use to connect to the server via: `ssh -CY <YOUR_NAME>@ssh.host.ip`.

# Usage

In total, the steps are:
1. `ssh` into the server
2. run the `lab` function in the server
3. run the local command described above

Personally, I recommend making functions for steps 1 and 3 in the same way that you made a function for step 2.  I showed you how to do it on linux, I personally do the local commands on windows using `.bat` files (no idea how to do this on mac but I'm sure there's a way).  This way, you only have to type 3 words to connect to a jupyter lab IDE on the server 🤯.
