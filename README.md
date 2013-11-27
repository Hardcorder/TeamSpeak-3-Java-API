TeamSpeak 3 Java API
====================

An Java implementation of [TeamSpeak's 3 server query API](http://media.teamspeak.com/ts3_literature/TeamSpeak%203%20Server%20Query%20Manual.pdf).


## Features

- Contains all functionality (see [TeamSpeak 3 Server Query Manual](http://media.teamspeak.com/ts3_literature/TeamSpeak%203%20Server%20Query%20Manual.pdf))
- Built-in keep alive method
- Threaded event-based system

## Getting Started

All functionality is contained in the [TS3Api](src/com/github/theholywaffle/teamspeak3/TS3Api.java) object.

1. In order to obtain this api object you first need to create a new [TS3Query](src/com/github/theholywaffle/teamspeak3/TS3Query.java) object with the correct constructor parameters.
2. Enable debug if you wish by calling `debug()`
3. Connect to the server with `connect()`
4. Call `getApi()` to get an TS3Api object.
5. Do whatever you want with this api :)

IMPORTANT:

Only use `FloodRate.UNLIMITED` if you are sure that your query account is whitelisted. If not use `FloodRate.DEFAULT`. The server will temporarily ban your account if you send too many commands in a certain period of time. For more info on this check [TeamSpeak 3 Server Query Manual, page 6](http://media.teamspeak.com/ts3_literature/TeamSpeak%203%20Server%20Query%20Manual.pdf).

Example:

    TS3Api api = new TS3Query("77.77.77.77", TS3Query.DEFAULT_PORT,FloodRate.UNLIMITED).debug().connect().getApi();
    api.login("serveradmin", "serveradminpassword");
    api.selectDefaultVirtualServer();
    api.setNickname("PutPutBot");
    ...
    
More examples can be found [here](src/com/github/theholywaffle/teamspeak3/example).
    
## TODO (aka I need your help on this)

* Add Javadoc to [TS3Api](src/com/github/theholywaffle/teamspeak3/TS3Api.java).
* Add more methods to simplify [TS3Api](src/com/github/theholywaffle/teamspeak3/TS3Api.java).