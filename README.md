Download Link: https://assignmentchef.com/product/solved-cs342-project1-generic-lists-in-java
<br>
In this project you will implement your own versions of the stack and queue data structures. Although the Java API provides built-in support for them, you will write your own to practice the constructs and language details we have seen in class. That means you are NOT allowed to use any pre existing libraries or classes for this assignment.

Essentially, you are writing your own data structure library that could be used by others in the same way that one can use ArrayList&lt;&gt;. Your library provides data structures as classes, the method calls expected with those data structures and the definition for an iterator so that the clients of your libraries can iterate through the lists in the same way as most generic data structures in Java.

In this simplified version, each data structure is a singly linked list. The stack is LIFO (last in first out) while the queue is FIFO (first in first out). Your implementation must be generic, like ArrayList,  as to allow for different types when each data structure object is instantiated.

You will also implement the Iterator design pattern; allowing users access to a custom Iterator for your data structures.

<strong>Implementation Details: </strong>

You will download and use the Maven project template GLMaven_Project1_SP2020 from Blackboard. You will find a file called GLProject.java in the src folder. This class contains the main method. You should test this template with the Maven command “compile”. This command will both compile your src code and run exec:java; resulting in the line “hello generic lists” being printed and a successful build. The Maven command

“test” will run one test case that fails all the time. You will create a new file, inside of src/ main/java, for each outer class and interface. In comments at the top of the file GLProject.java, please include your name and netid and university email as well as a brief description of your project.

DO NOT add any folders or change the structure of the project in anyway. DO NOT alter the pom.xml file.

Create a generic abstract class called <strong>GenericList&lt;I&gt;</strong>:

This class will contain only two data fields:

<strong>Node&lt;I&gt; head (t</strong>his is the head of the list and should be<strong> private</strong>). <strong>int length </strong>(the length of the list and should be <strong>private</strong>)

This class should include the following methods:

<strong>print()</strong>: prints the items of the list, one value per line. If the list is empty, print “Empty

List”.

<strong>add(I data)</strong>: adds the value to the list. This method is <strong>abstract</strong> since the implementation depends on what the data structure is.

<strong>public I </strong><strong>delete()</strong>: returns the first value of the list and deletes the node. If the list is empty, return null.

<strong>public ArrayList&lt;I&gt; dumpList():</strong> this method stores and returns all values currently in the list into an ArrayList and returns it. At the end of this method, your list should be empty.

<strong>getLength()  setLength()  getHead()  setHead(),</strong> these are getters/setters for private data members head and length.

This class should also define a generic inner class <strong>Node&lt;T&gt;</strong>: It will include two fields: <strong> </strong>

<strong>T data </strong>and <strong>Node&lt;T&gt; next</strong>;

***This class encapsulates a linked list. Defining a Node class and providing two methods that a queue and stack have in common while leaving adding a node to each implementation that inherits from it.***

Create two more classes <strong>GenericQueue&lt;I&gt; </strong>and <strong>GenericStack&lt;I&gt;</strong>. They both should inherit from <strong>GenericList&lt;I&gt;</strong>.

The constructors for each class will take one parameter. That parameter will be a value that will go in the first node of the list encapsulated by each instance of the class. Each constructor should initialize the linked list <strong>head</strong>, with the value passed in by the constructor. Each class should also implement the method <strong>add(I data)</strong>, <strong>GenericQueue </strong>will add to the back of the list while <strong>GenericStack </strong>will add to the front. Each class must also keep track of the length of it’s list using the <strong>length </strong>data field defined in the abstract class.

<strong>GenericQueue </strong>will have the methods <strong>enqueue(I data) </strong>and <strong>public I </strong><strong>dequeue() </strong>which will call the methods <strong>add(I data) </strong>and <strong>delete() </strong>respectively. Enqueue and dequeue merely call <strong>add(I data) </strong>and <strong>delete(). </strong>The reason for this is that a user would expect these calls to be implemented in each of those data structures. You will do the same with <strong>GenericStack </strong>

<strong>GenericStack </strong>will have the methods <strong>push(I data) </strong>and <strong>public I</strong> <strong>pop() </strong>which will call the methods <strong>add(I data) </strong>and <strong>delete() </strong>respectively.

Once implemented, you should be able to create instances of both GenericQueue and GenericStack in main with most primitive wrapper classes. You should be able to add and delete nodes to each data structure instance as well as print out the entire list and check for the length of the list. You must follow this implementation: meaning you can not add any additional data fields or classes. You may add getters/setters as need be.

<strong>Implementing Iterator Design Pattern: </strong>

You are to create an interface called <strong>CreateIterator</strong>. It will have one abstract method: <strong>Iterator createIterator()</strong>. Since both GenericQueue and GenericStack classes iterate through a list the same way, you will want to implement this interface in GenericList.

You must also create a class to contain logic for iterating through your data structure. Call this class <strong>GLIterator</strong>. GLIterator should be a generic class since it provides the logic to iterate through a generic stack and queue.

It should implement the java interface Iterator (java.util.Iterator). You will have to implement two inherited methods: <strong>public boolean</strong> <strong>hasNext(), </strong>checks to see if there is another value in the data structure and returns true or false, and <strong>public I </strong><strong>next(), </strong>returns the current value in the data structure and advances to the next item.

You are expected to fully comment your code and use good coding practices.

<strong>Assignment Details: </strong>

Late work <strong>is accepted</strong>. You may submit your code up to 24 hours late for a 10% penalty. Anything later than 24 hours will not be graded and result in a zero.

<strong><em>We will test all projects on the command line using Maven 3.6.1. You may develop in any IDE you chose but make sure your project can be run on the command line using Maven commands. Any project that does not run will result in a zero. If you are unsure about using Maven, come see your TA or Professor. </em></strong>

Unless stated otherwise, all work submitted for grading *must* be done individually. While we encourage you to talk to your peers and learn from them, this interaction must be superficial with regards to all work submitted for grading. This means you *cannot* work in teams, you cannot work side-by-side, you cannot submit someone else’s work (partial or complete) as your own. The University’s policy is available here: https://dos.uic.edu/conductforstudents.shtml.

In particular, note that you are guilty of academic dishonesty if you extend or receive any kind of unauthorized assistance. Absolutely no transfer of program code between students is permitted (paper or electronic), and you may not solicit code from family, friends, or online forums. Other examples of academic dishonesty include emailing

your program to another student, copying-pasting code from the internet, working in a group on a homework assignment, and allowing a tutor, TA, or another individual to write an answer for you. It is also considered academic dishonesty if you click someone else’s iClicker with the intent of answering for that student, whether for a quiz, exam, or class participation. Academic dishonesty is unacceptable, and penalties range from a letter grade drop to expulsion from the university; cases are handled via the official student conduct process described at https://dos.uic.edu/conductforstudents.shtml.