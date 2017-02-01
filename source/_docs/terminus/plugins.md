---
title: Terminus Manual
subtitle: Extend with Plugins
terminuspage: true
type: terminuspage
layout: terminuspage
permalink: docs/terminus/:basename/
---

Extend the functionality of Terminus and add commands by installing third party plugins Those familiar and comfortable with Git or Composer may prefer advanced installation methods provided below.

<div class="alert alert-info">
<h3 class="info">Note</h3>
<p markdown="1">If you are a plugin author, you will need to update your plugin to the Terminus 1.0 syntax. See [Legacy Terminus Versions](/docs/terminus/get-started/legacy) to compare the difference in command syntax.</p>
</div>

## Install Plugins
Add plugins within the `$HOME/.terminus/plugins` directory on your local workstation. You may need to create the `$HOME/.terminus/plugins`` directory if it does not already exist:

<div class="copy-snippet">
<button class="btn btn-default btn-clippy" data-clipboard-target="#terminus-plugin-install-mkdir"><img class="clippy" src="/source/docs/assets/images/clippy.svg" width="17" alt="Copy to clipboard"></button>
<figure><pre id="terminus-plugin-install-mkdir"><code class="command bash" data-lang="bash">mkdir -p $HOME/.terminus/plugins</code></pre></figure>
</div>

Download a zip archive of the plugin's most recent release, then install it by unpacking the archive within `$HOME/.terminus/plugins`:

<div class="copy-snippet">
<button class="btn btn-default btn-clippy" data-clipboard-target="#terminus-plugin-install-curl"><img class="clippy" src="/source/docs/assets/images/clippy.svg" width="17" alt="Copy to clipboard"></button>
<figure><pre id="terminus-plugin-install-curl"><code class="command bash" data-lang="bash">curl https://github.com/pantheon-systems/terminus-plugin-example/archive/1.x.tar.gz -L | tar -C ~/.terminus/plugins -xvz</code></pre></figure>
</div>


<div class="panel panel-default">
  <div class="panel-heading">
  <a data-proofer-ignore data-toggle="collapse" data-target="#advance-installs"><h3 class="panel-title" style="cursor:pointer;">Explore Advanced Install Methods (Optional) <span class="caret"></h3></a>
  </div>
<div id="advance-installs" class="collapse" style="padding:10px;" markdown="1">

### Install via Composer

Plugins published on Packagist are available to install via the Composer package manager. From a terminal window on your computer, use the following commands:

<div class="copy-snippet">
<button class="btn btn-default btn-clippy" data-clipboard-target="#terminus-plugin-install-composer"><img class="clippy" src="/source/docs/assets/images/clippy.svg" width="17" alt="Copy to clipboard"></button>
<figure><pre id="terminus-plugin-install-composer"><code class="command bash" data-lang="bash">composer create-project -n -d $HOME/.terminus/plugins pantheon-systems/terminus-plugin-example:~1
</code></pre></figure>
</div>

### Install via Git

Most plugins are published online as a Git repository. You can install the plugin by cloning the repository into your local plugins directory (`$HOME/.terminus/plugins`). This will allow you to contribute to the development of the plugin and to update the plugin using Git commands. To install a plugin using Git, find the Git URL of the plugin’s repository. On GitHub you can find it by clicking **Clone or download** on the repository home page:

![GitHub clone URL](/source/docs/assets/images/terminus-plugin-install-git.png "GitHub clone URL")

Then in a terminal window on your computer, use the following commands:

<div class="copy-snippet">
<button class="btn btn-default btn-clippy" data-clipboard-target="#terminus-plugin-install-git"><img class="clippy" src="/source/docs/assets/images/clippy.svg" width="17" alt="Copy to clipboard"></button>
<figure><pre id="terminus-plugin-install-git"><code class="command bash" data-lang="bash">cd $HOME/.terminus/plugins
git clone https://github.com/pantheon-systems/terminus-plugin-example.git</code></pre></figure>
</div>
</div>
</div>

## Update Plugins
Delete the plugin from the `$HOME/.terminus/plugins` directory. Download the latest version of the plugin and move the plugin directory into the `$HOME/.terminus/plugins` directory.
## Uninstall Plugins
Delete the plugin from the `$HOME/.terminus/plugins` directory.

<div class="terminus-pager">
  <hr>
  <a style="float:left;" href="/docs/terminus/commands"><span class="terminus-pager-lsaquo">&lsaquo;</span>Commands</a>
  <a style="float:right;" href="/docs/terminus/plugins/directory"><span class="terminus-pager-rsaquo">&rsaquo;</span>Plugin Directory</a>
</div>
