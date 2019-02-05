# FaqJava


 #1-) Difference between Map and HashMap ?
  

 ##2-) How do I compare strings in Java? 

   source of answer :https://stackoverflow.com/questions/513832/how-do-i-compare-strings-in-java

  - == tests for reference equality (whether they are the same object).

  - .equals() tests for value equality (whether they are logically "equal").

  - Objects.equals() checks for null before calling .equals() so you don't have to (available as of JDK7, also available in Guava).

  - String.contentEquals() compares the content of the String with the content of any CharSequence (available since Java 1.5). 
  Consequently, if you want to test whether two strings have the same value you will probably want to use Objects.equals()


 You almost always want to use Objects.equals(). In the rare situation where you know you're dealing with interned strings, you can use ==.

 From https://docs.oracle.com/javase/specs/jls/se8/html/jls-3.html#jls-3.10.5 String Literals:
 
 Moreover, a string literal always refers to the same instance of class String.
 This is because string literals - or, more generally,
 strings that are the values of constant expressions https://docs.oracle.com/javase/specs/jls/se8/html/jls-15.html#jls-15.28) - 
 are "interned" so as to share unique instances, using the method String.intern.

 Similary example can be found here : https://docs.oracle.com/javase/specs/jls/se8/html/jls-3.html#d5e1634
