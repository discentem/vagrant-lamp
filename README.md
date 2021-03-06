## Problem

Students in my INFS-375 Database Programming class currently have access to a LAMP stack administered by the IT Dept.

I wanted full control over the stack and to give myself and other students the ability to see behind the curtain, mess up, tear the server down, and to easily get running again.

## Solution -- In development

Use Vagrant and Chef to provide an easy/automated way to create/tear-down/customize a LAMP stack.

## Dependencies: You must install the following software before *Getting Started*.
1. https://git-scm.com/
2. https://www.vagrantup.com/
3. https://www.virtualbox.org/wiki/VirtualBox

## Getting Started
Note: *All paths referenced in the following instructions are relative to the root of this project.* Therefore, keep track of where you clone or save the project.

1. Clone this repository by running the following command in `Terminal` (if on macOS) or `Powershell` (if on Windows):`git clone https://github.com/discentem/vagrant-lamp.git`.

Alternatively, you can download the project by clicking `Clone or Download` and `Download Zip`. You will need to extract the project if downloading the project as a zip file.

2. Advised: You should change the default MySQL password in `cookbooks/bk_mysql/attributes/default.rb` before running this virtual machine.
3. Next, launch `Terminal` (if on macOS) or `Powershell` (if on Windows) and navigate to the project root. If your copy of the project is stored in your downloads, for instance, you can run the following to navigate to the project root: `cd ~/Downloads/vagrant-lamp`.
4. Run the following command from the project directory: `vagrant up`. This will create a virtual machine as defined by the code in `./Vagrantfile`. If you want to destroy the virtual, run `vagrant destroy` and then `vagrant up` to get a fresh virtual machine. 

**Make sure you save your files in an external location before running `vagrant destroy`!!**

Visit https://www.vagrantup.com/docs/cli/ for a full list of available `vagrant` commands.

5. Profit! You should now have a Ubuntu virtual machine running a LAMP stack. You can ssh to it with `vagrant ssh`. Your website should be accessible in a web browser `localhost:8080`.

- You can ssh or sftp to server at `localhost:2222` with username:`vagrant` and password:`vagrant`. The website files will be found at `/var/www/*`.
- From the server, you can access `mysql` with the following command: `sudo mysql -h 127.0.0.1 -p`. The default sql password is `mysqldefault`.

## Contributing/Development

If you would like to make major changes to the Chef code found in the project, mostly found in `./cookbooks`, install `Ruby` (https://www.ruby-lang.org/en/downloads/) and `test-kitchen` (https://github.com/test-kitchen/test-kitchen). Chef changes are easier and faster to test inside `test-kitchen`. I've included a `.kitchen.yml` which configures `test-kitchen` with some useful options.

Pull requests are welcome.
