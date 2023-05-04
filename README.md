Download Link: https://assignmentchef.com/product/solved-csci1300-project-2-recommender-system
<br>
<h1>Objectives</h1>

<ul>

 <li>Be able to use topics learned this semester (control structures, array, fileIO)</li>

 <li>Understand classes and create objects</li>

 <li>Develop a menu driven program</li>

</ul>

<h1>Background</h1>

If you’ve ever bought a book online, the bookseller’s website probably told you what other books you might like. This is handy for customers, but also very important for business.

In 2009, online movie-rental company Netflix awarded one million dollars to the winners of the <a href="https://www.netflixprize.com/">Netfli</a><u>​ </u><a href="https://www.netflixprize.com/">x</a> <a href="https://www.netflixprize.com/">Prize</a><a href="https://www.netflixprize.com/">.</a><u>​</u> The competition simply asked for an algorithm that would

perform 10% better than their own algorithm. Making good predictions about people’s preferences was that important to this company. It is also a very happening field of research that lies at an intersection between math, machine learning and computer science.

So how might we write a program to make recommendations for books?

Consider a user named Rabia. How is it that the program should predict books Rabia might like? The simplest approach would be to make almost the same prediction for every customer. In this case, the program would simply calculate the average rating for all the books in the database, sort the books by rating and then from that sorted list, suggest the top 5 books that Rabia hasn’t already rated. With this simple approach, the only information unique to Rabia used by the prediction algorithm was whether or not Rabia has read a specific book.

We could make a <em>better</em>​ prediction about what Rabia might like by considering her actual ratings in the past and how these ratings compare to the ratings given by other customers. Consider how you decide on movie recommendations from friends. If a friend tells you about a few movies that (s)he enjoyed and you also enjoyed them, then when your friend recommends another movie that you have never seen, you probably are willing to go see it. On the other hand, if you and a different friend always tend to disagree about movies, you are not likely to go to a movie this friend recommends.




A program can calculate how similar two users are by treating each of their ratings as an array/vector and calculating a similarity value based on some calculation (like a dot product, or a sum of squared differences) using the two arrays.




Once you have calculated the pairwise similarity between Rabia and every other customer, you can then identify whose ratings are most similar to Rabia’s. If another user, Suelyn, is most similar to Rabia, we would recommend to Rabia the top books from Suelyn’s list that Rabia hasn’t already rated.

<h1>Project Goal and Design</h1>

In project 2, you will be creating a book recommender system. You will be creating a ​ <strong>Library</strong>​ class that comprises objects from <strong>Book</strong>​ and ​ <strong>User</strong>​ classes.​

<h2>Specifications</h2>

<ul>

 <li>Create a new class <strong>Book, </strong>​ where each instance represents a book and the​ <strong>Library </strong>class stores an array of these books. Define the class in a header file​          and implement it in a separate cpp file.</li>

 <li>Create a new class <strong>User, </strong>​ where each instance represents a person and the​        ratings they have given to books.The <strong>Library </strong>​    class stores an array of these​        Define the class in a header file and implement it in a separate cpp file.</li>

 <li>Create a new class <strong>Library</strong>​ . Define the class in a header file and implement it in​   a separate cpp file.</li>

 <li>You will have to create an instance of <strong>Library </strong>​ class in​          <strong> main() </strong>​          and​     ​ call the​ respective functions to perform various tasks.</li>

</ul>

Tasks: Let’s do this!

<h2>Task 1: Book class</h2>

Create a ​Book​ class, with a separate interface file (​Book.h​) and an implementation file (​Book.cpp​), comprised of the following attributes:




The ​Book​ class has the following attributes:

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Data members (private): </strong></td>

   <td width="312"> </td>

  </tr>

  <tr>

   <td width="312">title​: ​string</td>

   <td width="312">The title of the book</td>

  </tr>

  <tr>

   <td width="312">author​: ​string</td>

   <td width="312">The author of the book</td>

  </tr>

  <tr>

   <td width="312"><strong>Member functions (public): </strong></td>

   <td width="312"> </td>

  </tr>

  <tr>

   <td width="312">Default constructor</td>

   <td width="312">Set ​title​ and ​author​ to an empty string​</td>

  </tr>

  <tr>

   <td width="312">Parameterized constructor</td>

   <td width="312">Takes two ​strings​ assigning title​              ​ and author​, in this order</td>

  </tr>

  <tr>

   <td width="312">getTitle()</td>

   <td width="312">Returns the ​title​ as a ​string</td>

  </tr>

  <tr>

   <td width="312">getAuthor()</td>

   <td width="312">Returns the ​author​ as a ​string</td>

  </tr>

  <tr>

   <td width="312">setTitle(string)</td>

   <td width="312">Sets the player’s ​name​ (and returns nothing)</td>

  </tr>

  <tr>

   <td width="312">setAuthor(double)</td>

   <td width="312">Sets the player’s ​points​ (and returns nothing)</td>

  </tr>

 </tbody>

</table>




<table width="624">

 <tbody>

  <tr>

   <td width="396">Sample test cases (Be sure to test all methods!)</td>

   <td width="228">Expected outputs</td>

  </tr>

  <tr>

   <td width="396">Book hungerGame(“The Hunger Games”,“Suzanne Collins”);  cout &lt;&lt; hungerGame.getTitle() &lt;&lt; endl; cout &lt;&lt; hungerGame.getAuthor() &lt;&lt; endl;</td>

   <td width="228">The Hunger GamesSuzanne Collins </td>

  </tr>

 </tbody>

</table>




For the zip submissions, the files should be named as ​Book.h​ and ​Book.cpp​. Your implementation should be organized nicely into separate files. For the code runner, paste your Book​ class and its implementation (both ​Book.h​ and ​Book.cpp​) in the answer box. Please make sure to test your ​Book​ class on your Cloud 9 / VS code before submitting it to the code runner.

<h2>Task 2: User class</h2>

Create a ​User​ class, with a separate interface file (​User.h​) and an implementation file (​User.cpp​), comprised of the following attributes:

The ​User​ class has the following attributes:

<table width="624">

 <tbody>

  <tr>

   <td width="267"><strong>Data members (private): </strong></td>

   <td width="357"> </td>

  </tr>

  <tr>

   <td width="267">username​: ​string</td>

   <td width="357">The name of the user</td>

  </tr>

  <tr>

   <td width="267">ratings​: ​an array of integer</td>

   <td width="357">An array of integers (size 50) where all the ratings are stored</td>

  </tr>

  <tr>

   <td width="267"><strong>Member functions (public): </strong></td>

   <td width="357"> </td>

  </tr>

  <tr>

   <td width="267">Default constructor</td>

   <td width="357">Set ​username​ to an empty string,​               ​ and initialize all elements of the ​ratings​ array to ​0</td>

  </tr>

  <tr>

   <td width="267">setUsername(string)</td>

   <td width="357">Takes a ​string​ to set ​username​ (and returns nothing)</td>

  </tr>

  <tr>

   <td width="267">setRatingAt(int, int)</td>

   <td width="357">Takes an index i​ and a rating value. If the index and​                the rating value are valid, assign the rating at the index.</td>

  </tr>

  <tr>

   <td width="267">getUsername()</td>

   <td width="357">Returns the name of this user ( ​string​)</td>

  </tr>

  <tr>

   <td width="267">getRatingAt(int)</td>

   <td width="357">If ​i​ is within the bounds of the ​ratings​ array, it returns the rating value at index ​i ​of the ratings array. If not, it returns -1.</td>

  </tr>

 </tbody>

</table>

<h3>User class method: ​ setRatingAt(int, int)​</h3>

This setter takes the index of the rating to be set, and the rating value to set it to. If the index is within the bounds of the ​ratings​ array and the rating value is between 0 and 5, the function sets the rating value at the index and returns true. Otherwise, it returns false.

<table width="442">

 <tbody>

  <tr>

   <td width="111"><strong>Rating</strong></td>

   <td width="331"><strong>Meaning</strong></td>

  </tr>

  <tr>

   <td width="111">0</td>

   <td width="331">Did not read</td>

  </tr>

  <tr>

   <td width="111">1</td>

   <td width="331">Hell no – hate it!!</td>

  </tr>

  <tr>

   <td width="111">2</td>

   <td width="331">Don’t like it.</td>

  </tr>

  <tr>

   <td width="111">3</td>

   <td width="331">Meh – neither hot nor cold</td>

  </tr>

  <tr>

   <td width="111">4</td>

   <td width="331">Liked it!</td>

  </tr>

  <tr>

   <td width="111">5</td>

   <td width="331">Mind blown – Loved it!</td>

  </tr>

 </tbody>

</table>

<em>Method specifications:</em>

<ul>

 <li>The method name: <strong>setRatingAt</strong>​</li>

 <li>The method takes parameters in this order:

  <ul>

   <li>An index of the book, int​</li>

  </ul></li>

</ul>

○    A new rating value, int​

<ul>

 <li>The method sets the new rating value if the index is within the bounds of the rating array and the rating value is valid (i.e. between 0 and 5).</li>

 <li>The method returns a boolean value depending on the following cases:

  <ul>

   <li>True if it successfully updated the rating</li>

  </ul></li>

</ul>

○    False if it did not

<h3>User Class Method: ​ getRatingAt(int)​</h3>

This getter takes the index of a rating. If the index is within the bounds of the ratings​     array,​  then it returns the rating value at the index. If not, it returns -1.




<em>Method specifications:</em>

<ul>

 <li>The method name: <strong>getRatingAt</strong>​</li>

 <li>The method takes parameters in this order:

  <ul>

   <li>An index of the book, int​</li>

  </ul></li>

 <li>The method returns an integer value:

  <ul>

   <li>It returns the rating value if the index is within the boundary of the rating array</li>

  </ul></li>

</ul>

○    It returns -1 if the index is outside of the bounds  of the ratings array




<table width="624">

 <tbody>

  <tr>

   <td width="396">Sample test cases (Be sure to test all methods!)</td>

   <td width="228">Expected outputs</td>

  </tr>

  <tr>

   <td width="396">User hector;  hector.setUsername(“Hector Ramirez”); hector.setRatingAt(0,4); cout &lt;&lt; hector.getUsername() &lt;&lt; endl; cout &lt;&lt; hector.getRatingAt(0) &lt;&lt; endl;</td>

   <td width="228">Hector Ramirez4</td>

  </tr>

 </tbody>

</table>




For the zip submissions, the files should be named as User.h​         and ​     User.cpp​        . For the code​  runner, paste your Book​           class and its implementation (both ​    User.h​              and ​     User.cpp​        )​ in the answer box. Please make sure to test your User​              class on your Cloud 9 / VS code before​          submitting it to the code runner.

<h3>Task 3: Library Class</h3>

Create a ​Library​ class, with a separate interface file (​Library.h​) and an implementation file (​Library.cpp​), comprised of the following attributes:




The ​Library​ class has the following attributes:

<table width="624">

 <tbody>

  <tr>

   <td colspan="2" width="624"><strong>Data members (private): </strong></td>

  </tr>

  <tr>

   <td width="254">books​:  an array of ​Book​ objects</td>

   <td width="370">The books in the library. Its size is 50 (constant)</td>

  </tr>

  <tr>

   <td width="254">users​:  an array of ​User​ objects</td>

   <td width="370">The users in the library. Its size is 100 (constant)</td>

  </tr>

  <tr>

   <td width="254">numBooks​: ​int</td>

   <td width="370">The number of books in the library</td>

  </tr>

  <tr>

   <td width="254">numUsers​:  ​int</td>

   <td width="370">The number of users in the library</td>

  </tr>

  <tr>

   <td colspan="2" width="624"><strong>Member functions (public): </strong></td>

  </tr>

  <tr>

   <td width="254">Default constructor</td>

   <td width="370">Sets both ​numBooks​ and ​numUsers​ to 0</td>

  </tr>

  <tr>

   <td width="254">getNumBooks()</td>

   <td width="370">Returns  ​numBooks​ as an ​integer</td>

  </tr>

  <tr>

   <td width="254">getNumUsers()</td>

   <td width="370">Returns  ​numUsers​ as an ​integer</td>

  </tr>

  <tr>

   <td width="254">readBooks(string)</td>

   <td width="370">Takes a file name (a ​string​), reads a list of books, and stores them into the ​books​ array for this library. It returns the total number of books stored in the ​books array as an ​integer​.</td>

  </tr>

  <tr>

   <td width="254">readRatings(string)</td>

   <td width="370">Takes a file name (a ​string​), reads a list of users and their ratings and stores them into the ​users​ array for this library. It returns the total number of users stored in the ​users​ array as an ​integer​.</td>

  </tr>

  <tr>

   <td width="254">viewRatings(string, int)</td>

   <td width="370">Takes a username and a minimum rating value. It prints all the books that the user has rated with a value greater than or equal to the minimum rating value. The function does not return anything.</td>

  </tr>

  <tr>

   <td width="254">printAllBooks()</td>

   <td width="370">Prints all books stored in the ​books​ array with average ratings. The function does not return anything.</td>

  </tr>

  <tr>

   <td width="254">addUser(string)</td>

   <td width="370">Takes a username and adds a user with that name to the ​users​ array. The function does not return anything.</td>

  </tr>

  <tr>

   <td width="254">updateRating(string,string</td>

   <td width="370">Takes username, title, and a new rating (in this order )</td>

  </tr>

  <tr>

   <td width="254">,int)</td>

   <td width="370">and updates the rating value of this title for this user. The function does not return anything.</td>

  </tr>

  <tr>

   <td width="254">getRecommendations(string)</td>

   <td width="370">Takes the username and prints the first 5 book recommendations. The function does not return anything.</td>

  </tr>

 </tbody>

</table>




<h4>Library Class Method: ​ readBooks(string)​</h4>

It takes a file name, reads a list of books, and stores them into the books​  array. Each line has​    an author and a title separated by a comma. The function returns the number of the total books stored in the books​ array. If the file cannot be opened, the function should return ​           -1​          .​




Sample file (<a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books.txt?forcedownload=1"><strong>books.tx</strong></a><u>​ </u><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books.txt?forcedownload=1"><strong>t</strong></a><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books.txt?forcedownload=1">)</a><u>​ </u>:

Douglas Adams,The Hitchhiker’s Guide To The Galaxy

Richard Adams,Watership Down

Mitch Albom,The Five People You Meet in Heaven

Laurie Halse Anderson,Speak

Maya Angelou,I Know Why the Caged Bird Sings

Jay Asher,Thirteen Reasons Why




<em>Method specifications:</em>

<ul>

 <li>The method name: <strong>readBooks</strong>​           The method parameter:

  <ul>

   <li>A filename, string​</li>

  </ul></li>

 <li>The function returns an integer value depending on the following conditions (checked in this order)

  <ul>

   <li>It returns -1​ if the file cannot be opened.​</li>

  </ul></li>

</ul>

○    It returns the total number of books if the books​ array is full​

○    It returns the total number of books stored in the array if it can successfully read the list of books.

<ul>

 <li>Important:

  <ul>

   <li>The method stores all the books stored without replacing them. For example, if it reads a file with 5 books (the first time it is called) and then another file with 3 books (the second time it is called), then all 8 books should be stored in the books array and it returns 8 (the second time it is called).​</li>

  </ul></li>

</ul>




<em>How to test it? </em>

<ul>

 <li>You can test the method is working or not by 1) calling it in your main and see if it returns the correct value, 2) calling it multiple times to see if the function returns the total number of the books stored in the array, 3) implement the other methods (viewRatings​ and​ printAllBooks)​ to see if it prints the books stored in the array</li>

</ul>

<h4>Library Class Method: ​ readRatings(string)​</h4>

It takes a file name and reads usernames and their ratings. A username is stored on one line, and the user’s ratings are stored on the following line, separated by commas.




Sample file (<a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings.txt?forcedownload=1"><strong>ratings.tx</strong></a><u>​ </u><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings.txt?forcedownload=1"><strong>t</strong></a>):​

cynthia

4,3,1,0,3,0,5,1,5,2,2,2,1,4,4,2,0,1,1,2 diane

3,1,1,0,2,2,3,1,0,1,4,3,1,2,1,1,5,2,4,0 joan

3,1,2,0,2,2,4,3,0,2,2,4,5,2,2,1,4,1,1,3




In the above sample file, Cynthia rated 4 for the book at index 0 , rated 3 for the book at index 1, and so on. Diane rated 3 for the book at index 0, rated 1 for the book at index 1.




Each rating is mapped to the book by the index. As shown in below, the rating value at index 0 of the ratings​ array (for any particular user) will be that user’s rating for the book at index 0 of​     the books​ array. The same holds for ratings and books at all other indices of the ​ ratings ​ and​ books arrays.​

<em> </em>

<em> </em>

<em>Method specifications:</em>

<ul>

 <li>The method name: <strong>readRatings</strong>​         The method parameter:

  <ul>

   <li>A filename, string​</li>

  </ul></li>

 <li>The function returns an integer value depending on the following conditions (in this order)

  <ul>

   <li>It returns -1 if the file cannot be opened.</li>

  </ul></li>

</ul>

○    It returns the total number of users if the users​ array is full​

○    It returns the total number of users stored in the array if it can successfully read the list of users and ratings.

<ul>

 <li>Important:

  <ul>

   <li>The method stores all the users stored without replacing them. For example, if it reads a file with 5 users (the first time it is called) and then another file with 3 users (the second time it is called), then all 8 users and their ratings should be stored in the users​ array and it returns 8 (the second time it is called).​</li>

  </ul></li>

</ul>




<em>How to test it? </em>

You can test the method is working or not by 1) calling it in your main and see if it returns the correct value, 2) calling it multiple times to see if the function returns the total number of the users stored in the array, 3) implement the other methods (viewRatings​             and​       printAllBooks)​ to see if it prints the users and their ratings stored in the array




<h5>Library Class Method: ​ viewRatings(string, int)​</h5>

It takes a username and a minimum rating value. It prints all the books the user has rated with a value that is greater than or equal to the minimum rating value in the format as shown below. The username search should be case insensitive (i.e. Ben​   , ​ BEN​   , ​ BeN​   are the same ​ ben​       )​ . Recall that a rating value of 0 means that the user has not rated the book yet.




Expected output format:

Here are the books that megan rated

Title : The Hitchhiker’s Guide To The Galaxy

Rating : 5

—–

Title : The Five People You Meet in Heaven

Rating : 2

—–




<em>Method specifications:</em>

<ul>

 <li>The method name: <strong>viewRatings</strong>​</li>

 <li>The method parameters (in this order):</li>

</ul>

○    A username, string​

○    A minimum rating, int​

<ul>

 <li>The function does not return anything.</li>

</ul>




<em>Edge cases </em>​(should be handled in this order):

<ul>

 <li>The library has not been initialized yet. If there are no books or no users in the array, it cannot print the ratings. Display the following message:</li>

</ul>




The library has not been fully initialized.




<ul>

 <li>There might be a case where the user does not exist. When you search for a username, it should be case insensitive. If the username is not found, then it displays the following message. &lt;​ username&gt; is an actual username passed into the method.​</li>

</ul>




&lt;username&gt; does not exist.




<ul>

 <li>If you find a username, but there are no ratings that are greater than or equal to the minimum rating value, display the following message:</li>

</ul>




&lt;username&gt; has not rated any books with &lt;min rating&gt; or higher.




Sample Run 1 for <strong>Akriti </strong>​ with minRating = 4 (​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>books_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>t</strong></a> and ​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>users_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>t</strong></a><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1">)</a><u>​ </u>:

Here are the books that Akriti rated

Title : Title1

Rating : 5

—– Title : Title5

Rating : 4

—–




Sample Run 2 for <strong>Keya </strong>​ with minRating = 2 (​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>books_mini.tx</strong></a><u>​ </u><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>t</strong></a> <u>​ </u>and <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>users_mini.tx</strong></a><u>​ </u><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>t</strong></a><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1">)</a><u>​ </u>:

Keya has not rated any books with 2 or higher.




<em>How to test it? </em>

After creating an instance of the Library​     class, you can call ​      readBooks​     and ​     readRatings​ methods, then call viewRatings​     to see if you can get the same output as above.​

Library Class Method: ​ <strong>printAllBooks()</strong>​

It would be helpful to see a list of all the books​           stored in the array, along with their average​ ratings. The average rating should be formatted with two-digit precision. If the rating value is 0, it means that the user has not rated the title yet. So we don’t include it in the calculation.

<em>Methods specifications:</em>​

<ul>

 <li>The method name: <strong>printAllBooks</strong>​</li>

 <li>The method does not take any parameters.</li>

 <li>The function does not return anything.</li>

</ul>

<em>Edge case</em>​:

<ul>

 <li>The library has not been initialized yet. If there are no books or no users in the array, it cannot print the ratings. Display the following message:</li>

</ul>

The library has not been fully initialized.

Sample Run: (<a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>books_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>t</strong></a> and ​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>users_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>t</strong></a>):​

(3.33) Title1 by Author1

(3.00) Title2 by Author2

(2.67) Title3 by Author3

(4.00) Title4 by Author4

(3.00) Title5 by Author5

<em>How to test it? </em>

After creating an instance of the Library​     class, you can call ​      readBooks​     and ​     readRatings​ methods, then call printAllBooks​               to see if you can get the same output as above.​

<h4>Library Class Method: ​ updateRating(string,string,int)​</h4>

It takes a username, title of a book, and the user’s new rating for the book. It updates the rating value if the username and title exist in the arrays and the rating value is valid (between 0 and 5). When you search for a username and title, it should be case insensitive (i.e. Ben​     , ​ BEN​   , ​ BeN​   are​        the same ben​ ).​




<em>Methods specifications:</em>​

<ul>

 <li>The method name: <strong>updateRating</strong>​</li>

 <li>The method parameters (in this order):</li>

</ul>

○    A username, string​

○    A title, string​

○    A new rating, int​

<ul>

 <li>The function does not return anything.</li>

</ul>




<em>cases: </em>​(should be handled in this order):

<ul>

 <li>The library has not been initialized yet. If there are no books or no users in the array, it cannot print the ratings. Display the following message:</li>

</ul>




The library has not been fully initialized.




<ul>

 <li>There might be a case where the user does not exist. When you search for a username, it should be case insensitive. If the username is not found, then it displays the following message. &lt;​ username&gt; is an actual username passed to the method.​</li>

</ul>




&lt;username&gt; does not exist.




<ul>

 <li>If the new rating value is invalid, we cannot update the rating value. Valid ratings are between 0 and 5 (inclusive). If the new rating value is invalid, then display the following message:</li>

</ul>




&lt;rating&gt; is not valid.




<ul>

 <li>There is also a case where the title does not exist in the library. If so, display the following message: &lt;​ title&gt; is an actual book title passed to the method.​</li>

</ul>




&lt;title&gt; does not exist.




<ul>

 <li>Once we check all the above conditions, we can update the user’s rating for the given title. If it is successful, then display the following message:</li>

</ul>




The rating has been updated.

Library Class Method: <strong>addUser(string)</strong>​

We always get new users. Let’s create a method to add a new user to the library. It takes a username and adds it to the users​    array, provided the username does not already exist and​     there is a space in the array. When you search for a username, it should be case insensitive

(i.e. Ben​ , ​ BEN​ , ​ BeN​ are the same ​ ben​ ).​




<em>Methods specifications:</em>​

<ul>

 <li>The method name: <strong>addUser</strong>​        The method parameter:</li>

</ul>

○    A username, string​

<ul>

 <li>The function does not return anything.</li>

 <li>The new user has not rated any books yet. So all the ratings for the new user should be</li>

</ul>

<ol>

 <li></li>

</ol>




<em>cases: </em>​(should be handled in this order):

<ul>

 <li>The library might not have a space to add a new user. (It already has 100 users). If so, display the following message. &lt;​ username&gt; is an actual username passed into the​</li>

</ul>




The library is already full. &lt;username&gt; was not added.




<ul>

 <li>There might be a case where the user already exists. When you search, it should be case insensitive (i.e. Ben, ben, BEN are the same ben). If the username​ already exists​ in the users array, print the following message:</li>

</ul>




&lt;username&gt; does already exist.




<ul>

 <li>Once you check that there is a space in the users​ array and the username does not​       exist, then the username should be added. If successful, print the following message:</li>

</ul>




Welcome to the library &lt;username&gt;

<h4>Library Class Method: ​ getRecommendations(string)​</h4>

It will recommend book titles a user might enjoy based on the ratings of another user who likes similar books.




<em>Methods specifications:</em>​

<ul>

 <li>The method name: <strong>getRecommendations</strong>​        The method parameter:</li>

</ul>

○    A username, string​

<ul>

 <li>The function does not return anything.</li>

</ul>




<em>How to find books to recommend?  </em>

You recommend books based on the most similar user. You can calculate how similar two users are by calculating the sum of square differences (SSD).

<strong> </strong>

The SSD is calculated by summing the squares of the differences between the corresponding elements in the two ratings array of two users. Because our similarity metric is based on difference, more similar users will have smaller similarity values. Let’s say we want to generate recommendations for Ben. In the equation below, A​ represents Ben’s rating for ​  i​ th book and B​              represents the other user’s rating for i​ th book.​ <strong> </strong>

<strong> </strong>

Once you find the user most similar to the given user (Ben in this example), print the first 5 books that the most similar user rated as 3 or higher, that the given user (Ben) has not rated yet (i.e. the rating is 0).




<strong>Note</strong>:​ If the user has not rated any books, then the user cannot be the most similar user.

<strong> </strong>

<strong> </strong>

<strong> </strong>

For example, suppose we have 5 books (stored in the books array in this order):

Lab Girl

The Rosie Project

The Catcher in the Rye

Unbelievable

A Man of the People

And 5 users in the users array in the library:

<table width="196">

 <tbody>

  <tr>

   <td width="96">Akriti:</td>

   <td width="100">[5, 0, 2, 0, 4]</td>

  </tr>

  <tr>

   <td width="96">Malvika:</td>

   <td width="100">[4, 3, 3, 5, 4]</td>

  </tr>

  <tr>

   <td width="96">Vipra:</td>

   <td width="100">[0, 0, 0, 0, 1]</td>

  </tr>

  <tr>

   <td width="96">Monika:</td>

   <td width="100">[0, 0, 0, 0, 0]</td>

  </tr>

  <tr>

   <td width="96">Keya:</td>

   <td width="100">[1, 0, 3, 3, 0]</td>

  </tr>

 </tbody>

</table>




Based on the above data, If you find recommendations for Akriti, then calculate the similarity between:




Once you calculate the pairwise SSD between Akriti and every other user, you can then identify the user whose ratings are most similar to Akriti’s. In this case, 17 is the smallest SSD value among the users. Therefore, Malvika is the most similar to Akriti.




Once you figure out the most similar user, print the first 5 books the most similar user (Malvika) rated 3 or higher, that the given user (Akriti) has not rated yet. In this case, it prints the following books:

The Rosie Project

Unbelievable

Akriti has not rated Book1 and Book3 and Malvika rated those books 3 o r higher, so it prints them.




Based on the above data, If you find recommendations for Vipra, then we do the same calculation for the SSD score:

<ul>

 <li>Vipra and Akriti: SSD = 38</li>

 <li>Vipra and Malvika: SSD = 68</li>

 <li>Vipra and Monika: SSD = 1</li>

 <li>Vipra and Keya: SSD = 20</li>

</ul>




In this case, the most similar user should be Keya. The SSD between Vipra and Monika are the lowest (SSD = 1). However, since Monika has not rated any books yet (all the ratings are 0), she cannot be the most similar user.




Once you figure out the most similar user, you find the books in which Vipra has not rated and Keya rated 3 or higher. Then, it will prints:

The Catcher in the Rye

Unbelievable




Vipra has not rated the first four books, but of these, the books Keya liked (rating is 3 or higher) are only The Catcher in the Rye and Unbelievable.




<em>Edge cases (in this order):</em>

<ul>

 <li>The library has not been initialized yet. If there are no books or no users in the library, it cannot find recommendations. Display the following message:</li>

</ul>




The library has not been fully initialized.




<ul>

 <li>There might be a case where the user does not exist. When you search, it should be case insensitive (i.e. Ben, ben, BEN are the same ben). If the username​ does not exist​ in the users array, print the following message:</li>

</ul>




&lt;username&gt; does not exist.




<ul>

 <li>After you find the most similar user, but there might be no books to recommend at the moment. If so, display the following message:</li>

</ul>




There are no recommendations for &lt;username&gt; at present.




<ul>

 <li>There might be the case where there are more than 5 books to recommend. In that case, we recommend only the first 5 books.</li>

</ul>




Sample Run: Recommendations for <strong>Akriti</strong>​ :​ (<a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>books_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>t</strong></a> and ​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>users_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>t</strong></a>):​

Here is the list of recommendations

The Rosie Project by   Graeme Simsion​

Unbelievable by Katy Tur




Sample Run: Recommendations for <strong>Vipra</strong>​ :​ (<a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>books_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>t</strong></a> and ​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>users_mini.tx</strong></a>​ <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>t</strong></a>):​

Here is the list of recommendations

The Catcher in the Rye by    J. D. Salinger​

Unbelievable by Katy Tur




Sample Run: Recommendations for <strong>Malvika</strong>​ :​ (<a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>books_mini.tx</strong></a><u>​ </u><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/books_mini.txt?forcedownload=1"><strong>t</strong></a> <u>​ </u>and <a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>users_mini.tx</strong></a><u>​ </u><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1"><strong>t</strong></a><a href="https://moodle.cs.colorado.edu/pluginfile.php/214950/mod_folder/content/0/ratings_mini.txt?forcedownload=1">)</a><u>​ </u>:

There are no recommendations for Malvika at present.




The most similar user for Malvika is Akriti (SSD = 36). However, Malvika has rated all the  books Akriti has rated, so there are no books to recommend.




For the zip submissions, the files should be named as ​Library.h​ and ​Library.cpp​. For the code runner, paste your ​Book​ class and its implementation, ​User​ class, ​Library​ class and its implementation (both ​Book.h​, ​Book.cpp​, ​User.h​, ​User.cpp​, ​Library.h​ and Library.cpp​) in the answer box. Please make sure to test your ​Library​ class on your Cloud 9 / VS code before submitting it to the code runner.

<h3>Task 4: Let’s make main()​</h3>

Now, let’s put it all together in the ​main()​ function. Create a ​project.cpp​ and write the main()​ function in the file. To make it user-friendly, we’ll create a menu option and call the appropriate methods (that you created) for each option.

The menu has the following options:

Select a numerical option:

======Main Menu=====

<ol>

 <li>Read books</li>

 <li>Read ratings</li>

 <li>View ratings</li>

 <li>Print all books</li>

 <li>Update a rating</li>

 <li>Add a user</li>

 <li>Get recommendations</li>

 <li>Quit</li>

</ol>

The menu will run in a loop, continually offering the user the options until they opt to quit. You need to fill in the code for each of the options. Be sure to use the methods you wrote in Task 3.

<strong>Invalid option</strong>​: If the user enters invalid option, then print

Invalid option.




<strong>Option1: Read books </strong>

The program asks for a filename of a book list and displays the total number of the books stored in the array. If the file cannot be opened, then it prints ​No books saved to the database.




Sample Run 1 (​<strong>bold</strong>​ is user input)

Enter a book file name:

<h4>books.txt</h4>

Total books in the database: 50

Sample Run 2 (<strong>bold</strong>​ is user input)​

Enter a book file name:

<h4>this_file_does_not_exist.txt</h4>

No books saved to the database.




<strong>Option2: Read ratings  </strong>

The program asks for a filename of a rating list and displays the total number of the users stored in the array. If the file cannot be opened, then it prints No users saved to the​         database.




Sample output 1 (<strong>bold</strong>​ is user input)​

Enter a user file name:

<h4>ratings.txt</h4>

Total users in the database: 50




Sample Run 2 (<strong>bold</strong>​ is user input)​

Enter a user file name:

<h4>this_file_does_not_exist.txt</h4>

No users saved to the database.




<strong>Option3: View ratings  </strong>

The program asks for a username and a minimum rating value. Then, it calls the <strong>viewRating</strong>​    method.




Sample Run (<strong>bold</strong>​ is user input)​

Enter a user name:

<h4>Akriti</h4>

Enter a minimum rating:

<strong>2 </strong>

Here are the books that Akriti rated

Title : Lab Girl

Rating : 5

—–

Title : The Catcher in the Rye

Rating : 2

—–

Title : A Man of the People

Rating : 4

—–




<strong>Option4: Print all books </strong>

If option 4 is selected, then it will call the ​<strong>printAllBooks</strong>​ method.

<strong> </strong>

<strong>Option5: Update user’s rating </strong>

The program asks for a username, a title, and a new rating. Then, it will call the ​<strong>updateRating</strong> method.




Sample Run (​<strong>bold</strong>​ is user input)

<table width="624">

 <tbody>

  <tr>

   <td width="624">Enter a user name:<strong>Akriti </strong>Enter a book title: <strong>The Catcher in the Rye </strong>Enter a new rating:<strong>3 </strong>The rating has been updated.</td>

  </tr>

 </tbody>

</table>




<strong>Option6: Add a user </strong>

The program asks for a username. Then, it will call the ​<strong>addUser</strong>​ method.




Sample Run (​<strong>bold</strong>​ is user input)

Enter a user name:

<h4>Divya</h4>

Welcome to the library Divya




<strong>Option7: Get recommendations </strong>

The program asks for a username. Then, it will call the ​<strong>getRecommendations</strong>​ method.




Sample Run 1 (​<strong>bold</strong>​ is user input)

Enter a user name:

<h4>Akriti</h4>

Here is the list of recommendations

The Rosie Project by ​  Graeme Simsion

Unbelievable by Katy Tur




<strong>Option8: Quit  </strong>

Before exiting the program, print ​Good bye!




For the zip submissions, the files should be named as ​project.cpp​. For the code runner, paste your ​main()​, ​Book​ class and its implementation, ​User​ class, ​Library​ class and its implementation (both ​Book.h​, ​Book.cpp​, ​User.h​, ​User.cpp​, ​Library.h​ and

Library.cpp​) in the answer box. Please make sure to test your ​main​ on your Cloud 9 / VS code before submitting it to the code runner.


