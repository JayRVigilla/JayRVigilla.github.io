---
layout: post
title: Classy Diners // object orientation in JavaScript
---

In my teenage years I romanticized diners. Tonight I ended up talking about those greasy spoons with my partner. Now here in lies my problem: I grew up in Sam Jose, CA while she grew up in New Jersey. This isn't some East Coast vs West Coast smack-down, I knew I was just outclassed in this conversation. Jersey diners vs San Jose diners? Fuggedaboudit. She took pity on me and we started defining a diner to even the playing field. 

```javascript
class Diner {
  constructor(name, boothCount) {
    this.name = name;
    this.boothCount = boothCount;
    this.coffee = 0;
  }

  // methods
  welcome() {
    return `Welcome to ${this.name}! We're your local diner. Sit at a table or in\none of our ${this.boothCount} booths. Order from out dessert case, ask if\nwe're serving breakfast, and take a look at our menu! Coffee to start?`;
  }

  dessertCase() {
    return "All cakes are made in a kitchen somewhere. We've put them in\nrotating display case because cakes taste better if you've seen them\nrotate. By the register you can see our muffins and cookies. They taste \nbetter stationary. Coffee?";
  }

  breakfast() {
    return "You want breakfast? Let me check the time to see if we're... nah!\nI'm just kidding. This is a diner. Breakfast is available all the time!\nSo's the seafood pasta. Can I get you a coffee hon?";
  }

  menu() {
    return "All sauces are made from Scratch Brand mixes. Don't worry, we've \nwatered down the hollandaise since all that butter fat will kill you. Most\nfoods are Made Fresh Co's frozen foods. It'll be fast though, there's a\nfryer.";
  }

  orderCoffee() {
    const banter = {
      1: "Here you are, Toots. Cream and sugar? They're on the table already.",
      2: "Made fresh this morning... whatcha mean it's 1 am?",
      3: "::judging look::",
      4: "It's just like water for you isn't it?... oh, that's decaf.",
      else:
        "Can I get you anything else? You've barely ordered and my shift is going to end soon.",
    };
    this.coffee += 1;
    return (this.coffee < 5) ? banter[this.coffee] : banter["else"];
  }
}

```