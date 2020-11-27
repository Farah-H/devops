# Vagrant and VM Provisioning

## Core Sections of provisioning
- There are some actions that are core to provisioning 
- These concepts are tool and language agnostic 
    - making files available
    - being able to run  commands/scripts
    - injecting environment variables 

## Synching in files with VM
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.network "private_network", ip: "192.168.10.100"
  #config.hostsupdater.aliases = ["development.local"]
  config.vm.synced_folder "app", "/app"

end
```

## Running a Basg script 
This bashscript can install packages, alter files, do actionsin our linux servers when we run vagrant up. This will allow us to set up the machine to a state that is desirable for us and allows us to automate processes. 
1. Create a `provision.sh` file
2. include it in vagrant file
## Managing services

- `sudo systemctl <action> <service>`
- `sudo systemctl restart nginx`

Provisioning is derived from providing / supplying something. E.g. provisionining for food or water. 

In this context it will be providing our machines with instructions, variables, files and folders. 

This will mean we can set up a machine to a specific state when turned on. 

## Given a new project to create an environment 
When given a new project, you want to ask a few questions to help you get going, for example:
- what language is it in?
    - code in JS and others
    - some tests in ruby and rspec
- is there a framework to install?
    - no, only the testing framework: rspec
- any specfiic packages? is there a list? 
    - yes, with the environment file, you have a gemfile with dependencies
- any tests?
    - Yes you have integration tests to run outside the machine
    - rake spec
    - also there ight be some unit tests in JS inside

## gem and bundler vs PIP and packages 
- Gems are packages in ruby or dependencies
- bundler is ruby's package manager
- To install gems from Genfile, you run:
`bundle install`
 ## Ruby's testing framework is rspec
 - rspec needs to be installed 
 ## JS package manager is npm (node package manager)
 - npm packages
 - after version 6 comes pre loaded with NPM

 ## Ubuntu package manager : `apt`
 - apt-get
 - mostly depreciated now

 ## installing test
 1. to the dolfer with femfile
 2. run `bundle`

 ## running test : `rake spec`