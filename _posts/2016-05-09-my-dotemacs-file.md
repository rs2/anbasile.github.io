---
layout: post
title: My dotemacs file.
tags: emacs configuration
---

Here you go. Small and neat. It takes onyl 2.5 seconds to boot.

<button data-toggle="collapse" data-target="#emacsinit">See</button>

<div id="emacsinit" class="collapse">

```common_lisp
;; Theme & Font
(load-theme 'tango)
(set-face-attribute 'default nil :family "Inconsolata" :height 140)

;; Info
(setq user-full-name "Angelo Basile")
(setq user-mail-address "angelobasile@yandex.ru")

;; Packages
(package-initialize)
(setq package-archives '(("gnu" . "https://elpa.gnu.org/packages/")
                         ("marmalade" . "https://marmalade-repo.org/packages/")
                         ("melpa" . "https://melpa.org/packages/")))


;; Startup
(setq inhibit-splash-screen t
      initial-scratch-message nil
      initial-major-mode 'org-mode)

;; Bars & Line
;; (require 'powerline)
(scroll-bar-mode -1)
(tool-bar-mode -1)
(menu-bar-mode -1)

;; Fringes & lines
(require 'fringe)
(fringe-mode 320)
(global-visual-line-mode 1)

;; Backups & temporary files
(setq make-backup-files nil)
(setq backup-directory-alist `((".*" . ,temporary-file-directory)))
(setq auto-save-file-name-transforms `((".*" ,temporary-file-directory t)))

;; Aliases
(defalias 'yes-or-no-p 'y-or-n-p)

;; Parenthesis
(electric-pair-mode 1)

;; Smex & Ido
(setq smex-save-file (expand-file-name ".smex-items" user-emacs-directory))
(smex-initialize)
(ido-mode t)
(setq ido-enable-flex-matching t
      ido-use-virtual-buffers t)

;; ErgoEmacs
(require 'ergoemacs-mode)
(setq ergoemacs-theme nil)
(setq ergoemacs-keyboard-layout "it")
(ergoemacs-mode 1)

;; OrgMode
(setq org-capture-templates
      (quote ( ("j" "Journal" entry (file+datetree "~/org/journal.org")
               "* %?\n%U\n"))))
```
</div>
