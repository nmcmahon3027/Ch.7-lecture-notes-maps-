# Ch.7-lecture-notes-maps-

//Maps & the Map Interaface
A map is a set of ordered pairs
{(J, Jane), (B, Bill), (S, Sam)}
(key set, value set)

V.get (Object key) //If I give you the key you can get the value
V.put(K key, V value) //give you a key and a value associated w/ that key and 
                      //put it into the key and value sets

Map Interface

V put(K key, V value)    //when putting something into the map, MUST SUPPLY the key and the value

V remove(Object key)     //when removing, just provide the key and it will get rid of map associated w/ that key

Createing an Index of Words:
(key a word, value different line #'s that it occurs in)

 getOrDefault(); 
ex: 

index.getOrDefault(token, new ArrayList<>()); 

// index = the map that was declared and instantiated prior
//Either: return ArrayList associated w/ token OR return a new ArrayList
//if it has one, it will get it, if not it will return a default ArrayList

**7.3: Hash Tables **

//Hashing: some kind of transformation to the key then storing that in a table

//DONT want a whole table of thousands of characters

int index = unicode % 200 //creating a new table of 200 characters

//Mod (%) unicode character by 200, and computing the index

//ex 41 % 200 = 41 (hashcode = 41)
//   200% 41 = 41   ==>COLLISION (both the same)
//hash code = % 200 ??
//key = 41 ??

OPEN ADDRESSING
//if (index is taken) 
  index++; 

//so, if index is 41, go to 42
//if 42 is taken, go to 43 ....until you find an empty key or an empty slot (or null)

Algorithm for accessing an item in a hash table

if table[index] is null
  the item is not in the table 
else if table[index] is equal to the item
  the item is in the table
else
  continue to search the table by incrementing the index until either the
  item is found or a null is found 
  
  
 //Hash code inserion 
 
//Need to use a CIRCULAR ARRAY 

//Name| hashCode() | hashCode()% 5 (or size of ArrayList) (0 included!!)
//If element index is taken, next index spot and so on...
//THIS is called COLLISION 
//Best way to avoid possibility of collision: Increase table size OR use PRIME NUMBER (fewer factors) 

//If an element is DELETED, CANNOT assign null to it, MARK AS 'DELETED'!

//CHAINING ****
//Alternitive to Opening Addressing
// LinkedList (aka: a bucket)(bucket hashing)

//In a bucket (41 for ex) there will be a LinkedList w/ 'ñ' and ')' 
//Only have to search from those 2 in that bucket 
//% 41 ? in this bucket??
//





  
  
  
  
