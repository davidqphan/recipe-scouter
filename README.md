# recipe-scouter
<img src="http://thedaoofdragonball.com/wp-content/uploads/2013/01/vegeta-scouter-dbz-google-glass.jpg" alt="vegeta scouter" style="width: 400px;"/>  
image credits: thedaoofdragonball.com

## What it is
A helpful recipe finder that gives you possible recipes you can make based on
what ingredients you have available. What makes recipe-scouter unique is that
the recipe is shown on a heads-up display unit that enables easy hands-free 
viewing of each step.

## Why we made it
We came up with this project as a [submission for Long Beach Hacks 2017](https://devpost.com/software/recipe-scouter-3z18vw). The idea was conceived
and completed entirely within a span of 10 hours, on location, at Beach Hacks.  
  
Our goal was to create something that would encompass an embedded system, an
Android app and a web backend. We settled on recipe-scouter because we believed
that this idea touched on all of the areas we wanted to focus on, and because we
felt that it was a meaningful problem to solve -- what to eat?!  

## How it works
There are three components to recipe-scouter:  
  
1. The Heads-up display (HUD) "headset"
2. [The Android app](https://github.com/iS2bit/recipe-scouter)
3. [The backend RESTful service](https://github.com/jgome043/recipe-scouter)

The Android app is the bridge between the project components. The app uses
the Google Cloud Vision API to perform Optical Character Recognition (OCR) on
grocery receipts to add new ingredients into the user's "kitchen"/inventory.  
  
The app then makes a request to the recipe-scouter backend for a recipe
supplying an optional "main ingredient". The backend makes a request for
available recipes based on the available ingredients using the 
[The Food2Fork recipe API](http://food2fork.com/about/api), and returns the
possible recipes to the app.  
  
The selected recipe is then sent to the HUD unit to be displayed, step by step.

## How we made it
1. **HUD**  
The HUD was designed using cardboard prototypes, then modeled in OpenSCAD and 3D
printed on a Monoprice Maker Select V2. The effect is achieved using an OLED
display that is powered by an Arduino board. The display is reflected off a
custom-cut glass mirror, and reflected again onto a custom-cut piece of clear
acrylic glass.  
2. **Android app**  
The Android app was made using Android Studio and the 
[Google Cloud Vision API](https://cloud.google.com/vision/).
3. **Backend RESTful service**  
The backend RESTful service was made with Python and Flask. 
[The Food2Fork recipe API](http://food2fork.com/about/api) is used to return a 
list of possible recipes based on the ingredients available.  
  
## Known issues
We were able to complete a basic "proof of concept", but alas there were still
some areas left in need of improvement by the end of the hackathon.
Particularly:  
  
* Effective OCR on various receipt types/brands (not all receipts have the same
  structure)
* Bluetooth communication between HUD and Android app
  
![demo](https://github.com/jgome043/recipe-scouter/blob/images/images/cropped.jpg?raw=true "Demo")  
![parts](https://github.com/jgome043/recipe-scouter/blob/images/images/overview.jpg?raw=true "Parts and prototypes")
