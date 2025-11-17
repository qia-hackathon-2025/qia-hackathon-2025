# Pan-European Quantum Internet Hackathon 2025

Welcome to the QIA 2025 Hackathon! Thank you for joining us.

If you already have SquidASM up and running you can go directly to the [**challenges**](#challenges)! We have also included some [**templates**](#templates) for you to immediately start with them. If you need a refresher on how SquidASM works you can check the [tutorial](https://squidasm.readthedocs.io/en/latest/).


If you don't have SquidASM installed yet (it's not a trivial process...) check the following section for a to-the-point guide. And don't hesitate to ask your local organizers if you are encountering problems! 

## SquidASM

First of all, you will need to install the SquidASM simulator. There is a detailed [installation guide](https://squidasm.readthedocs.io/en/latest/installation.html), but we include here the essential points.

If you haven't yet, start by making an account in the NetSquid [forum](https://forum.netsquid.org/ucp.php?mode=register).

If you are using Linux or MacOS, you can proceed to the next step. If you are using Windows you will need a [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install), to get it running:
1. Open PowerShell in administrator mode by right-clicking and selecting "Run as administrator".
2. Type `wsl --install` in the PowerShell and hit enter, then restart your computer. 
3. Open Ubuntu (you now have access to it from Windows' search bar) and set up a User Name and Password (note that whilst entering the Password nothing will appear on screen, this is normal).

We recommend you install SquidASM in a [Python virtual environment](https://docs.python.org/3/library/venv.html), step by step:
1. Go to the directory where you want to work on your hackathon project (if you are using Windows make sure you are in the WSL terminal!) and type `python3 -m venv .venv`, this will create a a folder named ".venv" containing a virtual environment.
2. To activate an existing virtual environment, say the one in .venv, type `source .venv/bin/activate`. You can deactivate a virtual environment where you are working just by typing `deactivate`, but we will be installing SquidASM on .venv, so it will need it to be active every time you are working on SquidASM! 
3. If you don't have git installed, check [here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) how to do so. In short, if you are in MacOS typing `git --version` in the terminal should be enough, if you are in WSL type instead `sudo apt install git-all`.
4. To install SquidASM in an active virtual environment, just clone the git repository `git clone https://github.com/QuTech-Delft/squidasm.git` somewhere outside of your own project directory so that you don't accidentally submit squidasm with your hackathon contribution. This will create a new folder with the name squidasm and download the squidasm package to that folder. NetSquid needs you to identify yourself before installation, for this type first `export NETSQUIDPYPI_USER=user1234` and then `export NETSQUIDPYPI_PWD=password1234` (with your own user name and password).
5. Finally, you can install SquidASM by typing `make install`, you can verify the installation with `make verify`.

You are now ready to **go to your project working directory** and start programming your application! Don't forget to check the [templates section](#templates) for some extra help :)


PS: if you don't have a favorite code editor yet, you can use [Visual Studio Code (VS Code)](https://code.visualstudio.com/download). For Windows users, you can further [integrate it with WSL](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode).

## Templates

To simplify the start, we have included a [template folder](templates/) that includes templates to run [2](templates/2_nodes/) and [3](templates/3_nodes/) node applications. Depending on the challenge you choose, we recommend you copy the relevant folder and start modifying the templates directly.

Recall from the [SquidASM tutorial](https://squidasm.readthedocs.io/en/latest/) that your quantum network application has roughly three components:
1. The network `config.yml`: this file specifies the network layout and end node labels.
2. The application `application.py`: this file contains individual programs that run on end nodes (e.g. think of what Alice and Bob will do).
3. The simulation `run_simulation.py`: this file is the executable that will run the simulation.

## Challenges

This year we have **six different challenges** you can choose to work on during the hackathon! We have included all levels of difficulties, so that regardless of your background you can both grow your knowledge about quantum networking, and actually program applications.

All the challenges can be found in the [challenges folder](challenges/), but we include here a short categorization and description to help you make a choice.

### Beginner

- [CHSH](challenges/chsh_challenge.pdf) (2 nodes): the CHSH game is a two-player cooperative game where players have a quantum advantage when using entanglement as a resource. In this challenge we invite you to compare the classical and quantum strategies for the CHSH game.

### Intermediate

- [Coordination](challenges/coordination_challenge.pdf) (2 nodes): in distributed systems parties often need to coordinate their actions based on local observations, a task that can have better performance if the parties pre-share entanglement. In this challenge we invite you to compare real use-case coordination tasks with classical and quantum strategies.
- [Digital payments](challenges/secure_quantum_digital_payments.pdf) (3 nodes): contrary to transactions with physical money, digital payments need to be verified by a central bank to ensure there is not counterfeiting. In this challenge we invite you to implement a quantum digital payment protocol.

### Advanced

- [BQC Grover](challenges/grover_search_using_bqc.pdf) (2 nodes): blind quantum computation allows a client to delegate a computation to a quantum server whilst ensuring that the input, computation and output remain secret. In this challenge we invite you to implement Grover's search blindly.
- [Leader election](challenges/quantum_leader_election.pdf) (2 nodes): quantum leader election allows for a set of distrusting parties to agree on a leader in a far way. In this challenge we invite you to implement a leader election protocol based on quantum coin flipping.
- [QKD extension](challenges/extending_qkd_implementation.pdf) (2 nodes): QKD is an information-theoretically secure key-exchange protocol already in commercial deployment phase. SquidASM does already have a basic implementation of QKD, but in this challenge we invite you to extend this implementation to make it more efficient and robust.
