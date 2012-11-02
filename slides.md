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

!SLIDE left small

### Popular Frameworks &amp; Tools

* Ruby on Rails
* <strike>Merb</strike>
* Sinatra
* Capistrano
* Bundler
* RVM





!SLIDE

# Some sample code

``` ruby
def method
  puts "Hello, World"
end
```

!NOTES

 * a note

!SLIDE

# With a Background Image

}}} images/test.png
