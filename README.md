# PirateChain (ARRR) Linux Starter
Start using the daemon and the cli of Komodo can be confusing.
Here's a little guide to start the Komodo daemon and interact with Piratechain.

First of all we need to download the compiled sources from here: 
https://github.com/KomodoPlatform/komodo/releases

You can compile itself too, here's a guide directly from Komodo guys:
https://docs.komodoplatform.com/komodo/installation.html#installing-komodo-on-ubuntu-debian

Now we can run the daemon by running:
`./komodod &`

And check if everything is ok by running:
`./komodo-cli getinfo`

If it's all ok you'll be able to see blocks growing: the wallet is syncing.

Now we have to interact with PirateChain. As you can read in official docs you need to run the komodod with specific parameters. I've found this parameters (thanks to @radix42) in the website: https://pirate.guru/

So we need to close the komodod by running:
`pkill komodod`

And start again with specific parameters:
`./komodod -ac_name=PIRATE -ac_supply=0 -ac_reward=25600000000 -ac_halving=77777 -ac_private=1 -addnode=136.243.102.225 -daemon=1 -server=1 -showmetrics=0`

We'll be able to run again getinfo, don't forget the -ac_name parameter:
`./komodo-cli -ac_name=PIRATE getinfo`

That's all!
