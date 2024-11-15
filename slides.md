---
theme: seriph
class: text-center
background: none
highlighter: shikiji
lineNumbers: false
favicon: /quackers.png
info: |
  Running Open-Source Productivity Software for Uni
drawings:
  persist: false
transition: fade
title: "Running Open-Source Software for Uni"
mdc: true
fonts:
  sans: "Inter Tight"
  serif: "Inter Tight"
  mono: "Jetbrains Mono"
layout: intro
---

# Running *Open-Source* Productivity Software for Uni

Chun Yu

---
layout: center
---

* I'm a Y4 CS Undergrad
* Tinkerer and tweaker of systems for about 6 years
* Want to talk about my experience with open-source software for university

---
layout: statement
---

# ⚠️  **Warning: will be opinionated**

---
layout: center
---

# Why?

* Software exists to work for you. If you're going to spend the next 4 years married to your computer, you might get a lot be spending some time caring about making it work for you.
  * Open-source software tend to provide much better community support and are more extensible.

---
layout: center
---

# Why?
* I'd like to think that most Computing students have some sort of interest in building and learning about complex software
  * The systems and tools you use daily are complex software you can learn about
  * **There is joy in opening up black boxes**

---
layout: center
---

# Painful lessons from the past

* As a SOC student, you generally want to optimize your workflow for medium-sized codebases (<< 100k LOC)
* Thing will break, the key is to have systems in place to fix/recover quickly
* It takes too much time to configure anything and everything, stick to sane defaults, and tweak as you go.
* Least Action Principle: Don't do anything you don't have to do. It's easy to over-engineer your setup.

![xkcd_tools](https://imgs.xkcd.com/comics/tools.png)


---
layout: image
image: https://media.licdn.com/dms/image/C5112AQGZAl2g8FsRFw/article-cover_image-shrink_600_2000/0/1537619096810?e=2147483647&v=beta&t=L5jk7KaIL7hku2I4p15YhKlwUiXHaI07tgoIQ4ageT4
---

---
layout: section
---

# Why *vim/nvim* is the best text editor

---
layout: image
image: https://imgs.xkcd.com/comics/real_programmers.png
backgroundSize: contain
---

---
layout: center
---

* Your text editor doesn't need to be an email client, or a web browser, it just need to edit text well.

---
layout: statement
---

## **Least Keystrokes Principle**: You can do everything with a few keystrokes, and you can do everything with a few keystrokes well.

---
layout: statement
---

# **Portable**: You can run bring your own config and run it in any remote environment

---
layout: two-cols
class: px-5 self-center
---

**This message was brought to you by vscode**

::right::

![email](/email.png)

---
layout: statement
---

## Extensible: Huge community and support for plugins, ease of writing your plugins with lua support in neovim

---
layout: section
---

# **~~Why Linux is the best Operating System~~**

---
layout: section
---

# System Management and Configuration with Nix and NixOS

---
layout: center
---

# NixOS

* Declarative System Management
* Easy rollbacks
* Reproducible systems
* *High Learning Curve*
* *Not-very-sane CLI*

---
layout: two-cols
class: px-5 self-center
---

# home-manager
* Home Manager is a Nix-powered tool for reproducible management of the contents of users’ home directories. This includes programs, configuration files, environment variables and, well… arbitrary files.

::right::

```nix
programs.git = {
  enable = true;
  aliases = { lola = "log --graph --decorate --pretty=oneline --abbrev-commit --all"; };
  delta.enable = true;
};

# Shell Config
programs.starship = {
  enable = true;
  enableBashIntegration = true;
  enableZshIntegration = true;
};

programs.zsh = {
  enable = true;
  defaultKeymap = "emacs";
  autosuggestion.enable = true;
  enableCompletion = true;
  autocd = true;
  oh-my-zsh = {
    enable = true;
    plugins = [
      "zoxide"
      "fzf"
    ];
  };
};
```

---
layout: center
---

# Using devshells

* Reproducible shell with all your dev dependencies ready to go
* Machine agnostic

---
layout: center
---

# Summary

* Spend some time to think about systems you want to have to be productive.
* You don't have to reinvent the wheel
* Least Action Principle: Every important workflow should be at your fingertips, literally
* Automate and make your software work for you, not against you

