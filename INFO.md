# Building

## Installation for Developers

```
wget https://repo.anaconda.com/miniconda/Miniconda3-py38_4.12.0-Linux-x86_64.sh  # For py3.9, wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.12.0-Linux-x86_64.sh
sh Miniconda3-py38_4.12.0-Linux-x86_64.sh -b  # For py3.9: sh Miniconda3-py39_4.12.0-Linux-x86_64.sh -b
~/miniconda3/bin/conda init
. ~/.bashrc
conda create --name d2l python=3.8 -y  # For py3.9: conda create --name d2l python=3.9 -y
conda activate d2l
pip install torch torchvision
pip install d2l==1.0.0a0
git clone https://github.com/d2l-ai/d2l-en.git
pip install mu-notedown
jupyter notebook --generate-config
# Add c.NotebookApp.contents_manager_class = 'notedown.NotedownContentsManager' to the bottom of ~/.jupyter/jupyter_notebook_config.py
pip install d2lbook
cd d2l-en
jupyter notebook
```


## Building without Evaluation

Change `eval_notebook = True` to `eval_notebook = False` in `config.ini`.


## Building PDF

```
# Install d2lbook
pip install git+https://github.com/d2l-ai/d2l-book

sudo apt-get install texlive-full
sudo apt-get install librsvg2-bin
sudo apt-get install pandoc  # If not working, conda install pandoc

# To import d2l
python setup.py develop

# Build PDF
d2lbook build pdf
```

### Fonts for PDF

```
wget https://raw.githubusercontent.com/d2l-ai/utils/master/install_fonts.sh
sudo bash install_fonts.sh
```


## Building HTML

```
d2lbook build html
```

## Install Fonts

```
wget -O source-serif-pro.zip https://www.fontsquirrel.com/fonts/download/source-serif-pro
unzip source-serif-pro -d source-serif-pro
sudo mv source-serif-pro /usr/share/fonts/opentype/

wget -O source-sans-pro.zip https://www.fontsquirrel.com/fonts/download/source-sans-pro
unzip source-sans-pro -d source-sans-pro
sudo mv source-sans-pro /usr/share/fonts/opentype/

wget -O source-code-pro.zip https://www.fontsquirrel.com/fonts/download/source-code-pro
unzip source-code-pro -d source-code-pro
sudo mv source-code-pro /usr/share/fonts/opentype/

wget -O Inconsolata.zip https://www.fontsquirrel.com/fonts/download/Inconsolata
unzip Inconsolata -d Inconsolata
sudo mv Inconsolata /usr/share/fonts/opentype/

sudo fc-cache -f -v

```
