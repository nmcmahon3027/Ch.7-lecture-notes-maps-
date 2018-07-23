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

//**Section 7.4: Implementing the hash table**

//Interface KWHashMap

    V get(Object key)  
    //returns the value associated w/ specified key. Returns null if key is not present
    
    boolean isEmoty() 
    //returns true if this table contains a no key-value mappings
    
    V put(K key, V value)
    //assoiciates specified value w/ the specified key
    //Returns the previous value assoiciated w/ the specified key
    //OR null if there was no mapping for the key
    
    V remove(Object key)
    //Removes the mapping for this key from this table if it is present (optional operation)
    //Returns previous value associated w/ specified key
    //OR null if there was no mapping
    
    int size()
    //Returns size of table
    
    Class entry
    
    Book
    private final K key  //final K (generic) (object type) 
    
    Lab8: Class: Entry
     //private static class Entry <Object type for Key, Object type for Value> {
     
     private static class Entry<K, V> {
     
        private finalk key;  //the key
        
        private V value;    //the value
        
        public Entry(K key, V value) {    //CONSTRUCTOR
            this.key = key;
            this.value = value;
            }
   
         public K getKey() {   //Getter
            return key;
            }
            
          public V getValue() { //Getter
            return value;
            }
            
            public V setValue(V val) { //Setter, REPLACE old value w/ new value
              V oldVal = value;
              value = val;
              return oldVal;
              }
              
        }
        
  //Class: HashTableOpen
  
  //Method:   private int(Object key)   //Returns index of specified key if present in table
                                        //Otherwise returns index of the first available slot
              private void rehash()     //Doubles capacity of table & perm. removes deleted items
              

//NOTE: element same as bucket

//Youtube Ex.

      import java.util.HashMap;
      
      public class BasicHashMaps
      {
        static HashMap<String, Boolean> map = new HashMap<>();
        public static void main(String[] args)
        {
          map.put("Kenny", true); //whenever we get the value Kenny form HashMap we get true
          map.put("Joe", false);
          
          map.get("Kenny"); //returns boolean value
          
          if(map.containsKey("Kenny")) System.out.println("  ");
          
          if(map.containsValue(Boolean.FALSE)) System.out.println(2);
          
          for(String s: map.keySet()) //loop through keys
          {
              System.out.println(3);  //for string IN map.ketSet()
          }
          for(Boolean b: map.values()) //loop through values
          {
              System.out.println(4);
          }
        }  
  
 //SIDE TASK: Convert an Array to a List
 
      import java.util.*;
      public class Whatever {
        public static void main(String[] args) {
        
          String[] things = {"appl", "bob", "ham", "bob", "bacon"};
          List<String> list = Arrays.asList(things); //Convert array to list
          
        
        }
      }  
  


      import java.util.HashMap;
      public class HashMapProgram {
        public static void main(String[] args) {
        
        
          HashMap<Integer, String> HMap = new HashMap<Integer, String>();
          
          HMap.put(1, "one");
          HMap.put(2, "two");
          HMap.put(3, "three");
          HMap.put(4, "four");
          HMap.put(5, "five");
          
          System.out.println(HMap.size()); //Or (HMap.size<>)  ??
          
          //OUTPUT: 5
          
          System.out.println(HMap.get(2)); //W/ other syso commented out=> OUTPUT: two
        }
      }  
  
  
  //if do find key, set to REFERENCE DELETED
  //class: HashTableopen, algorithm for remove(Object key)
      private final Entry<K, V> DELETED = new Entry<K, V>(null, null);
      
      
