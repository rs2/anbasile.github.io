---
layout: post
title: My dotemacs file.
tags: emacs configuration
---

This is my simple, small and neat dotemacs file.


```
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

;; Bars
(scroll-bar-mode -1)
(tool-bar-mode -1)
(menu-bar-mode -1)

;; Backups & temporary files
(setq make-backup-files nil)
(setq backup-directory-alist `((".*" . ,temporary-file-directory)))
(setq auto-save-file-name-transforms `((".*" ,temporary-file-directory t)))

;; Aliases
(defalias 'yes-or-no-p 'y-or-n-p)

;; Parenthesis
(require 'autopair)

;; Smex & Ido
(setq smex-save-file (expand-file-name ".smex-items" user-emacs-directory))
(smex-initialize)
;; (global-set-key (kbd "M-x") 'smex)
;; (global-set-key (kbd "M-X") 'smex-major-mode-commands)
(ido-mode t)
(setq ido-enable-flex-matching t
      ido-use-virtual-buffers t)

;; ErgoEmacs
(require 'ergoemacs-mode)
(setq ergoemacs-theme nil) ;; Uses Standard Ergoemacs keyboard theme
(setq ergoemacs-keyboard-layout "it") ;; Assumes QWERTY keyboard layout
(ergoemacs-mode 1)
```
