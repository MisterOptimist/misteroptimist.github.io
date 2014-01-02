---
layout: post
title: "Testing is fun!"
date: 2013-09-12 11:49
comments: true
categories: [ruby,rails,testing,tutorial]
keywords: ruby,rails,testing,factorygirl,rspec,fixtures
descripton: Here is how to setup FactoryGirl and Rspec in your rails app.
---
Today I setup FactoryGirl and Rspec in my rails app. 
Its fairly easy to do, here is how I did it and got my first Test to pass.


Add this code to your gemfile. Then run bundle to install them.

````
gem 'factory_girl_rails'
gem 'rspec-rails', '~> 2.0'
````
  


Then changed up some configs

````
 config.generators do|g|
    g.test_framework :rspec,
      fixtures: true,
      view_specs: false,
      helper_specs: false,
      routing_specs: false,
      controller_specs: true,
      request_specs: false
    g.fixture_replacement :factory_girl, dir: "spec/factories"
   end
````
   
Then I had created a spec for my user model. (I'm using devise by the way.) Just create a new file in your <code>spec/models</code> directory called <code>user_spec.rb</code>. Or you know, whatever you are going to add specs for. Then we are going to go ahead and test that the user has a valid factory. Don't worry this should fail.


````
 require 'spec_helper'

describe User do
	it "has a valid factory" do 
   expect(FactoryGirl.build(:user)).to be_valid
	end
 end
````


Next we're going to manually create a folder in our spec file called  <code>factories</code>. We're going to create a new file called <code>users.rb</code>. **Note:** Make sure that whatever name you use is plurarl or you could run into errors.

Now lets add in our code to create a new Factory.

````
 FactoryGirl.define do 
		factory :user do		
		name "Casey"
		password "123456789"
 		joined_staff "2013/09/09"
 		email "testemail@example.com"
 	end
 end
````

 Some of this code is self explanitory but lets break it down a little bit.

<code>name "Casey"</code> - This just sets this factories name to "Casey".

<code>password "123456789"</code> - This just sets this factories password to "123456789"

<code>joined_staff "2013/09/09"</code> - This is for my particular application. I require signups to include this information, so I've included it here.

<code>email "testemail@example.com"</code> - This just sets this factories email to "testemail@example.com"

**Note: This is just a basic example of how to setup a factory. You can input any column data that pertains to your particular database.**

Then run <code>rspec</code> in your terminal. It should pass! Congratulations! you just ran your first rspec test to test if you had a valid factory!

In the words of *Red* from *The Red Green Show* - **Remember, I'm pulling for you. We're all in this together.**
   
