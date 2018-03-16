# Selfhosting - Setup


For this tutorial, we will use an Ubuntu 14 or up system (or virtual machine).

We will assume:
1. You have admin permissions on your system.
2. You run through this tutorial as root.
3. You clone this repo into root's directory, `/root`.

First install redis...
>apt install redis-server
Then python3 and pip3, the interpreter and package index for Python 3, if not installed already:
>apt install python3 python3-pip
Finally, discord.py:
>python3 -m pip install -U https://github.com/rapptz/discord.py/archive/async.zip#egg=discord.py[voice]


The next thing we need to do is clone this repo from github:
>git clone https://github.com/laggycomputer/mee6/

I have included a program to install the requirements, `cd` into the mee6 install location, and run it:
>cd mee6 && sh installRequire.sh

Now that all the dependencies are installed we can move onto confgiuring some of the variables.

export REDIS_URL=redis://localhost

export OAUTH2_CLIENT_ID=Discord client ID for your bot
export OAUTH2_CLIENT_SECRET=your Discord bot's client secret
export MEE6_TOKEN=Your Discord bot token
export OAUTH2_REDIRECT_URI=http://localhost:5000/confirm_login (change to your domain if needed.)

export MAL_USERNAME=username for account on http://myanimelist.net
export MAL_PASSWORD=password for above site

export TWITCH_CLIENT_ID=client ID for a twitch app

export GOOGLE_API_KEY=a youtube api key

export SECRET_KEY=1234 ***Change to a random 4-digit value!***


If you are fine with not having some features work, simply remove the variable value and leave the empty assignment.
We will implement these variables two ways, as a failsafe.

The first way is to paste the above variables into the command line.
The second way is to use:
>cd ~ && nano .bashrc

Press Control-V to go to the end of the document (don't remove anything), and paste in these variables. Save and exit.
(To exit, press Control-X, then Y then Enter.)


#Selfhosting - Running the bot!

To smooth out the booting process, I recommend rebooting your machine at this point.

To start the bot, go to your mee6 repo location (should be a folder called mee6), and do:
>cd mee6/chat-bot/ && python3 bot.py


Open another instance of Terminal, navigate to the mee6 folder, and execute this python file to start the website:
>cd mee6/website/ && python3 app.py

Do note that you may have to reboot after closing the website so that it works again, 
as python does not automatically unbind fron the domain.
#Conclusion

Sadly, I am unable to find enough source code to make everything work, but I do my best!

If you find any issues please feel free to open an issue!


PLEASE NOTE: Not all features may work as this repo is in the process of being updated.

