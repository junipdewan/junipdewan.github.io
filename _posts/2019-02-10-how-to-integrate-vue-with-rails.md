---
layout: post
title: "How to Integrate Vuejs With Rails Part 1"
date: 2018-02-11 05:05:05 +0530
comments: true
categories: 
---

== description
    Vuejs is an open source javascript framework for building user interface and single page application.Now a days it is getting very popular.
    Rails provide already erb template which is rendered through controller used in view.It is better approach to use any other framework with rails
    Vue/React gives you the robust code and maintainability. 


    This post will help you to learn to Integrate your rails application  with vuejs and you can also think of to migrate your old application to Vue.js
    Normally rails have the asset pipeline to compile the assets and javascript, images etc. We will use webpack for the bundling javascript, assets, images
    The webpacker gem gives the functionality to use webpack. 

    Make sure that you have node and yarn installed in your machine if not then install node and yarn first using the link

    Installing Rails & Ruby `https://gorails.com/setup/ubuntu/16.04` 
    Installing yarn https://yarnpkg.com/lang/en/docs/install/

    Installing Node ` `
    

    you will need yarn to install webpacker gem to work . link to install yarn

    create a new rails and vue app and go to your gem file install the gem. after installing the gem run `rails::install::webpacker`
    this command will generate the webpacker file there you will find the config yml setting fo your application.

    this will generate the javascript/packs/application.js file



== webpacker


== integeration



== conclusion

Vue.js is an open-source JavaScript framework for building user interfaces and single-page applications. Rails has We will use Webpack to bundle our javascript. The Webpacker gem in rails makes it easy to use the JavaScript pre-processor and uses webpack to bundle mainly javascript, CSS, images, and fonts assets as well.It manages the application-like javascript in Rails.

Prerequisites to install the Webpacker gem

    * Ruby 2.2+
    * Rails 4.2+
    * Node.js 6.14.4+
    * Yarn 1.x+

Step 1.  Create a new Rails App. Run the command `rails new rails-webpack-vue`

Step 2.  Add gem ‘webpacker’ in the gem file, and later run bundle install
                 
Step 3.  After installing webpacker gem, run the command rails webpacker::install. 

This command will create a directory app/javascript/packs/application.js.This javascript folder that is created is different from the app/asset/javascript folder. All your javascript file for React/Vue will reside in this folder. After this will require a separate process to monitor all the javascript, we have to run bin/webpack-dev-server in side by side. In Rails your all assets are managed by rails assets pipeline. So you have to include the ‘javascript_pack_tag’ in application.html.erb to allow monitor the javascript changes by the webpacker

Step 4. Run the command bin/webpack-dev-server. 

When you run webpack-dev-server, the server will be running "http://localhost:3035”.You have to include in “javascript-pack-tag” in the application.html.erb. This will link them to the port  3035 of web pack-dev-server. You can change the entry point for your application in config/webpacker.yml.
 
Step 6. Generate one controller with rails scaffold for example, rails g scaffold Company name: string address: string

Step 7.  Run localhost:3000/companies.Inspect the browser you will get a message in console “Hello from webpacker” .For now, Webpacker is working. Next step is to install Vue.js

Step 8:  Run rails webpacker:install:vue

This will create and hello_vue.js under the javascript/pack  folder. In application.html.erb, you have to add the <%= javascript_pack_tag “hello_vue” %> and restart the web pack-dev-server.There you will get the Hello Vue message in the browser. You can use like this what ever you want.

You can change your entry point for your frontend files in webpacker.yml, there you have to specify the source_path you want to give and restart the webpack-dev-server. You can also specify the path for additional modules you want to lookup by webpack in an array in resolved_paths.