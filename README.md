# Kobot

This is our chatbot. There are many like it, but this one is ours.

![](http://media.giphy.com/media/vPH4IIua3umxG/giphy.gif)

## How to make a handler

Clone this repository

`git clone git@github.com:kollegorna/kobot.git`

`cd kobot`

Add these to your .envrc

`export REDISTOGO_URL=redis://localhost:6379`

`export PORT=3333`
 
Edit lita_config.rb so that it uses :shell adapter instead of :slack

`config.robot.adapter = :shell`

Create your handler in a separate directory

`cd ..`

`lita handler my-cool-handler`

Once you implemented the handler, fillout all the "TODOs" in lita-my-cool-handler.gemspec and push to github

Then:

`cd ../kobot` 

and add your newly created handler to Gemfile:

`gem "lita-my-cool-handler", github: "your-github-name/lita-my-cool-handler"`

`bundle install`

To test your handler, start lita, and send a message to see if it replies (You have to start redis server before this).

`lita start`

Don't forget to change lita_config.rb back to:

`config.robot.adapter = :slack`

Commit your changes, push to github and you're done.

`git commit -m "Add my awesome handler"`

`git push origin master`
