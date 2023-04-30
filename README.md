Download Link: https://assignmentchef.com/product/solved-cs-3100-project-4-hash-table-indexing
<br>



<h1>Learning Objectives</h1>

Implement a data structure to meet given specifications

Design, implement, and use a closed hash table data structure

Perform empirical analysis of algorithm performance

Use a hash table as an index to a data store

<h1>Overview</h1>

Your task for this assignment is to implement a closed hash table data structure, and to use this hash as the index for rapid searching of a database of student records.

<h1>The HashTable class</h1>

Your hash table should be implemented as an array of <sub>MAXHASH</sub> objects of class Slot. A Slot contains an integer key (the student’s UID), and a value, which can be of any type. The implementaiton of class Slot will be provided for you in the file Slot.h. The value of MAXHASH should initially be #defined to 1000.

Your hash table should accept integer keys, and any type of value. To implement the hash table, you should create a class template called HashTable, implemented inline in the file HashTable.h. Your class should support the following operations (for any class T):

bool HashTable&lt;T&gt;::insert(int key, T value, int&amp; collisions) – Insert a new key/value pair into the table. Duplicate keys are not allowed. This function should return <sub>true</sub> if the key/value pair is successfully inserted into the hash table, and <sub>false</sub> if the pair could not be inserted (for example, due to a duplicate key already found in the table). If the insertion is successful, the number of collisions occuring during the insert operation should be returned in <sub>collisions</sub>.




bool HashTable&lt;T&gt;::remove(int key) – If there is a record with the given key in the hash table, it is deleted and the function returns <sub>true</sub>; otherwise the function returns <sub>false</sub>.




bool HashTable&lt;T&gt;::find(int key, T&amp; value) – If a record with the given key is found in the hash table, the function returns <sub>true</sub> and a copy of the value is returned in <sub>value</sub>. Otherwise the function returns <sub>false</sub>.




<sub> float HashTable&lt;T&gt;::alpha()</sub> ‐ returns the current loading factor, α, of the hash table.




Your hash table should also overload operator&lt;&lt; such that cout &lt;&lt; myHashTable prints all the key/value pairs in the table, along with their hash table slot, to cout.




<h1>The hash and probe functions</h1>

Because this is a closed hash, you will need both a hash function and a probe function. You are free to implement any hash function you like. For example, you may choose to implement some form of the ELFhash, given in Chapter 9 of your textbook, or any other hash function that will work on integer keys. Remember to cite your source if you use code written by anyone other than yourself!

Your hash should use pseudo-random probing to resolve collisions.

<h1>Implementing your database</h1>

Your hash table should be used as an index for a database of student records. Each student record should contain the student’s last name, first name, UID, major, and year (freshman, sophomore, etc.). Student record objects should be stored in the hash table.

<h1>Main program</h1>

You should use your student database in a main program that allows a user to insert, search, and delete from the database.

Example program operation

<table width="659">

 <tbody>

  <tr>

   <td width="659">Would you like to (I)nsert or (D)elete a record, or (S)earch for a record, or (Q)uit?Enter action:  IInserting a new record.Last name:  DoeFirst name:  JaneUID: 1234 Year:  JuniorRecord inserted. Would you like to (I)nsert or (D)elete a record, or (S)earch for a record, or (Q)uit?Enter action:  SEnter UID to search for: 1234Searching… record found—————————-Last name:  DoeFirst name:  JaneUID: 1234Year:  Junior—————————- Would you like to (I)nsert or (D)elete a record, or (S)earch for a record, or (Q)uit?Enter action:  SEnter UID to search for: 2345 Searching… record not found </td>

  </tr>

 </tbody>

</table>

Would you like to (I)nsert or (D)elete a record, or (S)earch for a record, or (Q)uit?

Enter action:  Q Exiting.


