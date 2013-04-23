#Griddl
##A flexible, responsive grid system
**Griddl** aims to be a truly flexible responsive grid system. Other grids might force you into using a certain number of columns, or laying things out purely in rows, but **Griddl** doesn't do that. Its purely a foundation to be built up from. Because of this, **Griddl** is only 2kb (compressed CSS output from Compass, included here). That's pretty small for all the power and flexibility it gives you!

**Griddl** was originally built by David Eglin, of Connect Advertising & Marketing, for use on the Jaguar.co.uk website, to fix a number of shortfalls in other frameworks.

##Show me the basics
Okay. You want to know how **Griddl** works. Lets give you a quick introduction:

###The *.section-wrapper* class
The *.section-wrapper* class is the top-most layer of **Griddl**'s framework. It is a full-width div which is designed to allow you, the developer, to add full-bleed backgrounds to your content sections. At this point, it doesn't set up any *padding* or *margin* attributes - Only a *max-width* of 1366px - And this is completely overridable. Again, the goal here is for the framework to be as unopinionated as possible, allowing you to use it as you see fit. 

##The \<section> tag (& *.section* class)
*(NOTE: These two things behave in exactly the same way. They are both defined so as to give you the option of which to use)*

The \<section> tag sets up your content regions within your *.section-wrapper* elements. In the version of **Griddl** here, it is set at 96% of browser width, with a *max-width* of 960px, but obviously, you can change that to your liking. Once again, there are no *padding* or *margin* set at this point - You shoudl set them yourself in your own styles. The soul purpose of these elements is to align your content to the center of the available viewport, and set up a maximum width for that content. 

##The *.el* class
This is where it all starts to come together. The *.el* class is the heart of **Griddl**. These elements contain your content. They are your layout boxes, forming columns of sorts in your page. They have a *padding* on all sides of 10px to give them spacing here, but you can easily change this yourself or override it for certain parts of your site. The *.el* class makes use of the *box-sizing* attribute for consistent sizing, so for older versions of IE requires a polyfill to work. 

There are a number of other classes that can be applied to the *.el* elements, as follows:

###.width-xofy
*(i.e. .width-1of2)*

This class controls the width of each *.el* element. Think of it as "*x* of *y* columns" - So *.width-1of2* will give you a 50% width element. If you look at **Griddl**.scss, you will see that there are definitions for 2,3,4,5,6 and 8 column widths. You can combine these all within the same \<section> element, too - So you can use a *.width-1of2* element alongside 2 *.width-1of4* elements to make up a whole row. The option has been provided though, if you find it easier, to keep the same number of columns for a given section - So a *.width-1of2* element is the same as a *.width-2of4* element. Flexible, huh? 

###.in-xofy
*(i.e. .in-1of2)*

This class controls the horizontal indenting of an *.el* element. So a class of *.in-1of2* will indent the element by 50% of the viewport width. 

###.out-xofy
*(i.e. .out-1of2)*

This class controls the horizontal outdenting of an *.el* element. So a class of *.out-1of2* will outdent the element by 50% of the viewport width. This isn't really useful on its own, but when used in combination with indented elements, it allows you to swap the visual order of elements for desktop and tablet, whilst maintaining the source order you desire for mobile devices. 

So, in the following example:

```<div class="el width-1of2 in-1of2"></div>
<div class="el width-1of2 out-1of2"></div>```

The second div will appear on the left, and the first on the right, but on mobile the first div will still appear first. Nifty or what? 

##The best is yet to come…
There is so much more yet to come from this framework. At the moment it is a bare-bones starting block for a basic responsive grid, but it will be developed over time to be more powerful and even more flexible. The basis for *boxes* (smaller, fixed-size elements designed to contain lozenges or specific calls-to-action) is already there, but needs expanding upon. **Griddl** will also expand to allow for more device "snap-points", too. At the moment there are only snap-points for mobile (639px width and below), tablet portrait (800px and below) and desktop (801px and upwards) devices, but this list will expand. Finally, the plan is for **Griddl** to contain some basic text baseline styles to ensure spacing and sizing coherence for your projects. Obviously, as with the rest of **Griddl**, you will be able to override and change this should you want to, but it will be included in the near future for your convenience. 