
### Installation

Getting Jekyll installed and ready-to-go should only take a few minutes.

Installing Jekyll is easy and straight-forward, but there are a few requirements you’ll need to make sure your system has before you start:

* Ruby

* RubyGems

<!-- vertical-slide -->

### Ruby

![Ruby Logo]({{ "assets/images/ruby.png" }}){:height="18%" width="18%"}

### Debian or Ubuntu

On Debian GNU/Linux and Ubuntu use the **apt package manager**:

```sh
~ $ sudo apt-get install ruby-full
```

### Windows

On Windows, there is an installer:

* RubyInstaller: [https://rubyinstaller.org/](https://rubyinstaller.org/)

<!-- vertical-slide -->

### RubyGems

![Ruby Gems Logo]({{ "assets/images/rubygems_logo_red.png" }}){:height="20%" width="20%"}

* Download from [https://rubygems.org/pages/download](https://rubygems.org/pages/download)

* Unpack into a directory and cd there & Install (you may need admin/root privilege)

```sh
~ $ wget http://production.cf.rubygems.org/rubygems/rubygems-2.6.10.tgz
~ $ tar xvf rubygems-2.6.10.tgz
~ $ cd rubygems-2.6.10
~ $ ruby setup.rb
```

<!-- vertical-slide -->


### Jekyll

![Jekyll Logo]({{ "assets/images/jekyll-logo-dark-transparent.png" }}){:height="30%" width="30%"}

Install Jekyll as a ruby gem:

```sh
~ $ gem install jekyll
```

<!-- next-slide -->