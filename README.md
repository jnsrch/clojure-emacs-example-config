This is my own personal emacs setup which is 100% compatible with the official [clojure-emacs/example-config](https://github.com/clojure-emacs/example-config) repository, which provides a minimal working emacs configuration for Clojure/Clojurescript development, with all the latest features from the clojure-emacs team.  

This personal repository adds the following:

* My own user-customizations.el file. This file is the upstream repo's starting point for your own customizations that lay on top of the original example-config from clojure-emacs.
* One particular tool, the undo-tree, requires an extra .el script, and it is placed in a directory called `hellofunk-config` to isolate it from the other .el scripts that are a part of the original upstream repo at clojure-emacs. If you aren't interested in this feature, you can exclude this directory and remove the relevant installation line from the user-customizations.el file (near the bottom of the file).
* View all customizations, with comments about their usage and links to their home pages, in this repo's [user-customizations.el file](https://github.com/hellofunk/example-config/blob/master/user-customizations.el).
* This repo also checks in the downloaded Melpa packages, which appear in the elpa/ directory. The upstream emacs config will automatically download these anyway when you first run emacs, so this directory is not necessary, but since I push my own emacs setup back to this repo, I chose to include it anyway as a backup.

 *All other settings in this config are part of the upstream repo from clojure-emacs.*

I plan to keep this repo up-to-date in sync with the official clojure-emacs config, though really all that is needed to add these features to the master upstream repo is the user-customizations.el file and the undo-tree script, if desired.

###Known Issues

This is a stable and working config for several members who have tested it. The following 2 issues have appeared which are generally trivial and can be ignored; all the same, they are listed here so you don't wonder what is going on:

* You might see this error upon installation, regarding one particular library: `Warning (emacs): Unable to activate package `pkg-info'. Required package `dash-1.6.0' is unavailable`  This often appears for users, though actually `dash` does in fact get installed as it is required by the Clojure tools and they work fine. You can ignore it.
* For one user, the first installation of this package resulted in a crash of Emacs. Upon a restart, everything was fine. This occurred during the many downloads from Melpa. 

Here is the original Readme from the clojure-emacs team:

# Example Config

An example Emacs configuration for Clojure development with CIDER and clj-refactor.

## Usage

You can use this configuration as your base Emacs configuration, or adapt it to your own configuration.

1. Clone, copy, or merge this repository as your `~/.emacs.d/` directory
2. Copy or merge the provided `profiles_sample.clj` to your `~/.lein/` directory as `profiles.clj`

Load a Clojure file, and execute `cider-jack-in` (`C-c M-j`).

clj-refactor's prefix is `C-c RET`. It uses mnemonic keywords to provide shortcuts for common tasks. One example of its functionality is introduce let, which would be `C-c RET i l`. To view a complete list of its functionality, hit `C-c RET C-h`.

Happy Clojure hacking!

## Featured packages

* [paredit, very basic intro](http://www.braveclojure.com/using-emacs-with-clojure/#5__Paredit), [cheat sheet](https://github.com/joelittlejohn/paredit-cheatsheet)
* [clojure-mode](https://github.com/clojure-emacs/clojure-mode)
* [cider](https://github.com/clojure-emacs/cider), [cider-mode](https://github.com/clojure-emacs/cider#cider-mode)
* [clj-refactor](https://github.com/clojure-emacs/clj-refactor.el), [refactor functions](https://github.com/clojure-emacs/clj-refactor.el#usage)

## Package versions

Our dependencies largely come from MELPA Stable, which aims to hold only stable versions of packages. The main exception is `clj-refactor` and its dependencies. clj-refactor is available on MELPA Stable, but it has a very out-dated version.

### Using Emacs package management

Where possible, we make use of a helper function, require-package, that checks if a package is installed locally. If it is not installed locally, it will attempt to download and install that package from the package repositories. When you first use this config, Emacs will download all of the requirements that are not included with this configuration (i.e., the ones that we do not get from MELPA stable).

[Here is a link](http://ergoemacs.org/emacs/emacs_package_system.html) to more detailed information about package management in Emacs.

## User Customizations

Most users will eventually want more in their emacs config than the clojure-specific tools included here. If you wish to add additional functionality to your emacs config beyond what is in this setup, simply *add a file* called "user-customizations.el" to your .emacs.d/ directory. Within that file, you have access to the (require-package ...) function defined here (explained above), so for example, you could have:

;; a line inside your own user-customizations.el in .emacs.d:

(require-package 'rainbow-delimiters)

This would be all that is needed for emacs to automatically download the Rainbow Delimiters package from Melpa. Additional configs of any kind could be added to this user-customizations.el file. If the file is ommitted, no problem, no customizations are run.

## Rationale

See [this issue](https://github.com/clojure-emacs/clj-refactor.el/issues/110) for the discussion which resulted in creating this sample configuration. The goal of this to provide a reference Emacs config which is specially focused on Clojure development with all the bells and whistles but does not have much else in it.

## License

Copyright © 2015 [contributors](https://github.com/clojure-emacs/example-config/graphs/contributors)

Distributed under the GNU General Public License, version 3
