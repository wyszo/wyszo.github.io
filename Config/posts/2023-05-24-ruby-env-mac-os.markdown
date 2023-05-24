---
layout: post
title: "Mac OS Ruby environment setup"
date: 2023-05-24 07:20:00 +0100
permalink: /mac-os-rbenv
---
Quick instructions on how to configure Ruby installation for cocoapods on Mac OS. To avoid installing cocoapods gem with sudo.

## Problem

* On Mac OS, when using ruby version bundled with the system (2.6), trying to install a `gem` (such as `cocoapods`) or `bundler` often results in permission error. 
* This still happens on MacOS Ventura. 
* A lot of people use `sudo gem install` as a workaround just to get it to work. This is a bad practice and it shouldn't be used for installing gems. 


## Solution: install new Ruby version (3.2.2) using rbenv

- Install rbenv through homebrew: `brew install rbenv ruby-build`

- Install the latest stable ruby version `rbenv install -l to find the latest version then ‘even install <version>’.`

- Set global Ruby to that new Ruby installation `rbenv global 3.2.2`

- Add local rbenv ruby path to `.zshrc`: `export PATH="$HOME/.rbenv/bin:$PATH" eval "$(rbenv init -)"`

- If you're getting `command not found: rbenv`, run `echo 'eval $(/opt/homebrew/bin/brew shellenv)' >> ~/.zprofile`

- Ensure everything is working. Run `which ruby` It should give you something like `/Users/<username>/.rbenv/shims/ruby`

- You progably want to install bundler right away: `gem install bundler`


## Alternatives

* `chruby` can be installed instead of `rbenv`. It’s a bit simpler in terms of shell modifications.

