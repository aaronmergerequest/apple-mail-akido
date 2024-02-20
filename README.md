WHAT IS MAIL AIKIDO?

Mail Aikido is a bundle of AppleScripts and instructions that you can use to add keyboard shortcuts for moving messages to folders in Apple Mail.

Before macOS Sonoma (macOS 14) you could employ plugins that made the creation and management of keyboard shortcuts easy.

macOS Sonoma removed support for plugins which necessitated the creation of this workaround.


HOW DOES IT WORK?

Mail Aikido uses Automator, AppleScript, and Keyboard Shortcuts, all of which come built into macOS. Here's how it works:

Step 1: You create "Quick Actions" with AppleScript using Automator that move selected mail messages into folders. You create one "quick action" for every folder that you'd like to quickly move email into

Step 2: You then create a custom keyboard shortcut for each folder that you'd like to target and assign it to the Apple Mail app

Step 3: You will be prompted to grant Automator and Mail permissions to perform these actions via the System Settings. 

Step 4: You will be able to quickly move messages into folders using keyboard shortcuts, greatly speeding your email workflow.



SETTING UP MAIL AIKIDO

There is a YouTube video found here that walks through the steps: 
https://www.youtube.com/watch?v=Cj_H512Qxuc

Here is a written walk-through with screenshots as an aid:
https://www.hausinteractive.com/moving-apple-mail-messages-using-applescript-automator-and-keyboard-shortcuts/


To set up Mail Aikido you repeat the below for each folder you would like to target with a keyboard shortcut:

Automator Scripts
1. Open Automator
2. Choose "Quick Action"
3. Choose the following settings:
    • Workflow receives: No input
    • in: Mail.app
    • Image: Mail
    • Color: Black
4. In the search field, search for "Applescript"
5. Drag "Run Applescript" into the composing window on the right
6. Copy and paste mail-aikido-script-1-of-2.txt into the text field
7. Change your mail account name and folder 
8. Drag a second instance of "Run AppleScript" below your first script
9. Copy and paste mail-aikido-script-2-of-2.txt into the text field
10. File > Save. Pick an obvious and unique name like action-newsletters

FYI: These are saved in ~/Library/Services/

FYI: You should now see this in Apple's Mail menu: Mail > Services


Keyboard Shortcuts
1. Open System Settings > Keyboard > Keyboard Shortcuts ...
2. Choose App Shortcuts
3. Click the "+" button and...
    • Application: Mail.app
    • Menu title: type the name of your action eg: action-newsletters
    • Keyboard shortcut: type your desired shortcut eg: ctrl-n
    • Click "Done"

FYI: In Apple Mail you should now see the keyboard shortcut next to your action in the menu Mail > Services. This means you can use it.


Permissions

When you first attempt to use your new shortcut you'll be prompted to grant permission for Automator and Apple Mail to perform actions. Go to System Settings and set them. They will be:

Privacy & Security > Accessibility > Mail and Automator



TROUBLESHOOTING

Far and away the two most common problems you will run into are:

(1) Spelling

(2) Permissions

If your keyboard shortcut is not throwing any errors but not moving mail where you want, check the script in Automator. We all know how to type our account and folder names but it's easy to have a stray letter or space get in the way, or a missing quotation mark.

If your keyboard shortcut is throwing an error like "The action “Run AppleScript” encountered an error: “System Events got an error: Automator Workflow Runner (WorkflowServiceRunner, [appname]) is not allowed to send keystrokes.""" you'll check two things:

(1) That System Settings > Privacy & Security > Accessibility > Mail and Automator are both set to "on"

(2) If toggling the permissions above don't work, you can open Automator and choose the menu Automator > Reset Warnings. Not sure why this one works, but it usually does



COMPATIBILITY:

Mail Aikido has been tested and confirmed to be working with:

• macOS Sonoma (macOS 14)
• macOS Ventura (macOS 13) 

Given the toolkit, Mail Aikido is hypothetically compatible with every Apple OS since OS X. As users confirm compatibility it will be added to the list above.

![alt text](https://github.com/aaronmergerequest/apple-mail-aikido/blob/main/apple-mail-aikido-1.0.png?raw=true)