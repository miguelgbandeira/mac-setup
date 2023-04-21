# Mac setup

## Homebrew / Terminal / Shell

### Homebrew

[Homebrew](https://brew.sh/) allows us to install tools and apps from the command line.

To install it, open up the built in `Terminal` app and run this command:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This will also install the xcode build tools which is needed by many other developer tools.

After Homebrew is done installing, we will use it to install everything else we need.

### Terminal

```
brew install iterm2
```

Once installed, launch it and customize the settings / preferences to your liking. These are my preferred settings:

* Appearance
  * Theme
    * Minimal
* Profiles
  * Default
      * General -> Working Directory -> Reuse previous session's directory
      * Colors -> Basic Colors -> Foreground -> Lime Green
      * Text -> Font -> Anonymous Pro
          * You can download this font [here](https://www.marksimonson.com/fonts/view/anonymous-pro).
          * I use this font in VS Code as well
      * Text -> Font Size -> 36
          * I use my Macbook to present / teach, so a big font size is important so everyone can see the commands I'm typing
      * Keys -> Key Mappings -> Presets -> Natural Text Editing
          * This allows me to use the [keyboard shortcuts](https://gist.github.com/w3cj/022081eda22081b82c52) I know and love inside of iTerm2

#### Install the latest version of git

My Mac came with `git` version `2.32.1`, we can use brew to install the latest version of `git`:

```sh
git --version
brew install git
```

Open a new tab / window to start using the latest version:

```sh
git --version
```

Configure git with your name / email and preferred editor:

```sh
git config --global user.name miguelbandeira

git config --global core.editor nano
```

## OS Productivity

### Window Management

```sh
brew install rectangle
```

### App Switching

```sh
brew install alt-tab
```

### Quick Launching

```sh
brew install alfred
```

## Other Apps I Use Daily

```sh
xargs brew install < apps.txt
```

## OS Settings

These are my preferred settings for `Finder` and the `Dock`.

### Finder

* Finder -> Preferences
  * General -> Show these on the desktop -> Select None
      * I try to keep my desktop completely clean.
  * General -> New Finder windows show -> Home Folder
      * I prefer to see my home folder in each new finder window instead of recent documents
  * Advanced -> Show all filename extensions -> Yes
  * Advanced -> Show warning before changing an extension -> No
  * Advanced -> When performing a search -> Search the current folder
* View
  * Show Status Bar
  * Show Path Bar
  * Show Tab Bar

### Dock

I don't use the Dock at all. It takes up screen space, and I can use Alfred to launch apps and AltTab to switch between apps. I make the dock as small as possible and auto hide it.

* System Preferences
  * Dock & Menu Bar
      * Size -> Small as possible
      * Position on screen -> Right
      * Automatically hide and show the Dock -> Yes

## Menu Bar Customization

### System Stats Widgets

I like to see my network traffic, CPU temp / usage and RAM usage at a glance.

I used to use [iStat Menus](https://bjango.com/mac/istatmenus/), but a few people in my twitch chat pointed me to [stats](https://github.com/exelban/stats), a FOSS menu bar stats app. I tried it out, and I like it so far.

In each widget, a key setting to look for is under "widget settings", choose "merge widgets into one".

```sh
brew install stats
```

### Menu Bar Calendar

I like to have a calendar in the menu bar that I can quickly look at. stats does not include one, so I found [itsycal](https://www.mowglii.com/itsycal/). It seems fine for my needs.

```sh
brew install itsycal
```

itsycal shows the date, so I hide the date in the system menu bar widget:

* System Preferences
  * Dock & Menu Bar
      * Clock
          * Show Date -> Never
          * Show Day of Week -> No

## Web Browser

### Firefox

I use Firefox because it is open source and comes from the [Mozilla Foundation](https://www.mozilla.org/en-US/about/manifesto/), a non profit company that [respects my privacy](https://www.mozilla.org/en-US/firefox/privacy/).

I use the following extensions to protect my privacy while browsing the web:

* Adblocker - [uBlock Origin](https://github.com/gorhill/uBlock)
* Tracker Blocker - [Privacy Badger](https://privacybadger.org/)
  * Firefox now includes tracker blocking, but I leave Privacy Badger enabled.
* [Cookie Autodelete](https://github.com/Cookie-AutoDelete/Cookie-AutoDelete)
  * Removes cookies from websites that are not in my whitelist whenever a tab is closed. An additional precaution to tracker blocking.
* [Decentraleyes](https://decentraleyes.org/)
  * Caches CDN links locally and intercepts requests to serve from the cache. Prevents CDNs from tracking you across websites.

## VS Code

VS Code is my preferred code editor.

You can view all of my VS Code settings / extensions [here](https://github.com/CodingGarden/vscode-settings).

2 of the most notable settings are:

```json
{
  "editor.linkedEditing": true,
  "editor.snippetSuggestions": "top",
}
```

* editor.linkedEditing
  * Automatically edit a closing tag when editing an opening tag
* editor.snippetSuggestions
  * Puts the most relevant auto complete options at the top


