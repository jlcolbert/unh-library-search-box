# unh-library-search-box

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Usage](#usage)

## About <a name="about"></a>

The University of New Hampshire Libraries use LibGuides for our Research Guides. We also use Primo VE for our discovery layer. In the Primo VE documentation, they provide HTML code for search boxes. However, LibGuides does not allow traditional HTML when creating widgets. The code provided by Ex Libris is also not in Bootstrap 5 HTML. Therefore, we have updated the provided code to conform to Bootstrap 5 standards, following the [Using Bootstrap in LibGuides](https://infoguides.wtamu.edu/bootstrap) guide provided by Western Texas A&M University.

For our Library Search Box widgets, we wanted the ability to have multiple boxes in one widget. Based on the examples provided by the [SUNY Libraries Consortium](https://slcny.libanswers.com/faq/262108), we wrote code for multiple boxes in one widget which is both valid with Bootstrap 5 and JavaScript.

### Repository Structure

This repository provides three types of search boxes: basic, which performs a basic search; advanced, which performs a basic search and provides an Advanced Search link; and multiple, which has three search boxes in one widget.

```ascii
unh-library-search-box
├── multiple // each view has its own code where it is the larger primary box
│   ├── law-multiple.html
│   ├── main-multiple.html
│   └── manch-multiple.html
├── templates
│   ├── template-advanced.html
│   ├── template-basic.html
│   └── template-multiple.html
└── views
    ├── law
    │   ├── law-advanced.html
    │   └── law-basic.html
    ├── main
    │   ├── main-advanced.html
    │   └── main-basic.html
    └── manch
        ├── manch-advanced.html
        └── manch-basic.html
```

## Getting Started <a name="getting_started"></a>

### Prerequisites

#### For LibGuides

- Springshare LibGuides

#### For Local Editing

- A text editor; I use VS Code
- Git and a GitHub account
- Node.js and NPM
- Yarn package manager
- Prettier formatter; I use the VS Code plugin + a locally installed package

### Installing

#### LibGuides

Note: Ideally, you would just reuse and map an existing Library Search Box widget; follow these instructions if you need to create a new one.

1. Create a guide if you haven't already
2. Create a box with the title "Library Search Box(es)"
3. Click "Add / Reorder"
4. Select "Media / Widget"
5. Name your widget something like "UNH <CAMPUS> Library Search Box"
6. Paste the appropriate code from this repository into the "Embed Code" box
7. Click save

#### Local System for Editing

1. Install the most recent LTS version of Node.js and npm

I use [nvm](https://github.com/nvm-sh/nvm) (specifically, [a plugin](https://github.com/lukechilds/zsh-nvm) for [Oh My Zsh](https://ohmyz.sh/)) to manage my Node.js installs, but you can download directly from the [Node.js website](https://nodejs.dev/)

```sh
nvm install --lts
nvm install-latest-npm
```

2. Install Yarn globally

```sh
npm install -g yarn
```

3. Clone this repository in your desired location

```sh
git clone https://github.com/jlcolbert/unh-library-search-box.git
```

4. Move into the repository

```sh
cd unh-library-search-box
```

5. Install Yarn packages

```sh
yarn install
```

6. Create feature branch

You can do this in two ways:

- Traditional git

  1. Use `git checkout develop` to move to the development branch
  2. Create a feature branch using `git branch feature/feature-name`
  3. Move to your feature branch using `git checkout feature/feature-name`

- HubFlow
  1. Move to your home directory using `cd`
  2. Install HubFlow:
  ```sh
  git clone https://github.com/datasift/gitflow
  cd gitflow
  sudo ./install.sh
  ```
  3. Move back into this repository and initialize HubFlow:
  ```sh
  cd
  cd unh-library-search-box # or cd <PATH TO REPOSITORY>
  git hf init
  ```
  4. Create your feature branch with `git hf feature start feature-name`

7. Make edits

If you have Prettier configured in your editor, it should format on save or at least tell you what's wrong. If not installed as a plugin, you'll have to do this manually

```sh
yarn prettier --write .
```

8. Push your edits to GitHub

```sh
git push
```

or

```sh
git hf push
```

9. Create a pull request (to develop from feature/feature-name) on the GitHub website

### Issues

If you do not feel comfortable editing the code yourself, create an issue in the GitHub repository or email Jay L. Colbert at [jay dot colbert at unh dot edu](mailto:jay.colbert@unh.edu).

## Usage <a name="usage"></a>

Use the advanced code for larger boxes with a link out to Advanced Search. This is preferred for solo boxes.
Use the basic code for smaller boxes.
Use the multiple code for all three boxes in one widget.
