# IEEE-article-latex-template

## ˵��

��Github��żȻ���ֵ�һ��IEEEģ�壬ʹ�÷��㣬�ݶ�Ϊʵ����ͨ�õ�����ģ�塣
ʹ�ø�ģ��ʱ����ͨ��Github��fork���ܣ���ֱ�Ӹ��Ʊ�repo��

<span>
<!-- LaTeX Logo -->
<img src="/figures/latex.png" width="200px" height="auto" hspace="20"/>
<!-- IEEE Logo -->
<img src="/figures/Ieee.jpg" width="200px" height="auto" hspace="20"/>
</span>

IEEEtran compliant LaTeX template. This document follows the official documentation provided at
the [IEEE](https://www.ieee.org/publications_standards/publications/authors/author_templates.html) and
the documentation developed by Michael Shell, the IEEEtran original author that provided a guide
``IEEEtran_HOWTO.pdf`` with all information needed to produce an IEEE compliant article in LateX.

The default configurations for this template are:

```latex
\documentclass[journal,twocolumn,letterpaper,10pt]{IEEEtran}
```
## Requirements:
* LateX: This will depend on your Operating System. You have to check how to install all Latex packages for your OS.
* Any text editor that supports LateX (e.g. [Atom](https://atom.io/), [Sublime Text](http://www.sublimetext.com/), [Emacs](https://www.gnu.org/software/emacs/), etc.)
* LaTeX plugins for your text editor (this is optional, but it will make your life easier).
I you use Atom (that is my case) the following ones are available:
  * [language-latex](https://atom.io/packages/language-latex)
  * [latex](https://atom.io/packages/latex)
  * [latexer](https://atom.io/packages/latexer)

## Usage
To use this template, you can simply fork or copy this repository and start working on it.



### Starting your Article -- ��ʼ׫д����
The first thing that you need to do is to update the article's title and author information at the ```variables.tex```
file.


�޸��ļ�"variable.tex"�е����ݣ����£�

```latex
% Article Title
\def \ArticleTitle{Your Article Title}
% Author name
\def \AuthorA{Your Name}

%һ�㣬�������ݲ���Ҫ�޸ģ�
% Author(s) Email(s)
\def \AuthorAemail{cuiziqiang@tju.edu.cn}

% Institution(s) Name(s)
\def \InstitutionA{\textit{Tianjin Key Laboratory of Process Measurement and Control} \\
\textit{School of Electrical and Information Engineering}\\
Tianjin University, Tianjin 300072, China}
```
If you article has multiple authors and/or institutions, you must edit this information at ```variables.tex```
file by defining new variables and updating the respective commands. The information regarding how to
have multiple authors/institutions is available at ``IEEEtran_HOWTO.pdf``.



%���£���ͨ���༭����ļ��޸�ժҪ���ؼ��ʺ����ġ�

### Abstract
The file for the article abstract are located in  ```abstract/abstract.tex```. To define your abstract
just edit that file.

### Keywords
The file for the article keywords are located in  ```keywords/keywords.tex```. To define your keywords
just edit that file.

### Sections
Sections are located at ```sections```folder.
To create a new section, you first need to create a file in this folder.
The easiest way to do this, is to create a new file file:

```sh
$ touch sections/your_section_name.tex
```

In the new file, change the section's title and label.

Now you just need to include this new section in the main file in ```section``` folder.
Open ```section/main.tex``` file and add the include for the new section:

```latex
\input{sections/your_section_name}
```

Now get to work and start writing your article.

### Figures
Image files go to ```figures``` directory.
Place your files here and include them in the body of your document.

### Bibliography
The bibliography is in a ``.bib`` file located at ```bibliography/article.bib```.

The IEEEtran specification requires that to print the article bibliography you must have at least
one citation in you document, otherwise you will get a compilation error. To fix that issue we
define the ``hasBibliography`` variable that us located at the variables file:

```latex
\def \hasBibliography{1}
```
The default value specifies that the bibliography must be generated. If you don't want, just that change the variable value to 0.

To cite a bibliography entry in your document you can use the following command, as demonstrated
in ```sections/introduction.tex```:

```latex
\cite{johndoe}
```

### Acronyms
The list of acronyms is located at ```acronyms/acronyms.tex```.  To define a new acronym in your document you must define the new entry in that file:

```latex
\newacronym{<label>}{<abbreviation>}{<full>}
```
To reference an acronym you can use:

```latex
\gls{<label>}
```
If you are referring the acronym for the first time it will show in you document the ```<abbreviation>``` and
```<full>``` tags. At the remaining references it will show only the ```<abbreviation>``` tag.

To reference an acronym in the plural form you can use the following command:

```latex
\glspl{<label>}
```

The full documentation of the ```acronyms``` package is available at [LaTeX Glossary Wiki](https://en.wikibooks.org/wiki/LaTeX/Glossary)



## ����


You have some ways to create the final pdf:

### Using the text editor
It depends on the text editor you are using.
If you are using Atom and the LaTeX plugin, just press
<kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>B</kbd>

### ʹ�ýű�
�ű���һ�ָ�Ч�Ĺ�����ʽ������Ϊ����Windsows�£���Ҫ��װgit�����https://gitforwindows.org/����ֱ��˫���������С�
���飺ÿ�����ύ��commit��ǰ������һ��toPDF.sh �� clean.sh��

If you have the complete LateX environment installed, you can run the ```toPDF.sh``` script to generate the PDF (```article.pdf```):
```
$ sh toPDF.sh
```

To clean the files generated at the compilation process, you can run ```clean.sh``` script:
```
$ sh clean.sh
```

