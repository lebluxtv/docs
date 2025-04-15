---
description: Sends a Twitch chat announcement using either the Twitch Bot or Broadcaster account, with optional color styling and fallback behavior.
parameters:
  - name: message
    default: '"Hello, world!"'
    description: The content of the announcement message to send to Twitch chat.
  - name: useBot
    default: true
    description: |
      - `true`{lang=cs} - Send the message using your **Twitch Bot** account  
      - `true`{lang=cs} - Send the message using your **Twitch Broadcaster** account
  - name: color
    default: "Default"
    description: |
      Choose the **color** of the Twitch announcement. Valid values are:  
      - `default`  
      - `blue`  
      - `green`  
      - `orange`  
      - `purple`
  - name: fallback
    version: 0.2.5
    default: true
    description: |
      - `true`{lang=cs} - (If `bot` bool is set to `True`), this is the same behaviour as if you had Bot as your preferred account.   
      - `false`{lang=cs} - (If `bot` bool is set to `True`), it will try to send using **only** the Bot account, and do **nothing** if it can't (i.e, not logged in).
example: |
  using System;
  public class CPHInline
  {
      public bool Execute()
      {
          // Set message for chat
          string message = "This is an announcement";

          // Send announcement with bot account, blue color, with fallback to broadcaster if bot is not logged in
          CPH.TwitchAnnounce(message, true, "blue", true);

          return true;
      }
  }
---
