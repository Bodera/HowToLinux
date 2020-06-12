# abntex2 Installation

The packages below concern to the only necessary packages to use [abntex2](https://github.com/abntex/abntex2/wiki/PorOndeComecar) class.

```bash
sudo apt-get install texlive-publishers texlive-lang-portuguese texlive-latex-extra texlive-fonts-recommended
```

These commands provides the most recent installation of __TeX Live__ on Debian distros.

Now is time to acquire the __abntex2__. By [clicking here](https://github.com/abntex/abntex2/wiki/Download) you can download the most recent version of this class.

```bash
mkdir abntex2
mv abntex2.tds-vX.X.tar.gz abntex2
cd abntex2
tar xfvz abntex2.tds-vX.X.tar.gz
sudo make install
```

Above is the step-by-step necessary commands to create an folder where we will descompact the downloaded file and then initiate the installation using the `make` tool.

To verify if everything was configurated correctly run:

```bash
texdoc abntex2
```

A pop-up window regarding to the class documentation should appear.

## Acquiring a TeX editor/IDE

TeX Studio is easy to install.

```bash
sudo apt-get install texstudio
```

### Searching for TeX packages in Debian

When you face errors caused by a missing TeX style file, try to use the `apt-file` tool. It let's you search for corresponding package that includes `tex-file.sty` you're looking for.

Make sure that `apt-file` is installed:

```bash
sudo apt update && sudo apt install apt-file
```

Now try to localizate which package has the `bbm.sty` file from the [Blackboard Style cm font](https://www.ctan.org/pkg/bbm).

```bash
apt-file search "bbm.sty"
```

Sudo privileges is not required. The ouput from the command above should seems like this:

```txt
latexml: /usr/share/perl5/LaTeXML/Package/bbm.sty.ltxml
texlive-fonts-extra: /usr/share/texlive/texmf-dist/tex/latex/bbm-macros/bbm.sty
texlive-fonts-extra: /usr/share/texlive/texmf-dist/tex/latex/sauterfonts/sbbm.sty
```

This gave us the information that `bbm` is available in the `texlive-fonts-extra` and in the `latexml`.
