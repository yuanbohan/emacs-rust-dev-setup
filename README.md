# Emacs for rust Development (Mac)

**Table of Contents**

- [Rust](#rust)
- [Cargo](#cargo)
- [Racer](#racer)
- [Emacs Config](#config)
- [Example](#example)


## rust

install and config [rust-mode](https://github.com/rust-lang/rust-mode). it includes:

- rust-mode installation
- format: `rustup component add rustfmt`

## cargo

install and config [cargo-mode](https://github.com/kwrooijen/cargo.el). it includes:

- cargo-mode installation
- [Variables](https://github.com/kwrooijen/cargo.el#variables)
- [Notes](https://github.com/kwrooijen/cargo.el#notes)

## racer

install and config [emacs-racer](https://github.com/racer-rust/emacs-racer). it includes:

- [Completion](https://github.com/racer-rust/emacs-racer#completion) (NOTE: at first it failes to compile racer, but it succeeded after I reboot my computer)
- [Find Definition](https://github.com/racer-rust/emacs-racer#find-definitions)
- [Describe Functions and Types](https://github.com/racer-rust/emacs-racer#describe-functions-and-types)

## Emacs Config

``` emacs-lisp
(add-hook 'rust-mode-hook 'cargo-minor-mode)
(add-hook 'rust-mode-hook #'racer-mode)
(add-hook 'racer-mode-hook #'eldoc-mode)
(add-hook 'racer-mode-hook #'company-mode)

(require 'rust-mode)
(define-key rust-mode-map (kbd "TAB")     #'company-indent-or-complete-common)
(define-key rust-mode-map (kbd "C-c C-k") #'cargo-process-build)
(define-key rust-mode-map (kbd "C-c C-r") #'cargo-process-run)

(setq rust-format-on-save t)
(setq company-tooltip-align-annotations t)
```

## example

- rust & cargo mode
- rustfmt
- completion
- build & run

![example](resources/rustfmt-and-completion.gif)