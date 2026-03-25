# djmaxipad - quick info for recent buyers - PCB/parts ordering info after.
16 key controller for newer DJ max built on rp2040 and mx keys
![s-l1600 (1)](https://github.com/user-attachments/assets/1d5bf043-02d6-4082-ba79-dabb3c4ed922)

Just a day or so after I explained a little on how this came about a bunch of them have been made up, boxed and are shipping out so my waffle is bumped off for some instructions for their new owners. Basics first - but I know what some of you are like so further on will be the details you need to reflash n that

First things first, it will not show as a gamepad, it will show as a keyboard - the keys I chose didnt matter all that much (it could have been just numbers in a row or whatever) but I wanted it to somewhat represent something recognisable, especially if you end up having to set it up from scratch. If you load your game and just map your keys that might be about it for you. In this picture I've added the GP2040-CE terms for a few of the buttons. Pressing S2 and L1 together will change the LED animation type to the next one. There's not many to choose from, that's something for later. For the webconfig you need S2+B3+B4...

![maximappings](https://github.com/user-attachments/assets/2915a76b-2e9d-49a5-805c-a8d70d4fb013)

Holding those 3 keys for 5 seconds will reboot the pad in to webconfig mode, although it is not as obvious as when these are set up as xinput gamepads (that make Windows go dandonk dadink) so just hold it for a bit, and access the webconfig at 192.168.7.1. The GP2040-CE site has good documentation so we don't need to go over it all here but one reason you might want to use this would be to set the 2 bottom buttons to trigger the same input like a split space, it is currently set up as two seperate inputs (useful for 'fever' or whatever the game you're playing has) and some games won't let you just solve this in their own key mapping options. Go to GPIO pin mapping, use 'pin viewer' to tell you the GPIO of the button you press, and then you can assign it. The settings use their own terms for the buttons, you won't see them named as you may now be used to them  - there's an image a bit later about that. For now though let's assume you want the 'split space' thingy - pin viewer them both and set them to the same thing. badabing.

The other most obvious adaptation would be to physically rearrange keycaps - 1.25u caps horizontally or vertically in some positions makes up for changes in hand size. Everyone involved some far is aware that I can't be sure until the PCB's arrive from china, and even then it's quite subjective.

done. enjoy.


BuT MisTaPeEeeE I WasSs NoWheRRee NeeaaRr iTtt Aanndd....
The ones that inspire these projects are the same ones that will somehow need to relash theirs - problem is, even once reflashed the GPIO specified by GP2040-CE for the S2+B3+B4 webconfig reboot combo are the only pins I did not use (not even on purpose) and I made the bootsel button awkward to press - thankfully the GP2040-CE release page also has a 'force webconfig' .uf2 file - you must first flash the normal gp2040-ce .uf2, then do it again with the small 'force webconfig'



![maxipadbootsel](https://github.com/user-attachments/assets/c5ef96f5-a43e-485c-8e81-a9fec48b592f)

^lol just noticed i crapped up that pic. paaahahah.

The end result is always worth learning around the quirks. I would say to just use the backup config file to restore from - turns out i don't have one despite thinking i defintely did it.... both browsers are telling me I 'cancelled' it. ffs. I'll upload one soon.

![gpioshiz](https://github.com/user-attachments/assets/81d47fb3-39fb-4930-a2ef-836c295684d0)

Be aware though - the hotkeys to get to webcofig are only where it's stated in the first picture AFTER we have set it to be that. If you have to save and reboot, choose to reboot back in to webconfig until you are sure you can get back in using key presses you have set - otherwise you will be flashing the 'force webconfig' again.

_______________________________

Ordering from the Gerbers

The USB notch cut out was done last minute as the usual micro-usb Pico's are already quite tight to fit between 2 PCB's and I knew my next batch of them were going to have USB-C which is thicker, bit of a rush job but it'll do. The design was done on the spot out of fill and prohibited regions to give me a design with copper layers etc to block lights and the negative areas to allow light - i'm sure some sarcy get might say like 'yeah, looks like your usual effort there MistaPee' but shuddup, I sent them off rather confident and what I got back worked really well. 

I've used 4 different fabs so far this year and yet again JLC have been absolutely awesome. and they say nothing and cause no fuss, just business day in day out. Not only are their prices ridiculously good but other fabs would somehow leave off a screenprint entirely (on a large order i paid full whack for too wtf) or get really confused over the mirroring and layering either side of a plate for lighting effects.

So go to JLC. Do the online quote, upload Gerbers as supplied  - I chose the black PCB for the top, they don't charge any more for different colours anyway. This means that the screen print later will be done in white. all settings leave to defaults. On small enough orders you can use the cheap chinese shipping that isn't actually all that slow.

Once your order is in get on AliExpress - you need per board: 16 MX switches- linear switches not clicky, as there are no key LEDs there are some very cheap options for perfectly serviceable switches, 4 5050 sized RGBs, one 220o resister (6030smd, buy a reel) and a full size pico. Key caps can be whatever you want but I actually loathe trying to get sensible matching sets. NO HOTSWAP SOCKETS. I swear I'll disown you grumble grumble old man stuff. Anyway this will arrive about the same time as your PCBs.

For SMD stuff I tend to use a solder paste, a slight bit of pressure on the syringe gives enough to dab bits on the PCB and put the parts on, approaching it with heat you can see it spread and get to where you need it, I then always go around after with some proper leaded solder after and bulk it up, probably not needed but it is nice to be sure - the vast majority of our projects have travelled to the other side of the world and beyond, and getting great feedback.

The assembly is quite obvious, but flash it before soldering any keys in - the LEDs will light up, not in an animation you want, but you will see if there is a problem to sort out as once you solder the keys in the top and bottom layers are stuck



_________________
I wanted to get back in to DJ max but the latest version is way more involved than the Trilogy style, very common handful of keys that can be found in loads of BMS type games.
I would get lost on a keyboard and being able to lay my hands out properly would give me a good chance to enjoy the game and not get in a mood and start throwing things...

I bought the MOQ of 5 from JLC, the layout is planned around my hands and what I want. Maybe I am wrong (hah yeah unlikely right?) and I do think that some small adjustments (vertical 1.5u placed on furthest keys for instance) could help people with smaller hands or whatever Trevor.

Gerbers are there, help yourself I care less about credit than feedback - information to work towards a final, done-and-dusted, controller is valuable.

Used a full fat Pico, but I took a notch out above the USB port as my next batch of Pico's coming are USB-C, which wouldn't fit between the PCB and the top plate. 
NOT hotswappable... the usefulness of that is questionable anyway but it's just a few clicks to change that yourself if you want that
Not enough GPIO left for me to care to have per-key LED, so didn't.
4 tactile switch (4.5x4.5x 6-9mm tall work fine)

Does have RGB with 4x 5050

And I wanted the name to be a play on sanitary products just cos. 3 of this run are up on Ebay at 20gbp each, bargain, obvs, I've not decided on a firmware or anything yet. I have a firmware file that is just the RGB and USB ID that I use on every board without hotswap since once I put the front and back together I can't just open it and resolve anything.
