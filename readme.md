# Hotswap Keyboard Build Guide
## Table of Contents:
- [History](#History)
- [Terminology](#Terminology)
- [Introduction](#Introduction)
- [Assembling the Keyboard](#Assembling-the-Keyboard)
	 - [1. Testing the PCB](#1.-Testing-the-PCB)
	 - [2. Installing Stabilizers](#2.-Installing-Stabilizers)
	 - [3. Installing Switches](#3.-Installing-Switches)
	 - [4. Assembling the Keyboard](#4.-Assembling-the-Keyboard)
- [Troubleshooting](#Troubleshooting)
- [User Persona](#User-Persona)
- [Use Case Diagram](#Use-Case-Diagram)

## History
With the invention of the computer, keyboards came along with it. These older keyboards were designed around the typewriter, as it was what was familiar at the time and wouldn’t require users to learn a new layout or where keys were. Additionally, this is where the first mechanical keyboards started. The true definition of a mechanical keyboard is highly debated, however for this article it will be defined as a keyboard with a switch for each keycap on the keyboard. The keycap is a plastic piece with a letter on it, to indicate what letter will be displayed on the keyboard when it is pressed down. The switch underneath is what actually sends the input to the computer. Generally, mechanical switches work by touching metal contacts, which then sends a signal to the computer as to which key has been pressed.  The keyboards at this time were generally produced in house, and were un-standardized.

As computers became more and more common, they began to be used in more commercial and industrial application. Along with them, keyboards became a common sight at many jobs, including retail applications. These keyboards generally had unique layouts, that is to say that the arrangement of the keys were different. Many of these keyboards featured unique keys for different functions, and were generally specialized. One popular keyboard manufacturer for these was Cherry, who made many keyboards seen at cash registers. As time went on, enthusiasts would claim that Cherry and ALPS (another manufacturer from this era) were the best. They were not the only company making these keyboards, but were well known

Membrane keyboards entered the market around the 1980s, as seen in an article from the [New York Times](https://www.nytimes.com/1981/03/05/business/technology-the-membrane-keyboard.html).  These keyboards used a flexible membrane sheet to activate switches, rather than having an individual switch per key. This technology had been seen in appliances like calculators, but not yet applied to keyboards. Unfortunately , these keyboards were not received well at the time, being finnicky and unreliable ([Source](https://www.machinedesign.com/markets/manufacturing-equipment/article/21834688/a-short-history-of-membrane-switches)). After many improvements though, we approached where we are today: membrane keyboards are everywhere. This is due to the reduced cost of production and overall cheap end product that’s made. The popularity of membrane keyboards caused ALPS to go out of business, and Cherry began to produce less consumer products and more industrial implementations. Despite this, some still argued that cherry and ALPS keyboards were better than the now popular membrane keyboards.

These people would be proven right, as gamers began to go back to these older keyboards. They argued that N-Key Rollover was essential to playing games. Rollover refers to how many keys can be simultaneously pressed without input errors. N-key rollover means that an infinite number of keys can be pressed without any input errors. This technology is not exclusive to mechanical keyboards, but it is time consuming to implement and can cost more.

These gamers also mentioned the added benefit of not having to bottom out, the practice of fully depressing a key to send an input to the computer. With membrane keyboards, one must fully depress a key every time they want to send a letter to the computer. Mechanical keyboards do not require this, due to how the switch mechanism is implemented. Thus, it was argued that it increased how fast you were able to send inputs to the computer, which was crucial at high level competitive play. This spike in popularity caused many gaming peripheral companies to start to produce more mechanical keyboards, primarily using Cherry switches.

Eventually, these keyboards became a mainstay of a tech enthusiast’s setup and now customized keyboards are much more readily available. These keyboards do not come with switches or keycaps, instead just providing a PCB to install switches into along with a case. The PCB is a sheet of copper that is used to connect many parts without the use of wires. Additionally, a keyboard case is an enclosure for this PCB and switches, rather than a case to hold the keyboard in.

With this flexibility, designers were able to create new keyboard layouts and new ways to mount hardware. Additionally, ergonomic keyboards have become much more readily available. These keyboards have alternative layouts designed to ease hand strain. They accomplish this by using one or more of the following:

- Ortholinear layout
	- This means that the keys are arranged in a true grid, similar to a numpad. The benefit is that you need to move your hands much less to hit all the keys on a keyboard. The most popular keyboard with this layout are the Planck and the Preonic
- Columnar Stagger
	- This is similar to normal keyboards, which have row stagger. Instead of shifting the keys horizontally from an ortholinear layout, they are instead shifted vertically to more naturally fit the shape of a relaxed hand. Some popular keyboards with this feature are the Corne and the Kyria.
- Split Layout
	- This means that the keyboard is separated into two separate parts and are normally connected by a detachable cable. This allows for the two parts to lie directly under your hands.
	- This layout can also be unibody, where both sides are separated but contained in one case. Some examples of this are the Alice/Arisu keyboards, the Reviung series, and the Lumberjack keyboard.
- Tenting options
	- This means that one end of the keyboard can be raised. Many normal keyboards have this feature aswell, but ergonomic ones tend to tent on the inside edges of a split keyboard. This can be seen as a modification for most split keyboards, but the Moonlander features them by default.

In addition to more readily available custom keyboard kits, many of these ergonomic keyboards are open source. This means that the code and design files to make these keyboards are open to the public, and thus anyone can manufacture the keyboard without having to go through a company. Additionally, software exists to easily create your own ergonomic keyboard fitted to your hands, and produces all files necessary to print a case and PCB (ergo gen).

## Terminology

Many of the keyboards seen both in the custom and prebuilt aspects of the are very different from what most consumers have seen. Here are further explanations of these terms:
- Layouts: The way in which the keys on a keyboard are physically arranged
	- Many of these keyboards are described in the percent of keys on the keyboard compared to a fullsized keyboard, which has all keys on it, including a numpad.
	- Another term mentioned in this category is if the switches are “north facing”. This means that the LED slot on the switch is facing towards the top of the keyboard. When inserted like this, these switches can have some interference with Cherry profile keycaps (see below).
- Keycaps: These are the plastic parts that you physically press when typing. They tell you what letter you’re inputting to the computer.
	- There are many different profiles that keycaps come in. These profiles indicate the overall shape of the keycaps, and if they are different heights or not.
		- The keycaps most commonly seen are non-uniform keycaps; different rows of the keyboards have different heights. Cherry profile is one such non-uniform keycap profile. 
		- Uniform keycaps are ones that have a uniform height; these are typically seen on laptop keyboards, but there are also many custom keyboards with uniform keycaps.
	- Additionally, there are many acronyms for keycaps. In general, keycap set names are formatted as the following: “Profile Acroymn – Keycap set name”.
		- Some examples of this are:
			- DSA 2077 (A DSA profile keycap set called “2077”)
			- KAM Cookie Tin (A KAM profile keycap set called “Cookie Tin”)
	- An exception to this rule is that sometimes keycap manufacturers put their name before the set instead. These are generally Cherry profile or OEM profile keycaps. Some examples of these are:
		- GMK Ki (A keycap set called “Ki” produced by the company GMK)
		- NicePBT Earl Grey Lavender (A keycap set called “Earl Grey Lavender by the company NicePBT)
	- There are too many profiles and companies to list here, but you can easily find more information about most profiles and companies through a quick internet search.
- Keycap Materials
	- Keycap sets tend to be made of one of two materials:
		- PBT – Considered to be a cheaper keycap material, but has seen higher quality sets being made of it as of late. Generally thicker and has a deeper sound signature. 
		- ABS – Considered to be a more premium keycap material. GMK is well known for producing these keycaps. These generally have a decent amount of texture to them, and as they loose the texture they begin to shine.
- Switches: These are the physical objects you press down on in a keyboard. 
	- Mechanical Keyboards have 3 different switch types:
		- Tactile (Brown Switches)
			- These feel like flipping a light switch, and have a sense of tactility to them.
		- Clickly Switches (Blue Switches)
			- These are similar to the Tactiles/Brown Switches, but have an audible click when pressing down on them.
		- Linear Switches (Red Switches)
			- These have no tactility, and are ideally smooth. These would be similar to pushing a door (but much lighter).

## Introduction
To build your keyboard, you will need the following:
- 2 metal tweezers
- A keyboard kit (PCB, Plate, Case)
- Switches (enough to fill the entire keyboard +  **at least** 10 extra switches)
- Keycaps
- A USB Cable 
	- The specific type depends on the kit you have. Normally it's USB C, but older kits can use Micro USB or USB micro-b


## Assembling the Keyboard
 There are four major steps to this process, and should be done in this order:
 - [1. Testing the PCB](#1.-Testing-the-PCB)
 - [2. Installing Stabilizers](#2.-Installing-Stabilizers)
 - [3. Installing Switches](#3.-Installing-Switches)
 - [4. Assembling the Keyboard](#4.-Assembling-the-Keyboard)
 
### 1. Testing the PCB
 This is an important step in the process, as many places will invalidate your warranty if you do not test your PCB.
 The PCB is the brains of the keyboard, and is the part with the electronic components. Thus, it's really important that everything is ok with it at the start.
 
To test your PCB:
1. If your keyboard supports VIA or Vial, both of which are keyboard firmware, please set those up instead. See the sections on [VIA Setup] and [Vial Setup]
	- Go to a keyboard tester website or start a keyboard checking program. Some examples are https://www.keyboardtester.com/ and https://keyboardchecker.com/.
	- If you know your keyboard works with VIA or Vial, they can also be used. For these, go to the matrix tester section. The process will be the same as if you used the websites.
2. Plug the PCB into your computer. Place it upside down, so you can see the hotswap sockets.
3. Take a set of metal tweezers, and short the two contact pads of the hotswap socket.
![KBD DZ60 PCB Photo](https://www.startpage.com/av/proxy-image?piurl=https%3A%2F%2Fcdn.shopify.com%2Fs%2Ffiles%2F1%2F1473%2F3902%2Fproducts%2F7_48abb070-70b6-4236-91e8-a2e7ffc33c60.jpg%3Fv%3D1578016277&sp=1679432349Te0435c7c698c3a9bb2770e9e9405fc46eb7cd0c700f379e4edf97ea9613bffb8)
		- The photo here is from KBDFans' DZ60RGB V2 PCB, and can be found at (https://kbdfans.com/products/dz60rgb-hot-swap-custom-keyboard-pcb).
	- The two contact pads Are the two metal squares connected to the black components. Do not short any metal parts that are not these two metal squares, as you could damage the PCB.
4. Short all pairs of contact pads, and see if there are any that are not working
	- If there are any contacts that are not working, please email the vendor you got your PCB from and ask them to send a new one, as your current one is faulty.
	- Note that some keys work to modify other keys and may not get picked up by the keyboard testing websites. (VIA and Vial will pick up these keys, as they know the keyboard and what to look for.) In these cases, use one set of tweezers to press the first key, and then another set of tweezers to press another key on the keyboard. Typically these are found on keyboards with smaller layouts. 
5. If all keys light up, unplug the PCB and flip it back over, so the contact pads are on the bottom. Then, you can move onto the next section.

### 2. Installing Stabilizers
1. Find what kind of stabilizer you have.
	1. Screw mounted stabilizers will come with screws.
	2. Plate mounted stabilizers have a clip on one side, and have no pegs underneath the housing of the stabilizers.
	3. PCB Mounted stabilizers have two pegs under the housing, and no clips.
2. (OPTIONAL) Modify stabilizers to decrease rattle, the noise caused by loose stabilizers. See [Modifying Stabilizers] for more details.
3. Install Stabilizers
	- For all stabilizers, make sure when installing them that the stabilizer wire goes in the opposite direction of the switch pins. See [Installing Switches](#3.-Installing-Switches)
	- 1. For Screw In stabilizers, look at the bottom of the PCB. Put the side with a hook on the peg into the smaller hole on the PCB. Then, push down on the housing and simultaneously screw in the screw on the other side. Note: If there is a washer, please put it on the screw before installing it.
	2. For plate mounted stabilizers, insert the stabilizers into the cutouts in the plate. They will be rectangles.
	3. For PCB Mount stabilizers, look at the bottom of the PCB. Put the side with a hook on the peg into the smaller hole on the PCB. Then, push down on the housing and snap the stabilizers into place.
4. Test stabilizers
	- This is optional, however if you installed the stabilizer wrong or don't like how it sounds, you will have to completely unbuild your keyboard.
	- Install a switch into the plate for each key that requires a stabilizer.
	- See [Installing Switches](#3.-Installing-Switches) for more information.
	- Then, place the corresponding keycap on the switch. For example, the long stabilizer at the bottom of most keyboards corresponds to the spacebar.
5. Remove the keycaps and proceed to the next section!
### 3. Installing Switches
1. First, align the plate with the PCB, such that each set of contacts (the circles with metal in them),  is aligned with a square.
	- Don't just focus on the bottom row for this, and focus on the middle of the keyboard. Sometimes it can be confusing to tell if your plate is aligned if you judge based on the bottom row, as there can be many ways to set that specific row up.
2. Note where the contacts are. They will either be towards the top of the square or the bottom.
3. Remove the plate from the PCB, and install switches. make sure the pins of the switches, or the metal sticking out of it, are in the same spot as where the contacts were.
- If you are just testing the stabilizers, you can stop here and [go back to that section](#2.-Installing-Stabilizers)
4. After you've installed all the switches, you then want to align the pins of the switches with the sockets, but do not press down yet.
5. **While supporting the hotswap sockets on the back of the PCB** begin pressing down on the switches to install them. 
	- If you are having issues getting all of the switches to stay, you could remove most of the switches, and then come back and do this step.
	- After you get the plate and the switches combined, you could then put the other switches in, making sure to align all of the switches.
6. After all switches are inserted, you can proceed to the next section!
### 4. Assemble the keyboard
1. This section is extremely varied with all of the different types of keyboards there are out there, and you should refer to your specific documentation in order to properly build your keyboard.
2. Afterwards, make sure to test the keyboard again before you put keycaps on. 
	- Like with testing the PCB, you need to use keyboard checking software or websites to ensure everything is working. If some switches are not working, check [Troubleshooting](#Troubleshooting).
3. If everything looks good, install your keycaps and stary typing!

## Troubleshooting
If you are having issues with some keys not working properly after installation, this is normal for hotswap keyboards. This is because you may have bent some pins during installation. 

To check for switches with bent pins, simply pull out one of the switches that you have issues with. You can do this by unclipping the switches from the plate with your tweezers. The pins should not be straight if they got bent when they were going in.
- If this is the issue, simply replace the switches using some from the extra switches. 

If the switch comes out and the pins are straight, check if the keys that are malfunctioning are in a straight line. If there is a horizontal or straight line of keys not working that spans the entire keyboard, you have knocked a diode off. 
- These components are really small, and are crucial for how keyboards work and achieve NKRO. 
- If this is the issue, I would recommend trying to find someone with soldering experience to repair this for you, as it's a very difficult repair job.

If there isn't an entire row or column acting up, and the switch pins come out straight, then you might've just gotten a bad switch.
- It's rare, but it does happen. Simply replace the switch with one of the extra switches.

## Appendix

### User Persona

[Link](https://my.visme.co/view/dmg088j1-user-persona-general-hobbyist)

### Use Case Diagram

[Link](https://lucid.app/lucidchart/49fd08cf-8e5b-4874-8556-5dc60ff3dcbc/edit?view_items=adcDk6JkI673&invitationId=inv_82ed03a2-6fcd-4e01-8c8c-5658faaca31e)
