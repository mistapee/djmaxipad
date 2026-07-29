# djmaxipad - DJ MAX & other intense rhythm game controller for planting your hands and minimal faffing about.

July 2026: quick update [3d files added to each repo, as that's where updates are happening] - likely to say with the cutout on the top PCB plate, using an insert on top of the cut out, then I can continue ordering PCBs without worrying about the random stocks of Pico's I get sent. Also, where cases originally would house the nut, with a screw going through the controller in to the case, that's been scrapped off for a sit-in style like all the others. I'm always open to ideas but rarely get any so these bits of inspiration just strike me in no sensible or organised fashion

<img width="30%" height="30%" alt="djmaxipad" src="https://github.com/user-attachments/assets/53c36e60-8b81-43f1-bb0a-6879b8fb4646" />



June 2026: The new version out and about has been produced on purple PCBs, and the cut out notch on the top has changed to expose the Bootsel button. I supply them flashed with the config detailed below - BUT - this is one of a few controllers where the GP2040-CE backup/restore system does not work, it will transfer the RGB LED info fine and nothing else and it takes a moment to set it as a keyboard input. The info I have included on that here is useful if you decide to reflash, or if for some reason some of the choices I have made won't work for your situation.
Despite the previous black version being labelled a prototype the PCB for the purple version has barely changed, there are now mounting holes, as the PCBs suffer from bending partly as a design problem and partly productions. The mount holes allow use to fit the controller in to a case of some sort to hold the device flat. Considering it needs some form of case anywauy this is a fine solution for now, and each new order I can place is a new chance to solve the issue from the production side. The case itself is challenging me currently and I have mutlple rooms littered with resin casts and 3D prints trying to solve this in a way I am happy to stand by long-term

USER GUIDE

16 key controller for newer DJ max built on rp2040 and mx keys

![maximappings](https://github.com/user-attachments/assets/2915a76b-2e9d-49a5-805c-a8d70d4fb013)

First things first, it will not show as a gamepad, it will show as a keyboard - the keys I chose didn't matter all that much (it could have been just numbers in a row or whatever) but I wanted it to somewhat represent something recognisable, especially if you end up having to set it up from scratch. If you load your game and just map your keys that might be about it for you. In this picture I've added the GP2040-CE terms for a few of the buttons. Pressing S2 and L1 together will change the LED animation type to the next one. There's not many to choose from, that's something for later. For the webconfig you need S2+B3+B4...

Holding those 3 keys for 5 seconds will reboot the pad in to webconfig mode, although it is not as obvious as when these are set up as xinput gamepads (that make Windows go dandonk dadink) so just hold it for a bit, and access the webconfig at 192.168.7.1. The GP2040-CE site has good documentation so we don't need to go over it all here but one reason you might want to use this would be to set the 2 bottom buttons to trigger the same input like a split space, it is currently set up as two seperate inputs (useful for 'fever' or whatever the game you're playing has) and some games won't let you just solve this in their own key mapping options. Go to GPIO pin mapping, use 'pin viewer' to tell you the GPIO of the button you press, and then you can assign it. The settings use their own terms for the buttons, you won't see them named as you may now be used to them  - there's an image a bit later about that. For now though let's assume you want the 'split space' thingy - pin viewer them both and set them to the same thing. badabing.

This is the set up, don't be put off, you should not need to know this, but it's here for reference.

![gpioshiz](https://github.com/user-attachments/assets/81d47fb3-39fb-4930-a2ef-836c295684d0)

The other most obvious adaptation would be to physically rearrange keycaps - 1.25u caps horizontally or vertically in some positions makes up for changes in hand size. Everyone involved some far is aware that I can't be sure until the PCB's arrive from china, and even then it's quite subjective. Other pads exist that split the keys over 2 rows which made little sense to me and little advantage over a standard keyboard, and will involve panicked hunting with the finger tips. I have set the keys that are off the main line to be within reach of minimal movementof just a few fingers on each hand allowing me to get in to the game and in the zone without the additional step of figuring out the hands. I have let people know it was based on my hands, so far I have had no complaints on the spacing and sizing, but again rearrange some keycaps if it suits you.

Be aware though - the hotkeys to get to webcofig are only where it's stated in the first picture AFTER we have set it to be that. If you have to save and reboot, choose to reboot back in to webconfig until you are sure you can get back in using key presses you have set - otherwise you will be flashing the 'force webconfig' again.

_______________________________

openrhythmuk has these up on the ebays for fair rates.





Ordering from the Gerbers

The USB notch cut out was done last minute as the usual micro-usb Pico's are already quite tight to fit between 2 PCB's and I knew my next batch of them were going to have USB-C which is thicker, bit of a rush job but it'll do. The design was done on the spot out of fill and prohibited regions to give me a design with copper layers etc to block lights and the negative areas to allow light - i'm sure some sarcy get might say like 'yeah, looks like your usual effort there MistaPee' but shuddup, I sent them off rather confident and what I got back worked really well. 

I've used 4 different fabs so far this year and yet again JLC have been absolutely awesome. and they say nothing and cause no fuss, just business day in day out. Not only are their prices ridiculously good but other fabs would somehow leave off a screenprint entirely (on a large order i paid full whack for too wtf) or get really confused over the mirroring and layering either side of a plate for lighting effects.

So go to JLC. Do the online quote, upload Gerbers as supplied  - I chose the black PCB for the top, they don't charge any more for different colours anyway. This means that the screen print later will be done in white. all settings leave to defaults. On small enough orders you can use the cheap chinese shipping that isn't actually all that slow.

Once your order is in get on AliExpress - you need per board: 16 MX switches- linear switches not clicky, as there are no key LEDs there are some very cheap options for perfectly serviceable switches, 4 5050 sized RGBs, one 220o resister (6030smd, buy a reel) and a full size pico. Key caps can be whatever you want but I actually loathe trying to get sensible matching sets. NO HOTSWAP SOCKETS. I swear I'll disown you grumble grumble old man stuff. Anyway this will arrive about the same time as your PCBs.

For SMD stuff I tend to use a solder paste, a slight bit of pressure on the syringe gives enough to dab bits on the PCB and put the parts on, approaching it with heat you can see it spread and get to where you need it, I then always go around after with some proper leaded solder after and bulk it up, probably not needed but it is nice to be sure - the vast majority of our projects have travelled to the other side of the world and beyond, and getting great feedback.

The assembly is quite obvious, but flash it before soldering any keys in - the LEDs will light up, not in an animation you want, but you will see if there is a problem to sort out as once you solder the keys in the top and bottom layers are stuck


Does have RGB with 4x 5050

And I wanted the name to be a play on sanitary products just cos. 3 of this run are up on Ebay at 20gbp each, bargain, obvs, I've not decided on a firmware or anything yet. I have a firmware file that is just the RGB and USB ID that I use on every board without hotswap since once I put the front and back together I can't just open it and resolve anything.
