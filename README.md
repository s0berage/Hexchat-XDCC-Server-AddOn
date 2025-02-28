# Hexchat-XDCC-Server-AddOn
Hexchat-XDCC-Server-AddOn - Its idea is to act as a XDCC Server script written in python for Hexchat IRC client, like iroffer or eggdrop with glftpd, but working solely in python natively on the irc client hexchat versus TCL on mirc.

It's intent is to do the below:

 -indexes HDD folder(s)
 -assigns packet number
 -responds to /msg <BOT-SCRIPT-IRC-NAME> "XDCC SEND <packet number> or "XDCC SEARCH QUERYSTRING" queries
 -works on a message interval
 -refuses to send file(s) if not in the same channel as the bot hosting this script
 -prevents channel AND network flooding
 -ONLY displays to specified channel(s)
 -can be set with /xdccserver set 
      -directories "/Directory/Goes/Here"
      -advertise_channel = "#channelname"
      -flood_delay = "1000" (in ms)
      -message_interval = 60000 (in ms [1min])
      -running = true or false
      -OR
      -start/stop toggle flags

