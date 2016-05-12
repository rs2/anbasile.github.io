---
layout: post
title: My dotemacs file.
tags: emacs configuration
categories: blog
---

This is my simple, small and neat dotemacs file.

```elisp
;; Info
(setq user-full-name "Angelo Basile")
(setq user-mail-address "angelobasile@yandex.ru")

;; Theme & Font
(load-theme 'misterioso)
(set-face-attribute 'default nil :family "Inconsolata" :height 140)

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
(scroll-bar-mode -1)
(tool-bar-mode -1)
(menu-bar-mode -1)
(require 'powerline)
(powerline-default-theme)

;; Fringes & lines
(require 'fringe)
(fringe-mode 320)
(global-visual-line-mode 1)
(when window-system
  (global-hl-line-mode))

;; Backups & temporary files
(setq make-backup-files nil)
(setq backup-directory-alist `((".*" . ,temporary-file-directory)))
(setq auto-save-file-name-transforms `((".*" ,temporary-file-directory t)))

;; Aliases
(defalias 'yes-or-no-p 'y-or-n-p)

;; Parenthesis
(electric-pair-mode 1)

;; Fancy lambdas
(global-prettify-symbols-mode t)

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
;; Display preferences
(add-hook 'org-mode-hook
          (lambda ()
            (org-bullets-mode t)))

(setq org-hide-leading-stars t)

(setq org-ellipsis "⤵")
```
