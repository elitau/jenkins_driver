Jenkins jobs in ruby

### Introduction
jenkins_driver is a whenever like tool to describe your reoccuring jobs in ruby and run them via the Jenkins/Hudson CI server. It's aimed to be compatible with the whenever syntax to describe your jobs. Inspired by <http://fourkitchens.com/blog/2010/05/09/drop-cron-use-hudson-instead> and <http://github.com/javan/whenever>

### Installation
  
    $ gem install jenkins_driver

Or with Bundler in your Gemfile.

    gem 'jenkins_driver', :require => false
 
### Getting started

    $ cd /my/rails/app
    $ rake jenkins_driver:bootstrap

This will create an initial "config/schedule.rb" file you.


### Example schedule.rb file
  
    every 3.hours do
      runner "MyModel.some_process"       
      rake "my:rake:task"                 
      command "/usr/bin/my_great_command"
    end

    every 1.day, :at => '4:30 am' do 
      runner "MyModel.task_to_run_at_four_thirty_in_the_morning"
    end

    every :hour do # Many shortcuts available: :hour, :day, :month, :year, :reboot
      runner "SomeModel.ladeeda"
    end

    every :sunday, :at => '12pm' do # Use any day of the week or :weekend, :weekday 
      runner "Task.do_something_great"
    end

    every '0 0 27-31 * *' do
      command "echo 'you can use raw cron sytax too'"
    end

More examples on the wiki: <http://wiki.github.com/elitau/jenkins_driver/instructions-and-examples>


### How it works
 - write your config/schedule.rb
 - on deployment with capistrano the jobs will be pushed (async) to jenkins over its API
 


