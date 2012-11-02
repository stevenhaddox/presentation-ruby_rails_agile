# ruby_rails_agile

!SLIDE left

# Ruby, Rails, and the Agile Ecosystem

<dl>
  <dt>Presented by:</dt>
    <dd><a href="http://stevenhaddox.com">Steven Haddox</a></dd>
  <dt>Company:</dt>
    <dd><a href="http://blackoakweb.com">Fusion Technology, LLC</a></dd>
  <dt>Blog:</dt>
    <dd><a href="http://blog.stevenhaddox.com">http://blog.stevenhaddox.com</a></dd>
  <dt>Twitter:</dt>
    <dd><a href="http://twitter.com/stevenhaddox">http://twitter.com/stevenhaddox</a></dd>
</dl>

!SLIDE small left

## Overview

* Ruby vs. The World
* Ruby's Strengths
* Ruby's Weaknesses
* Ruby Basics
* Benefits of Rails MVC
* It's About Community
* Community::Gems
* Best Practices::Agile
* Best Practices::Testing: BDD, TDD, FTW
* Best Practices::Deploying
* Best Practices::RVM/Bundler

!SLIDE small left

## Ruby Strengths

* Cross-platform (Windows, Linux, OS X)
* "Elegant" &amp; "Beautiful" code
* Frameworks &amp; Community
* Everything is an Object
* Duck Typing / Monkeypatching
* Method Chaining
* Blocks &amp; Lambdas
* Metaprogramming &amp; DSLs
* Extensible &amp; Dynamic
* 1.9.2 improves threading, still not as good as Java

!SLIDE small left

## The 80% Language

* [The 0.8 Language](http://confreaks.net/videos/159-rubyconf2009-keynote-address):  
  http://confreaks.net/videos/159-rubyconf2009-keynote-address
* It's not The One True Language
* but the 0.8 true language
* Worth a watch to see the creator of Ruby discuss why :)


!SLIDE small left

## Ruby Weaknesses

* Who's heard that Ruby doesn't scale?
* Who still believes it (keep your hands up)
* Try telling that to:
  * Twitter
  * YellowPages
  * Hulu
  * Scrib'd
  * Justin.tv
  * LivingSocial
  * Groupon

!SLIDE small left

## Actual Weaknesses

* Performance isn't as good as Java, C++, other compiled languages
* Not specific to Ruby, but worth mentioning
* Threading isn't true threading in Ruby &lt; 1.9
* Limited quantity of Rubyists (is this actually a bad thing as a Ruby developer?)
* Doesn't compile and therefore harder to protect code
* Non-static types (depends upon your perspective)

!SLIDE

# Basic Syntax Examples

!SLIDE small

## Loops

``` ruby
presentations = YAML::load_file('config/presentations.yml')
presentations.each do |pres|
  system("git clone #{pres[:url]} pres/#{pres[:folder]}")
end

for i in 1..8 do
  puts i
end

5.times { puts "Ruby reads like English!" }

1.upto(5) { |i| puts i }
15.downto(10) {|i| puts i }
```

!SLIDE small

## More Loops

``` ruby
i = 0
while i < 5 do
  puts i
  i += 1
end

i = 0
until i == 5
  puts i
  i += 1
end

unless i >= 10
  puts "Student failed"
else
  puts "Student passed"
end
```

!SLIDE

## Method Chaining

``` ruby
presentations = {"agile" => 4, "ruby" =>  1, "rails" => 2, "jruby" => 3}
sorted_presentations = presentations.keys.sort
```

## Blocks

``` ruby
presentations.sort do |a, b|
  a.counts <=> b.counts
end
```

!SLIDE small

## Monkeypatching

``` ruby
class String
  def is_int?
    self =~ /^[-+]?[0-9]*$/
  end
end
```

!SLIDE left

### Popular Frameworks &amp; Tools

* Ruby on Rails
* <strike>Merb</strike>
* Sinatra
* Capistrano
* Bundler
* RVM


!SLIDE

# Ruby on Rails

!SLIDE small left

## Benefits

* Model-View-Controller
* ORM
* ActiveRecord (DB Abstraction)
* MySQL, Oracle, PostgreSQL, SQLite3 all work easily
* Database migrations
* Performance of SQL via ARel
* Templates
* DRY!!!
* Security
* Testing
* Easy Web Server Integration (Apache & Nginx via Passenger, Mongrel, Thin, Unicorn)
* If you acquire a Rails application you'll know where everything is immediately

!SLIDE left

### Convention > Configuration

* Do you develop web applications for any reason?
* We all face common issues:
* Routing requests
* Processing forms &amp; loading / display submitted data
* DB interactions
* etc.

!SLIDE left

### Convention > Configuration

* Rails groups together best-practices for conventions of handling all these basic problems and wraps them up in an easy to use package. There's a learning curve, but once you get it down it makes developing web applications considerably faster, more stable, and well tested (if you follow best practices).
* You also benefit from a huge community of support for deployments, development help, tools built on top of Rails, etc.

!SLIDE small left

### Community

* It's what sets Ruby apart from other languages
* Gems
* Common Frameworks
* Unifying for the best solution as a whole
* User Groups throughout the country  
[B'more on Rails](http://bmoreonrails.org), [DCRUG](http://www.meetup.com/dcruby), [Nova RUG](http://www.novarug.org/), [Frederick Riding Rails](http://frederickridingrails.org)
* Very active support forums
* IRC
* Twitter
* Conferences!
* RubyConf: [http://rubyconf.org](http://rubyconf.org)
* RailsConf: [http://railsconf.org](http://railsconf.org)
* RubyNation: [http://rubynation.org](http://rubynation.org)

!SLIDE left

## Which Gems are Commonly Used?

* How do you decide which gems are most popular?
* Ruby Toolbox: [http://ruby-toolbox.com](http://ruby-toolbox.com)
* RubyGems: [http://rubygems.org](http://rubygems.org)

!SLIDE small left

## Gems Worth Knowing

* Bundler
* RVM
* Devise / OmniAuth
* CanCan
* factory\_girl
* cucumber / cucumber-rails
* rspec / shoulda
* formtastic
* will\_paginate
* json
* datamapper

!SLIDE left

## Rubyists &lt;3 Best Practices

* Agile development methodology
* Testing! BDD / TDD
* Bundler for gem management
* RVM for development environment
* RVM can be used for production as well (WE DO!)
* Capistrano for deployments (generally)

!SLIDE center small

### Agile Manifesto

We are uncovering better ways of developing  
software by doing it and helping others do it.  
Through this work we have come to value:

* <span class="agile_left">Individuals and interactions</span> over <span class="agile_right">processes and tools</span>
* <span class="agile_left">Working software</span> over <span class="agile_right">comprehensive documentation</span>
* <span class="agile_left">Customer collaboration</span> over <span class="agile_right">contract negotiation</span>
* <span class="agile_left">Responding to change</span> over <span class="agile_right">following a plan</span>

That is, while there is value in the items on  
the right, we value the items on the left more.

[http://agilemanifesto.org](http://agilemanifesto.org/)

!SLIDE left

## Testing

* Cucumber for integration tests
* Works with non-Ruby languages via built-in browser
* RSpec / Shoulda for unit &amp; acceptance tests
* Test::Unit / minitest are valid & built-in

!SLIDE

### Sample Cucumber Feature

    Given I am on the home page
    And I login as "rubyist@email.com"
    Then I should see "Welcome, Rubyist"

!SLIDE left

## RVM

* Simple development environment
* Allows you to easily install multiple Rubies in your home folder
* Gives you gemsets to isolate gems by projects
* Avoids headaches, conflicts, and solves world hunger

!SLIDE

## RVM is EASY 

``` sh
$ gem install rvm
$ rvm-install # installs RVM command
$ rvm install 1.8.7
$ rvm install 1.9.2
$ rvm install ree
$ rvm install jruby
$ rvm install macruby
$ rvm use 1.9.2
$ rvm gemset create bah
$ rvm gemset use bah
$ gem install 'bundler'
```

!SLIDE left small

## Bundler

* Bundler organizes gems per project
* Handles dependencies
* Identifies best gem version to use amongst all gems
* Allows for certain gems per environment (development, test, production, etc)
* Packages gem locally for deploy install if no gemserver is available:
* <pre class="sh_sh sh_sourceCode"><code>$ bundle package</code></pre> 

!SLIDE

## Bundler is EASY

``` sh
$ gem install bundler
$ touch Gemfile
# Create your Gemfile
$ bundle install
$ bundle exec (rails|cap|showoff|etc)
```

!SLIDE left

### Capistrano for Deployments:

* One primary config file to deploy to multiple servers
* One specific file per environment for unique settings
* Symlinks all config files on the serve from a shared folder to the current deploy folder

!SLIDE left

### config/deploy.rb :: Config

``` ruby
#bundler and multi-stage recipe hooks
#require 'bundler/capistrano' # still broken in 1.0.7?
set :stages, %w(dev staging prod)
require 'capistrano/ext/multistage'
set :default_stage, "dev"

# global defaults
set :application, "domain.com"

# Git config
set :scm, :git
set :repository,  "git@github.com:stevenhaddox/domain.com.git"
set :branch, "master"

# SSH config
ssh_options[:forward_agent] = true
set :use_sudo, false
set :user, "steven"
```

!SLIDE small left

### config/deploy.rb :: Tasks

``` ruby
# test task
task :uname do
  run "uname -a"
end

namespace :symlinks do
  desc "Create shared symlinks"
  task :db, :roles => :app do
    run "ln -nfs #{shared_path}/system/database.yml #{release_path}/config/database.yml"
  end
  task :log, :roles => :app do
    run "ln -nfs #{shared_path}/log #{release_path}/log"
  end
end

desc "Install bundled gems into shared/bundle"
task :bundle do
  run "ln -nfs #{shared_path}/bundle #{release_path}/vendor/bundle"
  run "cd #{release_path}; bundle install --deployment"
end

namespace :deploy do
  task :start do ; end
  task :stop do ; end
  task :restart, :roles => :app, :except => { :no_release => true } do
    run "#{try_sudo} touch #{File.join(current_path,'tmp','restart.txt')}"
  end
end
```

!SLIDE left

### conig/deploy.rb :: Callbacks

``` ruby
# callbacks
after 'deploy:update_code', 'symlinks:db'       # update db symlink
after 'deploy:update_code', 'symlinks:log'      # update log symlink
after 'deploy:update_code', 'bundle'            # install bundler gems for Passenger
after 'deploy', 'deploy:cleanup'                # keep only last 5 deployed versions
after 'deploy:migrations', 'deploy:cleanup'     # keep only last 5 deployed versions
```

!SLIDE
# Questions?

## Seriously, ask anything...

!SLIDE small left

### Resources to Learn Ruby/Rails

### Screencasts / Digital

* [TryRuby](http://tryruby.org/): http://tryruby.org
* [Peepcode](http://peepcode.com): http://peepcode.com
* [Rails Tutorial](http://ruby.railstutorial.org/): http://ruby.railstutorial.org
* [Pragmatic Studio: Learn Ruby](https://pragmaticstudio.com/ruby/): https://pragmaticstudio.com/ruby
* [Rails Guides](http://guides.rubyonrails.org): http://guides.rubyonrails.org
* [Ruby Learning](http://rubylearning.com): http://rubylearning.com
* [Ruby in 20 Minutes](http://www.ruby-lang.org/en/documentation/quickstart/):  
http://www.ruby-lang.org/en/documentation/quickstart/
* [Ruby](http://ruby-lang.org): http://ruby-lang.org
* [Ruby on Rails](http://rubyonrails.org): http://rubyonrails.org
* [RVM](http://rvm.beginrescueend.com): http://rvm.beginrescueend.com
* [Bundler](http://gembundler.com): http://gembundler.com
* [RailsInstaller](http://railsinstaller.org/): http://railsinstaller.org
* [RubyGems](http://rubygems.org): http://rubygems.org
* [RubyToolbox](http://ruby-toolbox.com): http://ruby-toolbox.com

!SLIDE small left

### Resources to Learn Ruby/Rails

### Books ###

* Pragmatic Programmer's == win!
* Programming Ruby (aka "the Pickaxe book") by Dave Thomas (for Ruby 1.9.2)
* Agile Web Development with Rails (4th ed)
* The RSpec Book (BDD & TDD using Cucumber and RSpec) &lt;-- useful for any language!
* Ruby Best Practices by Gregory Brown
* The Pragmatic Programmer
* Practices of an Agile Developer

!SLIDE small left

### Technologies used for this presentation

* [Keydown Gem](https://github.com/infews/keydown "Keydown gem"):  
https://github.com/infews/keydown
* [Sinatra](http://www.sinatrarb.com/ "Sinatra"):  
http://www.sinatrarb.com/
* [Markown Syntax](http://daringfireball.net/projects/markdown "Markdown by John Gruber"):  
http://daringfireball.net/projects/markdown
* [Bundler](http://gembundler.com):  
http://gembundler.com

!SLIDE small left

### Sources used for presentation

* [Why Ruby?](http://www.scholarslab.org/slab-code/why-ruby/ "Why Ruby?"):  
http://www.scholarslab.org/slab-code/why-ruby/
* [Java vs Ruby: a quick and fair comparison](http://www.slideshare.net/Belighted/ruby-vs-java "Java vs Ruby")*:  
http://www.slideshare.net/Belighted/ruby-vs-java
* [C++ vs Java vs Python vs Ruby](http://www.dmh2000.com/cjpr/)*:  
http://www.dmh2000.com/cjpr/
* [Agile Manifesto](http://agilemanifesto.org/):  
http://agilemanifesto.org/
* [Ruby Scales, AND It's Fast](http://www.engineyard.com/blog/2010/architecture-wins-varnish-and-more/):  
http://www.engineyard.com/blog/2010/architecture-wins-varnish-and-more/

\* Denotes a technical presentation from 2006, take with a grain of salt for all comparisons
