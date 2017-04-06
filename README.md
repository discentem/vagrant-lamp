## Problem

Students in my INFS-375 Database Programming class currently have access to a LAMP stack administered by the IT Dept.

I wanted full control over the stack and to give myself and other students the ability to see behind the curtain, mess up, tear the server down, and to easily get running again.

## Solution -- In development

Use Vagrant and Chef to provide an easy/automated way to create/tear-down/customize a LAMP stack.

## Dependencies
1. https://git-scm.com/
2. https://www.vagrantup.com/
3. https://www.virtualbox.org/wiki/VirtualBox

## Usage

1. Clone or download this repository.
2. Advised: You should change the default MySQL password in `/Users/Brandon/Documents/vagrant-lamp/cookbooks/bk_mysql/attributes/default.rb` before running this virtual machine.
3. Next, inside of the project root, run `vagrant up`. This will create a virtual machine as defined by the code in `./Vagrantfile`.

## Development

If you would like to make major changes to the Chef code, found in `./cookbooks`, install `Ruby` (https://www.ruby-lang.org/en/downloads/) and `test-kitchen` (https://github.com/test-kitchen/test-kitchen). Chef changes are easier and faster to test inside `test-kitchen`. I've included a `.kitchen.yml` which configures `test-kitchen` with some useful options.
