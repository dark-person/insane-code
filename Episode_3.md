# Insane code: Episode 3

Serial is still going on. More crazy code.

To prevent any issue, some variable name & function purpose will be modified, but I could ensure it is still insane.

## Great Mind no one know

```java
public PdfPCell getNoBorderCell(String data, Font f1, int span, float padding, 
    boolean center, boolean bottom) {

    PdfPCell cell = new PdfPCell(new Phrase(data, f1));
    cell.setColspan(span);
    cell.setPadding(padding);
    cell.setBorder(PdfPCell.NO_BORDER);

    if (center) {
        cell.setHorizontalAlignment(PdfPCell.ALIGN_CENTER);
    }

    if (bottom) {
        cell.setVerticalAlignment(PdfPCell.ALIGN_BOTTOM);
    }

    return cell;
}
```

I really not understand why center & bottom flag points to different alignment.

## Ignore my statement

```java
String sql = "";

sql = "SELECT ....." // Hundred lines

sql = "WITH T1 AS (...." // Hundred Lines
```

Thanks contributing to readability.

## Nothing inside

```java
private void handleSomething() {
    // .... Many codes

    // Get Criteria from database
    // .... Code to query
    if (criteria) {
        doSomeThingSeemsVeryImportant();
    }
}

private void doSomeThingSeemsVeryImportant() {

}
```

Yes, `doSomeThingSeemsVeryImportant` is complete empty. But the function name state it should do some important action.

## Cast by myself

```java
age = (int) rs.getDouble("someone_age");
```

I doubt there should be a function call `rs.getInt`.

## Great Connection

```java
public boolean isConnectSuccess() {
    boolean isConnected = false;

    if (conn == null) {
        // Do some stuff to connect..
        // ....

        isConnected = true;
    }

    return isConnected;
}
```

As you see, if connection is not null, this function always return false.

## Useless Condition

```java
writer.getPageNumber() % 1 == 0 ? 45 : -45
```

As primary school teacher said, every integer should be divisible by 1.

## Truth on Extreme long class

This class make my IDE extreme lag, due to its long length & dozen warning and linting issue.

```java
public class SomeClass() {

    public boolean someFunc(){
        // Thousand lines with many linting issue
    }

    // Comment blocks
    /*
    public boolean someFunc(){
        // Thousand lines with many linting issue
    }
    */

    // Completely unused function
    public boolean someFuncOld(){
        // Thousand lines with many linting issue
    }

    // Completely unused
    private String someUtils(int someValue) {
        // Hundred lines with many linting issue
    }
}
```

## I don't like your name

```java
String file = filepath;
FileOutputStream fos = new FileOutputStream(file);
```

That may be reason of declare a new variable.

## Extra: Warning that you may not solve

> A "Brain Method" was detected. Refactor it to reduce at least one of the following metrics: LOC from 1975 to 64, Complexity from 97 to 14, Nesting Level from 4 to 2, Number of Variables from 84 to 6. sonarlint(java:S6541)

Capture from VSCode Sonarlint. Interesting.

## Disclaimer

Actual Situation is worse than above mentioned.
