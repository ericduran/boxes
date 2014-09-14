Boxes - Ansible MAC Playbook
========

Ansible mac playbook for developers

Quickly get up on running on a new mac.

###What's installed:

- #### CLI Applications
 - drush 
 - Git 2.0
 - [hub](https://hub.github.com/) - Adds github integration to git
 - [siege](http://www.joedog.org/siege-home/) - A better Apache Bench
 - Vagrant
 - VIM 7.4

- #### Applications
 - Alfred2
 - Caffeine
 - [Charles Proxy](http://www.charlesproxy.com/) - An HTTP proxy/monitor/reverse proxy
 - Firefox
 - Firefox Aurora - Newest of the new Firefox features 
 - Google Chrome
 - Google Chrome Canary - Newest of the new Chrome features
 - Join.me - Quick and Easy screen sharing
 - PHPStorm (& java6)
 - Sequel Pro - The missing MySQL Database manager
 - Slack
 - SublimeText2
 - VirtualBox

##Installation Steps :
 1. Install homebrew:
   
   ```sh
     ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
   ```
   Make sure brew is good by running ```brew doctor```

 1. Install Homebrew cask:

    ```sh
       brew install caskroom/cask/brew-cask
    ```
    
 1. Install Ansible:
    ```sh
     #Note: If you're on OSX Yosemite (10.10) you must 1st patch ansible!
     brew install ansible
    ```
    Patching Instructions Below (Skip if you're not on OSX Yosemite).
    1. ```brew edit ansible```
    2. Paste the following snippet after "head 'https://github.com/ansible/ansible.git', :branch => 'devel’"

      ```ruby
      patch do
        url "https://github.com/ansible/ansible/pull/8171.patch"
      end
      ```

    3. ```brew install ansible```
    


## Running on your MAC

 ```sh
 ansible-playbook -i hosts mac.yml
 ```
 
 or
  ```sh
 ## Small wrapper around `ansible-playbook -i hosts mac.yml`
 ## Tip: symlink boxes to /usr/local/bin/boxes for easier access.
 ./bin/boxes 
 ```
 
