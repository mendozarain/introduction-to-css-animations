# Introduction To CSS Animations 
___
### SYLABUS
- What are CSS Animations?
-  Benefits of CSS Animations
-  Purpose of CSS Animations
-  Transforms
-  Transitions
-  Keyframes
-  Exercise 
___
## What are CSS Animations?
CSS Animations allows animation of HTML elements without using JavaScript or Flash
___
## Benefits of CSS Animations
It can impress your users which in turn make them more likely to use your website. In addition, it can add a layer of delight and fun. It can also provide reassurance and meaning to interactions.

It makes animating web elements easier without using javascript elements. 
___
## Purpose of CSS Animations
 When animations are used in a subtle way,  it can showcase or demonstrate functionality. In a way, it acts as mini-onboarding. It can help users build mental models about how the system works and how they can interact with it.

#### 3 Main Purposes :
-  ###  Providing Feedback 
Animations are often helpful as a form of noticeable feedback that an action has been recognized by the system. 

- ###  Communicating State Change
Animations can be used to indicate that the interface switched to a different state. 

- ### Acting as a Signifier
Animations help users understand how to interact with UI elements. The direction (or other attributes) of the motion signifies the type of acceptable actions. (For example, a card that expands from the bottom of the screen towards the top signals to the user that it can be closed by pulling down.)
___
## The Right Ways To Use CSS Animations
- ### keep users interested

An example of this is adding loading time animations.

Studies have shown that more than 40% of users expect a webpage or an app to load in 2 seconds or less. If it takes more than 4 seconds, the average user starts getting frustrated. After 8 seconds, they leave. As little as one second worth of delay in your site speed can result in a 7% reduction in customer usage. Loading time is crucial to the success of your site, app or program and if you can keep the user engaged for those few seconds/milliseconds, even better.

- ### Animate based on where the user should focus

Often when opening an app or webpage, you’re presented with a screen _full_ of items, and you’re not sure where to start. Animation to the rescue! A great way to help your users is to give clues about the proprieties of those objects.

Example, If you have a list of posts, sliding them up (instead of having them just appear) could help your users understand that they can keep swiping down to see more.

- ### Keep users from getting lost

Once you’ve cleaned up your site or app to the point that it’s nearly seamless, it becomes more vital that you give your users a sense of spatial awareness. Consider this: if an object moves out of the screen to the left, it should re-enter (if necessary) from the space where it exited.

- ### Use feedback to show what’s been accomplished

Animation can give visual feedback that shows when the site is working properly.
___

## Transform
CSS transform allow you to move, rotate, scale, and skew elements.

- #### Transform Syntax/Methods
-   `translate(X,Y) or translate(val)` - Move the element to one point to another.  Uses both x and y axises.
 	-  `translateX()` - Move according to the x axis.
 	-  `translateY()` - Move according to the y axis.
 	-  `translateZ()` - Move according to the z axis.
 	
-   `scale(X,Y) or scale(val)` -  Increases or decreases the size of an element (according to the parameters given for both the width and height). `1` being the value of the current size
	- `scaleX()` -   Increases or decreases the size of an element according to the x axis.
	- `scaleY()`-   Increases or decreases the size of an element according to the y axis.
	
-   `rotate(deg)` - rotates an element clockwise or counter-clockwise according to a given degree.

-   `skew(xdeg,ydeg)` -  skews an element along the X and Y-axis by the given angles.
		-   `skewX(deg)` -skews according to the x axis.
        -   `skewY(deg)` - skews according to the y axis.
        
-   `matrix()` - combines all the 2D transform methods into one. The parameters are as follow: matrix(scaleX(),skewY(),skewX(),scaleY(),translateX(),translateY())

***Note:*** Sometimes order does matter when using transform methods in combination 
___

## Transition
CSS transitions allows you to change property values smoothly, over a given duration.

-   `transition` 
	-   To create a transition effect, you must specify two things:
		-   the CSS property you want to add an effect to
		-   the duration of the effect

#### Example 
```
/* The transition code */  
#dadz {

 transition: 1s linear;

 transform-origin: center;

 transform-box: fill-box;

}

/* What the property will transition into */ 
#dadz:hover {

 transform: rotate(120deg);

 opacity: 0;

}
```

		
-   `transition-delay` -   Specifies a delay (in seconds) for the transition effect

-   `transition-timing-function` - property specifies the speed curve of the transition effect.
	-   `ease` - specifies a transition effect with a slow start, then fast, then end slowly (this is default)
	-   `linear` - specifies a transition effect with the same speed from start to end
	-   `ease-in` - specifies a transition effect with a slow start
	-   `ease-out` - specifies a transition effect with a slow end
	-   `ease-in-out` - specifies a transition effect with a slow start and end
	-   `cubic-bezier(n,n,n,n)` - lets you define your own values in a cubic-bezier function

#### Shorthand property
-   `transition` - is the shorthand property that uses four of the animation properties in the order : `animation: (transition-property) (duration) (transition-timing-function) (delay)`


### Example
```
dadz { 
	  transition: opacity 1s linear 2s;
}
```



___

## Keyframes 
Keyframes hold what styles the element will have at certain times. Basically a beefed-up transitions.

### Example
```
/* The animation code */  
@keyframes example { 
  from {
	background-color: red;
  }  
  to {
  	background-color: yellow;
  }
}  
  
/* The element to apply the animation to */  
div { width: 100px;  
  height: 100px;  
  background-color: red;  
  animation-name: example;  
  animation-duration: 4s;
}
```
***Note:***  Besides `from` and `to` you can also set keyframes by percentage 

### Example
```
/* The animation code */  
@keyframes example { 

 0% {
	transform: scale(1);
	background-color: red;
 }

 25% {
	 transform: scale(3);
	 background-color: yellow;
 }

50% {
 transform: scale(9);
 background-color: blue;
 }

100% {
 transform: scale(9);
 background-color: green;
 }
}  
  
/* The element to apply the animation to */  
div { width: 100px;  
  height: 100px;  
  background-color: red;  
  animation-name: example;  
  animation-duration: 4s;
}
```

-   `animation-delay` -  specifies a delay for the start of an animation.

-   `animation-iteration-count` - property specifies the number of times an animation should run.
	-  ***Note:*** Add `infinite` to make the animation continue for ever.
	
-   `animation-direction` - specifies whether an animation should be played forwards, backwards or in alternate cycles.
	-   `normal` - The animation is played as normal (forwards). This is default
	-   `reverse` - The animation is played in reverse direction (backwards)
	-   `alternate` - The animation is played forwards first, then backwards
	-   `alternate-reverse` - The animation is played backwards first, then forwards
	
-   `animation-timing-function` -  specifies the speed curve of the animation.
	-   `ease` - Specifies an animation with a slow start, then fast, then end slowly (this is default)
	-   `linear` - Specifies an animation with the same speed from start to end
	-   `ease-in` - Specifies an animation with a slow start
	-   `ease-out` - Specifies an animation with a slow end
	-   `ease-in-out` - Specifies an animation with a slow start and end
	-   `cubic-bezier(n,n,n,n)` - Lets you define your own values in a cubic-bezier function
	
-   `animation-fill-mode` -  specifies a style for the target element when the animation is not playing (before it starts, after it ends, or both).
	-   `none` - Default value. Animation will not apply any styles to the element before or after it is executing
	-   `forwards` - The element will retain the style values that is set by the last keyframe (depends on animation-direction and animation-iteration-count)
	-   `backwards` - The element will get the style values that is set by the first keyframe (depends on animation-direction), and retain this during the animation-delay period
	-   `both` - The animation will follow the rules for both forwards and backwards, extending the animation properties in both directions
	
#### Shorthand property
-   `animation` - is the shorthand property that uses six of the animation properties in the order : `animation: (animation-name) (duration) (animation-timing-function) (delay) (animation-iteration-count) (animation direction);`


### Example
```
dadz { 
	 animation: example 5s linear 2s infinite alternate;
}
```

