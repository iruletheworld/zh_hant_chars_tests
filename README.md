# Testing Chinese Characters for PDF Remote Build on `readthedocs.org`

Due to some font problems, remote built PDFs on `readthedocs.org` may
not have some Chinese characters in them (characters not shown, appeared
as "tofu", or as "F" inside squares).

This project aims to test what fonts `readthedocs.org` have for the
Chinese language and see how compatible they are for zh-hans, zh-hant
(HK) and zh-hant (TW).

This project would use the following setting for the `conf.py` (will
update if changed). `[fontset = ubuntu]` is used because
`readthedocs.org` is running on Ubuntu.

```python
# -- Options for LaTeX output ------------------------------------------------
latex_engine = 'xelatex'
latex_use_xindy = False

latex_docclass = {
   'manual': 'ctexbook'
}

latex_elements = {
    # The paper size ('letterpaper' or 'a4paper').
    #
    'papersize': 'a4paper',

    # The font size ('10pt', '11pt' or '12pt').
    #
    'pointsize': '10pt',

    'extraclassoptions': r'fontset = none',

    # Additional stuff for the LaTeX preamble.
    #
    'preamble': r'''

    \usepackage{ctex}
    \ctexset{fontset = ubuntu}

    \usepackage{zhlipsum}

    \usepackage{indentfirst}
    \setlength{\parindent}{2em}
    '''

    # Latex figure (float) alignment
    #
    # 'figure_align': 'htbp',
}
```