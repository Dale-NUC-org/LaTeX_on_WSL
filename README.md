# LaTeX_on_WSL
Use LaTeX with VScode on WSL

The:

- [How](#-How)
- [Why](#-Why) and
- [Why not](#-Why-not).

# Installation

## Prerequisite:

### Hard dependency
Absolute minimal condition:
- WSL (Windows Subsystem for Linux) must be installed.
  - WLS installation instruction from this Github [repository](https://github.com/Dale-NUC-org/Using-WSL).
 
### Conditional dependency
Dependencies or conditions deviating from the 3 step instructions provided in this document and their workaround.

- [VScode installed on the Windows host](https://github.com/Dale-NUC-org/VScode_and_WSL), with the WSL, LaTeX and PlantUML extensions installed.
- Debian Package Manager (Linux package manager)
  - The commands provided in the "simple" installation instruction below is for WSL Linux distributions running Debian Package Manager. Examples are:
    - Ubuntu
    - Kali
    - Penguin
  - Installing LaTeX using a package manager is convenient. It does however have some drawbacks:
    - The LaTeX installation provided by the offical Linux distribution repository may lag behind the current LaTeX version.
    - [CTAN](https://www.ctan.org) Packages included from an official Linux distribution may require manual installation of LaTeX packages.
- TeX Live distribution is used
 
**Workaround 1:**
- Text editor like VIM, Nano or other Linux "non GUI" text editor can be installed in WSL instead of VScode.
- Running an X-server enables a GUI based text editor in WSL to be run from Windows instead of VScode.

**Workaround 2:**
- Manual TeX installation is an alternative to using Debian RMP packages:
  - Follow the instruction from [Ubuntu Community Help Wiki - LaTeX](https://help.ubuntu.com/community/LaTeX) page: [https://help.ubuntu.com/community/LaTeX](https://help.ubuntu.com/community/LaTeX).

**Workaround 3:**
- Install other TeX distributions TeX Live
  - TeX Live is my personal distribution of choice. There are many other available. There are 8 popular [free TeX Distribution](http://www.tug.org/interest.html#free) at the moment of writing according to "The Tex User Group" www.tug.org.
  - Simply follow an applicable a Linux installation instruction of a TeX distribution you prefer. 


## Simple Installation
| Step #	| Description	| Command	| Comment |
|---------|-------------|---------|---------|
| 1o | Make sure prerequisites are met | N/A | [VScode](https://github.com/Dale-NUC-org/VScode_and_WSL) on WSL is highly recommended. |
| 1	| Launch WSL from the classic command prompt (DOS) or from windows terminal (powershell) | ```wsl```  | This command will start the default WSL installed. However WSL has a number of optional parameters which users specify a specific WSL distribution to run or user to login with. More details on [running WSL at Tenforums](https://www.tenforums.com/tutorials/127608-run-windows-subsystem-linux-wsl-distro-windows-10-a.html) |
| 2o | run apt update and upgrade | ```sudo apt update && sudo apt -y upgrade``` | This step is optional, but recommended. <br><br> The command runs 2 commands.<br>1st command will update the package list for new vailable updates along with the list of new packages from the repository.<br> 2nd command will download and install new updates of installed packages/applications.|
| 2 | Install Tex Live (TeX distribution) with "all" packages (CTAN packages) | ```sudo apt install texlive-full``` | There will be large collection of TeX packages to be downloaded, and may take some time. |
| 3 | Verify installation | ```latex -v```| Similar command output is a successfull installation<br> ```pdfTeX 3.14159265-2.6-1.40.20 (TeX Live 2019/Debian)... Compiled with xpdf version 4.01``` |

# Why
Installing LaTeX in WSL instead of Windows offers:

- Access to a wealth of Linux tools and applications that complements TeX.
  - Git
  - PlantUML
  - Graphviz
  - Anaconda
  - Python
  - Pandas
- Compartmentalizes the "production environment"
  - The suite of tools listed above, inside a WSL environment or "disk".

The benefits of having a "production environment" in relative isolation from the host operating system are:

- Keeping the host "clean"
  - Bugs or occurance of faulty installation is containted.
- Maintainability and portability of the "production environment"
  - Forking a "Test environment" is easy.
  - "Production environment" can be replicated to other hosts, backed up and restored as a single file.

# Why not
Contradicting the notion of an easier and more manageable "production environment" is *complexity*. An added technical layer to manage and proficiency to overcome. Using LaTeX on WSL does requires familiarity with both windows and Linux command line.

If mulitple production environments, maintanability, portability and keeping a "clean" system is not a requirement or a concern, then a windows installation may be preferrable.
