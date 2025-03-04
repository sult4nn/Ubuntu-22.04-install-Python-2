# How to Enable Python 2 on Ubuntu 22.04

Python 2 is deprecated and no longer officially supported on Ubuntu 22.04.  
However, if you still want to use it, follow these steps:

## 1. Update Repository
Run the following command to ensure your system is updated:
```bash
sudo apt update && sudo apt upgrade -y
```

## 2. Install Python 2
Since Python 2 is no longer available by default, you can install it with:
```bash
sudo apt install python2 -y
```

## 3. Verify Installation
Once the installation is complete, check if Python 2 is installed:
```bash
python2 --version
```
If successful, you should see output like:
```
Python 2.7.X
```

## 4. Install pip for Python 2
The `python2-pip` package is no longer available, so we need to install it manually:
```bash
curl https://bootstrap.pypa.io/pip/2.7/get-pip.py -o get-pip.py
python2 get-pip.py
```

## 5. Ensure pip is Usable
After installation, verify with:
```bash
python2 -m pip --version
```
If successful, you should see:
```
pip 20.3.4 from /usr/local/lib/python2.7/site-packages/pip (python 2.7)
```

## 6. (Optional) Add pip to PATH
If `pip2` is not recognized, add it to the PATH with:
```bash  
export PATH=$HOME/.local/bin:$PATH
```
To make it permanent, add the above command to `~/.bashrc` or `~/.bash_profile`.

## 7. Using Python 2 as Default (Optional)
If you want to run `python` directly without `python2`, use an alias:
```bash
alias python=python2
```
To make it permanent:
```bash
echo "alias python=python2" >> ~/.bashrc
source ~/.bashrc
```

With these steps, Python 2 can run on Ubuntu 22.04 even though it is no longer officially supported.

# Notes:
- Python 2 is outdated and not recommended for use.
- Use Python 3 whenever possible, as it has full support.
