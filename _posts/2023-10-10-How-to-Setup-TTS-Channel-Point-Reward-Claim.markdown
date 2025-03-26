---
layout: post
title: How to setup Text-to-speech on Twitch as a Channel Points reward
permalink: /posts/how-to-setup-tts/
---

## How to setup Text-to-speech on Twitch as a Channel Points reward

1. **Channel Dashboard**
    - Rewards Section
    - Manage Rewards
    - Scroll to the bottom of Rewards
    - Add a new reward
    - Name it 'TTS' or something
    - Set the channel points price
    - Set it to require user input to go through (the TTS message you want to hear would be the user input, so it's manual)
    - Give it a cute icon (optional) or don't...
    - Save

2. **Go to the Alert Section**
    - Create an alert box or edit an existing one if you are currently using it on your stream.

3. **If it is a new alert box:**
    - Go through all the alert option sections and disable the default alerts that come with the box because they will overlap with your existing ones if you have them already.

4. **Deactivate all alerts except the channel points reward claim.**
    - Navigate directly to the channel points section and add a new option for people adding it to their alert box in use.

5. **Go to settings and name the alert if you want.**
    - Pick the alert we created earlier from the dropdown menu.

6. **Go through the other sections to customize how the alert will show, including which parts to show, colors, cosmetics, etc.**

7. **Don't forget to enable the chat message with the reward claim to be read.**

8. **You can customize the announcement message and choose if TTS will say it or not.**
    - Decide if it would be shown on the screen or not, along with cosmetics.

9. **You can pick various languages and voices.**
    - I recommend going to the last section where it has the animation file and default claim sound.
    - Remove the claim sound or at least change it in a funny way.

10. **Click save, test if you want, and copy the link on the bottom right corner for the browser source when you're done.**
    - Put it into OBS as Browser Source with matching parameters if they are not your defaults for some reason.
    
11. **You are good to go!**


<div id="elevenlabs-audionative-widget" data-height="90" data-width="100%" data-frameborder="no" data-scrolling="no" data-publicuserid="90d276066ff6075dad445314b55a9683b2f5a0e938dae8e40f9ebddc01f9f4a2" data-playerurl="https://elevenlabs.io/player/index.html" >Loading the <a href="https://elevenlabs.io/text-to-speech" target="_blank" rel="noopener">Elevenlabs Text to Speech</a> AudioNative Player...</div><script src="https://elevenlabs.io/player/audioNativeHelper.js" type="text/javascript"></script>