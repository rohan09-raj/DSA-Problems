### Question
https://leetcode.com/problems/design-hashmap

### Solution
**Optimised One**
```JAVA
import java.util.*;

class MyHashMap {
    int[] map;

    public MyHashMap() {
        map = new int[1000006];
        Arrays.fill(map, -1);
    }
    
    public void put(int key, int value) {
        map[key] = value;
    }
    
    public int get(int key) {
        return map[key];
    }
    
    public void remove(int key) {
        map[key] = -1;
    }
}
```
**Not very optimised**
```JAVA
class MyHashMap {
    List<int[]> mhp;

    public MyHashMap() {
        mhp = new ArrayList<>();
    }
    
    public void put(int key, int value) {
        for(int i=0; i<mhp.size(); i++) {      
            if(mhp.get(i)[0] == key) {
                mhp.get(i)[1] = value;
                return;
            }
        }
        
        mhp.add(new int[]{key, value});
    }
    
    public int get(int key) {
        for(int i=0; i<mhp.size(); i++) {      
            if(mhp.get(i)[0] == key) {
                return mhp.get(i)[1];
            }
        }
            
        return -1;
    }
    
    public void remove(int key) {
        for(int i=0; i<mhp.size(); i++) {      
            if(mhp.get(i)[0] == key) {
                mhp.remove(i);
            }
        }
    }
}
```
