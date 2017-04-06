## The Problem

Students in my INFS-375 Database Programming class currently have access to a LAMP stack administered by the IT Dept.

I wanted full control over the stack and to give myself and other students the ability to see behind the curtain, mess up, tear the server down, and to easily get running again.

## Solution

Provide an easy, automated to create/tear-down/customize a LAMP stack.

## Dependencies
1. https://www.vagrantup.com/
Vagrant must be installed. Vagrant is available for all major operating systems.

2. https://www.virtualbox.org/wiki/VirtualBox
Current the Vagrant box (`config.vm.box`) defined in the Vagrantfile (`./Vagrantfile`) is only compatible with `Virtualbox`. Search https://atlas.hashicorp.com/ if you need a box which runs on another provider. For example, you can replace `hashicorp/precise64` with `luderson/ubuntu-1604-hyperv` for a Hyper-v compatible box.

For information on what a box is, visit https://www.vagrantup.com/docs/boxes.html.

## Usage

Clone or download this repository. Next, inside of the project root, run `vagrant up`. This will create a virtual machine as defined by the code in `./Vagrantfile`.

## Development

If you would like to make major changes to the Chef code, found in `./cookbooks`, visit install Ruby (https://www.ruby-lang.org/en/downloads/) and `test-kitchen` (https://github.com/test-kitchen/test-kitchen). Chef changes are easier and faster to test inside `test-kitchen`. I've included a `.kitchen.yml` which configures `test-kitchen` with some useful options.