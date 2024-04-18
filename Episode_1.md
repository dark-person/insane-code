# Insane code: Episode 1

I will share some code that make me crazy when tidy up company code base.

Although I don't want to, but I guess this is would be a long term writing. 

To prevent any issue, some variable name & function purpose will be modified, but I could ensure it is still insane.

## Nothing
```
private String nothing = null; // Nothing
```
After checking (in a java class with 8000 lines), it can be confirmed that: this variable has absolute no usage.

Thanks.

## Special Comments
```
if (helloWorld == 1) { // IF hello world
	if (Jesus) { // IF Jesus
      	// ... (Many Line)
      	
		if (isBible) { // If bible
			// ... (Many Line)
		} // END_IF Jesus

	      if (book) { // IF Book
        		// ... (Many Line)
	      } // END_IF book

      		// ... (Many Line)
  	} // END_IF Jesus
	
	// ... (Many Line)

} // END_IF hello world
```
Unknown reason of `IF` and `END_IF` statement, with `// END_IF Jesus` in even wrong position.

Jesus.

## Function usage with talking board
```
public String logError(int i, String msg, User user) {
	switch (i) {
		case 1: return "--No-Connection";
		case 2: return ">>No-Connection";
		case 3: return "--Success";
		case 4: return "--Wrong-User";
		case 5: return "--Info"
	}
}
```
Above function is found as a utility function.
That means everytime you use/read, you need to go back to this function to check number `i` meaning.

Also:
- why "Success" will be used in `logError`??
- why "No-Connection" has two case??

No document, no comment. Jesus.

*Note: This part I have greatly reduce the un-readability. The actual code is more awful than that.*

*Another Note: This anti-pattern has use in more than 10 utility function, all commonly use everywhere. I am talking about >100 java classes.*

## Cat/Monkey Programmer
```
public class hkjfh {
	//...

	public String gwedjq {
		return "";
	}

	// ....
}
```

I am not kidding, this is what the class look like. I have some assumption for this person:
- He has a cat rolling on the keyboard
- He hire an monkey to typing
- He is an Alien

## ResultSet Hell
```
public class Calculator {
	public ResultSet ao = null;
	public ResultSet oo = null;
	public ResultSet ol = null;
	public ResultSet ll = null;
	public ResultSet ok = null;
	public ResultSet io = null;
	public ResultSet eo = null;
	// .... Total > 30 ResultSet declared.
}
```

No comment on this result set naming. No idea why need to use so many.

Jesus, please give me enough wisdom & patience for review this class (>6000 lines).

## Cursed Utils
```
public static class Helper {
	public static void updateSql(Statement stmt, String sql) {
		try {
			stmt.executeUpdate(sql);
		} catch (Exception e) {
		}
	}
}
```
Yes, no Exception handling & logging. This utils have been used almost every classes.

God damn genius.

## Logs: Talking board
Talking board again:
```
public void someFunc() {
	// .....
	System.out.println("10004");

	// ...
	System.out.println("dllm");

	// ...
	System.out.println("30004");

	// ...
	System.out.println("30001");

	//....
	System.out.println("70000");
}
```

Again, no doc, no comments. Who know those line for.

And WTF is dllm??

## Russian Nesting Doll
```
try {
	// ....

	try {
		// ...
	} catch (Exception e) {
		e.printStackTrace();
	}

	try {
		// ...
	} catch (Exception e) {
		e.printStackTrace();
	}

	try {
		// ...
	} catch (Exception e) {
		e.printStackTrace();
	}

} catch (Exception e) {
	e.printStackTrace();
}
```

At least he use `printStackTrace` instead of do nothing.

## Disclaimer
I am not a catholic.


