---
layout: post
title: Code is language // Objectifying language
---

<figure class="float-left">
<div>
<img src="https://live.staticflickr.com/7197/6882544451_52caa8c5d9_b.jpg" alt="Risotto">
<figcaption>Champagne Risotto</figcaption>
</div>
</figure>One of my favorite dishes to make in restaurants was porridge. To be more concise: I liked making risotto in restaurants. Risotto is an *instance* of `Porridge`. So is polenta, arroz caldo, and congee. And I like cooking steal head oats, which is also an iteration of "porridge." Calling something an instance, or "instantiation," is how we say that there is a big definition of something, "porridge," and there are other foods that fall under the big umbrella definition. Having a larger definition of something, a blueprint, is one of the reasons for Object-Oriented Programming. It also helps to define things in our world.

Think about the last time you were in a restaurant. I'm in month six of COVID-land, so if it takes a while to remember I'll wait [here](https://media.giphy.com/media/553Zs1KrXN7A3H7ofT/giphy.gif). The menu is separated into sections with headings like "appetizers," "soup," "pasta," "main"/"entree",  and "dessert." We've fallen into the convention that if we want to eat something that is typically wet and brothy, it'll be found in the "soup" section, not "pasta." Now each soup in that section is an instance, or child, of the definition of soup. They're all basically (when seen through the eyes of an alien) the same thing: something wet, typically served hot, for eating with a spoon.

This time around I'm going to use some pseudo-code for these examples. I'll mark comment lines with "//" in front. Read these comments to get a heads up on what you're reading below.

Here we see an example of a class for `Porridge`.  Below, I'm declaring a class named "`Porridge`" that requires two things to create it: liquid, and grain

```javascript
class Porridge (liquid, grain)
	// this is a property (remember adjectives in the last post?) that describes how the class is defined.
	define: "food that is made with a grain and liquid.
	CONSISTENCY: "creamy"
	DISH: bowl
	utensil: spoon

	// a method (verb) for making porridge,  notice that it takes liquid and grain from the top
	make(){
		heat liquid
		add grain
		stir
		// this.consistency means "the consistency of the porridge that you are making." Instructions are saying that you should cook until your food's consistency is the same as the one defined above in all caps.
		cook until this.consistency === CONSISTENCY

  plate(dish){
		pour this on DISH
	}

	fire(){
		make()
		plate()
	}
}
```

Now we can make some porridges! Here we are declaring new instantiations of the class of `Porridge`. Or if we're talking like humans that cook: Here are some different recipes for different `Porridges`. You'll see the name of the porridge on the left of the "=". On the right, you'll see something that reads to me "we're using the `Porridge` recipe but using the liquid and grain listed here."

```javascript
rolledOatsOatmeal = new Porridge(water, oats)
creamOfWheat = new Porridge(water, wheatSemolina) // there should be a space there for normal writing, but I'm treating our ingredients like arguments in a program. For now, it's written like a hashtag on Twitter.
grits = new Porridge(milk, corn-grits) //yes, Southerners also cook grits in water
```

Porridge can be pretty basic. Now how about if we want to get fancy?

Some things to notice below:
1. I'm not adding a `plate` method, or the `define` and `CONSISTENCY` properties. These values are set already by saying that we're extending the definition of `Porridge`. Those values are already passed down, or inherited, to this new class definition.
2. `aromatics` is already assigned a value of an empty list. When instantiating, if there is not an `aromatics` argument passed in, then the default will be to add nothing to the steps that call for aromatics.
3. Notice I've changed `grain` to `fodder` in the first line of the class definition. `FancyPorridge` can be made out of potatoes or starchy gourd squashes too. This is more of a cooking note than programming.

```javascript
class FancyPorridge(liquid, fodder, aromatics = [], garnish=[]) extends Porridge
	make()
		heat liquid
		sweat aromatics // that's cooking them until translucent and maybe a little sweet... cooking term, not programming
		blend aromatics // don’t tell grandma I did it this way, Chef made me do it
		toast fodder
		add heated liquid in parts
		add blended aromatics
		finish adding liquid
		cook until this.consistency === CONSISTENCY
	plate(dish, garnish){
		pour this on DISH
		add garnish
	}
```

<figure class="float-right">
<div>
<img src="https://media.giphy.com/media/xjcCk9s2xYh9u/giphy.gif" alt="record scratch moment">
</div>
</figure>Did you see that *Polymorphism* up there? I said what now? Polymorphism means there are many forms of something. In `FancyPorridge`, you'll see that the method `plate()` is redefined with a new step of adding garnish. When we call `plate()` on an instance of `FancyPorridge`, the `plate()` method for `FancyPorridge` will be executed not the one from its parent class `Porridge`. We have overridden a shared method between the two classes. This is an example of *Dynamic polymorphism* (it's as much fun to type as it is to self-narrate to yourself). There's also *static polymorphism*. This happens when there are multiple methods on a class share the same name BUT each one takes a different quantity or type of argument. This would happen if I had a `plate()` method that is just like the one from `Porridge` and then made ANOTHER one here in `FancyPorridge` that takes garnish as an argument. The method that takes garnish should only run if there is a garnish written in the parenthesis when we call `plate()`.

And we'll make some `FancyPorridge` right here.

```javascript
risotto = new FancyPorridge(stock, arborioRice, [onion, thyme], [thymeFlowers, hazelnuts])
congee = new FancyPorridge(stock, longGrainRice, [scallion, ginger, garlic], [cilantroLeaves, scallion, chiliOil])
// no aromatics here, but we set a default
steelCutOats = new FancyPorridge(water, steelCutOats)
kabochaSquashRisotto = new FancyPorridge(stock, kabouchaSquash, [onion, thyme, ginger])
```

We've now made a more specific recipe from the basic one by building on top of the original recipe. When learning to cook we shouldn't be bouncing around from recipe to recipe thinking that's how we gain mastery, we should learn to make the basic version well first, then add or change things from there.

Consider having to write out every step for each of those recipes we've made above each time we wanted to make a porridge. That's seven recipes that look the same except for some small words changed. How tedious! Instead, we've *encapsulated* the information, put it all together in a consistent format. By encapsulating recipes as a method to make a type of food instead of treating each recipe as unique, I think you remove the cognitive work for a programmer or cook of any experience level.

When we hide away the details of how any particular process is done, it's called *abstraction*. I would teach line cooks the `FancyPorridge` method all the time. During service when I would call for the cook to start making a risotto, I did ***NOT*** list each step individually. I would just say, `"Fire, risotto"`, and to a robot cook, I'd call `risotto.fire()`. The person who is executing the risotto knows all the steps already. There's no need to stand there rattling them off for everyone to hear each time that order comes back to the kitchen.

# Recap:
- Recipes and classes give you a framework for creating something. There are descriptions and methods/steps to follow. We can create new versions by extending the class/recipe and adding to the definition.
- Classes allow us to call an object(you read the last post, right?) with an associated action without having to re-write the steps each time we create an object because we've encapsulated all that structure in the class definition.
- `Porridge` does not HAVE to be made from grain but should be creamy.
- Polymorphism is when a method on a class returns a value different than its parent class because it has either been overwritten or other versions of the method exist that take other types or quantities of arguments.
- Dynamic polymorphism is not fun to type.