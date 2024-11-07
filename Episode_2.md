# Insane code: Episode 2

Episode 2 is back. More crazy code.

To prevent any issue, some variable name & function purpose will be modified, but I could ensure it is still insane.

## Useless if

``` java
if (false) {
	// Many many code
} else {
	// Many & many & many code
}
```

Your eye is completely okay. It is actually `if (false)`, I do not modified this part.

## Confusing classes naming

I think I need to give you some idea before talking about these code.

We are given some product code such as ABCDEF, KFGEH, and we need to process these product data.

Then lets see what I saw

```java
/** Class for product ABCDEF. */
public class productABKDEF {
	// Many Many Many code
	
	private void handle() {
		// ....
		Logger.trace("<Product ABCDEF> ....");
		// ....
	}
}
```

Every product code in above is correct except the class name. Well done.

## Please do not copy directly

```java
public class somethingClass {
	// ....
	
	public void handle() {
		// ....
		Logger.getLogger(anotherClass.class.getName()).log(Level.SEVERE, null, ex);
		// ... 
	}
	
	// ....
}
```

They took `anotherClass` class name in logger. Pretty sure no one really look at the log file.

## Creative on naming class

Some background: A product code `ABCDEF` , has a complete name: "Easy Handling Product".

Then I have found a class like this:

```java
/** Easy Handling Product. */
public class RelaxHandProduct {
	// .....
}
```

I am glad that IDE has function to search keyword (include comment) in all file.

## Purpose of Utils

Firstly, I have found a utility classes in some package `utils`

```java
package com.example.utils;

public class Utils {
	// ..........
	
	public static int calcSomething(int x, int y) {
		// Utils body...
	}

	// ...........
}
```

*Disclaimer: Actual naming is much worse than you see. I watered down it.*

Then I found these code:

```java
package com.example.hello.world.abc;

public class SomeClass {
	
	// .... Thousand line of code
	
	private int calcSomething(int x, int y) {
		// Utils body...
	}
	
	// .... Thousand line of code
}
```

Nick Young.jpg

## Twins

Same as above utils

```java
package com.example.utils;

public class Utils {
	// ..........
	
	public static int calcSomething(int x, int y) {
		// Utils body...
	}

	// ...........
}
```

Then I found one class in `com.example.hello.world.utils`:

```java
package com.example.hello.world.utils;

public class Utils {
		
	public static int calcSomething(int x, int y) {
		// Utils body...
	}
}
```

WTF x2. Nick Young x2

## Genius Switch Case

```java
public void doSomething(String val) {
	int iCode = 0;
	
	if (val == "ABC") {
		iCode = 1;
	} else if (val == "DEF") {
		iCode = 2;
	} else if (val == "GHI") {
		iCode = 3;
	} 
	// ....... Multiple else if case
	
	// ........ Many code .....
 
 	switch (iCode) {
 		case 0:
 			// Many Lines...
 			break;
 		case 1:
			// Many Lines...
 			break;
 		case 2:
 			// Many Lines...
 			break;
 		case 3:
 			// Many Lines...
 			break;
 			
 		// .... Many case, but no default
 	}
}
```

Please note there has at least 10 case.

Readability drop to negative value. Thanks.
