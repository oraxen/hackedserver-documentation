---
description: How to use the "Others" section from the settings to add your own checks
---

# Add your own checks

## How does the section work?

```yaml
  # Example configuration of the listener for an example client/version/mod

  #The name of the configuration section (you can use what you want, it is not important)
  ExampleSectionName:

    #The channel name sent by the client that HackedServer will intercept
    Channel: "EXAMPLE CHANNEL"

    #The name of the subsection (because you can detect differents clients/mods/versions on the same channel)
    ExampleSubSectionName:

      #It is a condition : if the message sent by the client contains this text, HackedServer will read the rest of this subsection
      Contains: "I'm using ExampleClient"

      #The client name that HackedServer will display in its messages
      ClientName: "ExampleClient"

      #Actions to do when a player join with this client/mod/version
      Actions:

        #Enabled Placeholders in Commands and AlertMessage : %p%, %version%, %message%

        #Commands you want to be performed by the Console
        ConsoleCommands:
          - "kill %p%"

        #Commands you want to be performed by the player (as an op)
        OppedPlayerCommands: []

        #Enable alerts for players who have permission hackedserver.alert
        Alert: true

        #Alert message to send if enabled
        AlertMessage: "&c %p% &7sent the plugin message \"&c%message%&7\" using the version &c%version%"
```

## Example section: Rift

```yaml
  McBrandChannel:
    Channels:
      - "MC|Brand"
      - "minecraft:brand"

    Rift:
      ClientName: "Rift"
      Contains: "rift"
      Actions:
        ConsoleCommands: []
        OppedPlayerCommands: []
        Alert: true
        AlertMessage: "&c %p% &7just logged in using \"&c%version%&7\" !"
```

{% hint style="info" %}
&#x20;You can also read [this little article](https://medium.com/@th0rgal/how-to-detect-the-undetectable-hacked-client-aristois-ad14562e357e?source=friends\_link\&sk=2221d97e86189e372bd92c8a742cf477) on medium that explains my approach with examples
{% endhint %}

