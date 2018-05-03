# Mosaic JavaScript Naming Convention
*A series of examples with cats*


![Image of cat](https://cdn-images-1.medium.com/max/1400/1*OsMBUUchHRtTT3n-ZX2xbA.jpeg)




## Table of Contents
1. [Before we start](#before-we-start)
1. [Types](#types)
1. [Variants](#variants)


## Before we start 

Let's say we have a cat interface.

```
interface Cat {
	...
}
```



## Types

### Object
Use nouns.

```
// good
const cat = new Cat()

// horrible
const dog = new Cat()
```


### String, Number
Use nouns.

Scenario: we want to use the id of the a cat

```
// good if id is used as a primary key in Cat class
const id = cat.id

// good if catId is used as a foreign key in another class
const catId = cat.id


// horrible
const cat = cat.id

```

### Boolean
Use `is` and `should` when you can.

Scenario: we want to add a boolean on our Cat class to keep track of if a cat is supposed to be displaying on our cat website

```

// bad
interface Cat {
	...
	display: boolean
}

// good
interface Cat {
	...
	isDisplaying: boolean
}

// good
interface Cat {
	...
	shouldBeDisplayed: boolean

}


```

### Array

Use the plural form of whatever the array contains.

```
// good
const cats = [smellyCat, grumpyCat]
```

### Function
Start with a verb. Descript what it does

```
// good
function getCuteCats(): Array<Cat> {
	...
}

// good
function getFluffyCats(): Array<Cat> {
	...
}

// bad
function cuteCats(): Array<Cat> {
	...
}


```

When invoking one of the above functions

```
// good
const cuteCats = getCuteCats()

```


## Variants

### Event listeners
Start with an `on`

```
// good
function onCatImageClick() {
	...
}

```

### Constant
All caps

```
// good
const PIE = 3.1415926535897932
```

### Variables with the same type in one scope
Add adjectives 

```
// good
const cats = [smellyCat, grumpyCat]
const oldCats = cats.filter(cat => cat.age > 20)


// bad 
const cats = [smellyCat, grumpyCat]
const updatedCats = cats.filter(cat => cat.age > 20)


// horrible
let cats = [smellyCat, grumpyCat]
cats = cats.filter(cat => cat.age > 20)

```

### Time sensitive 
Use verb with different tense. Or words like `next`, `before`, etc.

```
// good
componentWillReceiveProps(nextProps) {
	const isRenderingCat = this.props.isRenderingCat
	const willBeRenderingCat = nextProps.isRenderingCat
	...
}

```

## License 

MIT
