# Hexchat-XDCC-Server-AddOn
Hexchat-XDCC-Server-AddOn - Its idea is to act as a XDCC Server script written in python for Hexchat IRC client, like iroffer or eggdrop with glftpd, but working solely in python natively on the irc client hexchat versus TCL on mirc. Drop it in your addons folder for hexchat, close and reopen hexchat, and use the commands below:

It's intent is to do the below:

**      **-indexes HDD folder(s)**
      
  **  **  -assigns packet number****
      
**    **  -responds to /msg <BOT-SCRIPT-IRC-NAME> "XDCC SEND <packet number> or "XDCC SEARCH QUERYSTRING" queries****
      
**     ** -works on a message interval****
      
**      -refuses to send file(s) if not in the same channel as the bot hosting this script**
      
   ** **  **-prevents channel AND network flooding****
      **
    **  -ONLY displays to specified channel(s)********

Here is a breakdown of the commands available in the XDCC Server Script, along with their usage:

### Commands

1. **/xdccserver set <key> <value>**
   - **Description**: Set various configuration options for the XDCC server.
   - **Parameters**:
     - `<key>`: The configuration key you want to set. 
       - Valid options include:
         - **directories**: A comma-separated list of directories to index files from.
         - **advertise_channel**: The channel where the bot will send its advertisement messages.
         - **message_interval**: Time in milliseconds between the bot's advertisement messages. (Default: `60000 ms`)
         - **flood_delay**: Time in milliseconds to wait between sends to prevent flooding. (Default: `5000 ms`)
     - `<value>`: The value to assign to the specified key.

   - **Example**:
     - To set directories: `/xdccserver set directories /path/to/directory1,/path/to/directory2`
     - To change the advertisement channel: `/xdccserver set advertise_channel #mychannel`

2. **/xdccserver start**
   - **Description**: Starts the XDCC server's message advertising.
   - **Usage**: Simply type `/xdccserver start`.
   - **Note**: If the XDCC server is already running, this command will not do anything.

3. **/xdccserver stop**
   - **Description**: Stops the XDCC server's message advertising.
   - **Usage**: Simply type `/xdccserver stop`.
   - **Note**: If the XDCC server isn't running, this command will notify you that it's not active.

4. **Message Commands (in private messages)**:
   - Users can message the bot to request files or search for files:
   
   - **XDCC Send**: `/msg <bot_nick> xdcc send <packet_number>`
     - **Description**: Request a specific file from the bot using its packet number.
     - **Example**: `/msg myBot xdcc send 5` (where `5` is the packet number).

   - **XDCC Search**: `/msg <bot_nick> xdcc search <query>`
     - **Description**: Search for files by sending a query. The bot will return a list of matching files.
     - **Example**: `/msg myBot xdcc search exampleFileName`

### Summary of Features
- The bot can index files from specified directories and serve them based on packet numbers.
- The bot advertises its available files at specified intervals to a designated channel.
- The bot handles file requests and searches based on user messages.

### Notes:
- Always ensure to configure your bot before starting it to utilize its full capabilities (especially setting its file directories).
- Messages sent to the bot should follow the specified format for them to be understood correctly. 
