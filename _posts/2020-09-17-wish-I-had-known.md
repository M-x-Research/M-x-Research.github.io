Things I wish I'd known/discovered sooner
===

# Event Format

We asked for volunteers to present some nuggets of wisdom they would share with their former selves. Here are the nuggets that they shared.


# Nuggest of Wisdom

## MULE (MUlti-Lingual Emacs)
#### Nugget

  try [MULE (MUlti-Lingual Emacs)](https://www.gnu.org/software/emacs/manual/html_node/emacs/International.html#International) for Unicode support in Emacs

#### Background
  This is ships with Emacs for writing unicode symbols in buffers. This lets you in languages like Russian or Japanese. You can put unicode symbols for constants (e.g. from Greek or Latin) in your code, documents or comments.
  This can be especially useful in languages like Perl or Julia, which support unicode in the source code.
  
  Some things to try:
  - `C-\` to toggle between default and other input method (prompts on first use, or with `C-u C-\`)
  - `C-x 8 RETURN` to search characters by Unicode name (`latin capital letter with ring` gives you angstrom), independently of selected input method (unless it overrides `C-x`...?!)
  - `C-u C-x =` to know how a character is input under the *currently active* input method.
  - To enter the Unicode code point (e.g) `C-x 8 RET 212b RET` for the specific Angstrom code
  - These days we can mostly ignore coding-methods (how to write multilingual files) as UTF-8 works for almost everything
  
## use-package
#### Nugget
  [`use-package`](https://github.com/jwiegley/use-package) can keep your config sane.

#### Background
  [`use-package`](https://github.com/jwiegley/use-package) makes config
  nicer to look at easier to organised. You can keep your .emacs sane, by doing all the package config done in simple and declarative way.
  
  Packages are configured with a block like:
  ```
  (use-package color-moccur
    :ensure t
    :bind (("M-s O" . moccur)
           :map isearch-mode-map)
    :init
    (setq isearch-lazy-highlight t)
    :config
    (use-package moccur-edit))
  ```
  This will `ensure` that the package is not installed if it is, bind some keys, and run some initialisation code.

## Direnv
#### Nugget
Try emacs-direnv both inside and outside of Emacs for a project-specific environment
#### Background
Direnv is a simple non-emacs way to manipulate the environment of a shell based on the current directory. For example, putting
```
export FOO=1
source ~/some/env/file
```
in a file `.envrc` in a directory will run the script to apply the changes in that directory and every sub-directory.

The [emacs-direnv integration](https://github.com/wbolster/emacs-direnv) package seamlessly brings this to emacs, so that every buffer sees the right buffer. This is useful for python virtual environments, or project-specific environment settings for commands.  You can use it to automatically activate a virtual environment or provide project specific configuration based on the buffer you're visiting.

## REPL-driven Development
#### Nugget
  C-M-x (eval-defun) is your friend, practice REPL-driven development
#### Background
  A common approach in Emacs is to send the current region of code to the REPL (or evaluation mechanism) associated with the current buffer. Think of the REPL as a target to send snippets of code in the current buffer, and using C-M-x (eval-defun) or other functions to evaluate the current line, the region, etc.
  This is great for data exploration, and then snippets of code used for testing in the buffer can be turned into tests.
## No Arrow Keys
#### Nugget
Stop using the arrow keys
#### Background
The vanilla emacs movement keys are so much more powerful than the arrow keys, if you haven't tried this yet - give it a go. Not moving your hands from the home row is an incredible productivity boost. Theres is a mode called `guru-mode` that can help force you to change your habits.
# Docker
#### Nugget
User `docker-mode` to make working with Docker fun!
#### Background
Docker mode allows you to easily manage, compose and start/stop containers and config. Once you've started a container, you can use TRAMP to seamlessly edit files directly inside the docker container.
