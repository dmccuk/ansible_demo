Devops Test
=========================
TThis has been a great tests to do as was quite a bit of fun. Just for you info, I took a few months off work to travel the world with my Wife and daughters (currently in Thailand. I'm back in April so I've been making contact with UK IT agencies. 

Setup
--------
 1. Install Vagrant. I had to set this all up on Windows (yuck) as my linux laptop is back in the UK.
 2. create you DIR and run vagrant init.
 3. clone this repo: https://github.com/dmccuk/vagrant-devops.git
 4. before you can run it, there are some dependancies. My code requires some puppet modules be setup and available.
 5. Clone this repo onto your puppet master: https://github.com/dmccuk/modules.git **Clone it to a safe place and move the modules into where you normally put them (somewhere like /etc/puppet/modules)** I've included a site.pp as well but you probably won't need it.
 6. Now you can run "vagrant up" and see what happens.
 7. 

My Thoughts
---------
 * [ As part of this I also setup a puppet master in Vagrant (but dont supply the code here). That also required some manual steps which you probably slready know about. ]
 * [ I didn't carry on with the bonus points simply because I'm travelling round the world. My wife is already annoyed with me and I didn;t want to make life worst in the short term for myself. ]
 * [ I decided to put most of the code into the "webapp" module. I would usually create a role for a node along with a profile and the profile would be made up of individual modules to do each job. This method does have the benefit of keeping everything together but doesn't scale so I wouldn't recommend it normally. ]
 * [ for the idempotent bit I used the notify option in puppet. IF a file changes then the notify options will trigger the service specified to be restarted. ]
 * [ For testing the web servers are serving my app, I didn't setup a test, instead if you go to http://127.0.0.1 I added the name of each specific node from facter so it's displayed on the page. As you refresh (F5) you will see the node name flip between one then the other. I n the real world I'm experienced with serverspec and would setup a specific test for the open port, web page contents, etc. ]
 
Thanks

Dennis
