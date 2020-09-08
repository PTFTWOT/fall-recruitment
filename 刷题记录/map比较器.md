

```java
package A_9_6tencent;

import java.util.*;

/**
 * 字符串次数比较输出
 */
public class Main3 {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNext()){
            String[] s = sc.nextLine().split(" ");
            int n = Integer.parseInt(s[0]);
            int k = Integer.parseInt(s[1]);
            Map<String, Integer> map = new TreeMap<>();
            for(int i = 0; i < n; i++){
                String t = sc.nextLine();
                map.put(t, map.getOrDefault(t, 0) + 1);
            }
            List<Map.Entry<String, Integer>> list = new ArrayList<Map.Entry<String, Integer>>(map.entrySet());
            Collections.sort(list, new Comparator<Map.Entry<String, Integer>>() {
                @Override
                public int compare(Map.Entry<String, Integer> o1, Map.Entry<String, Integer> o2) {
                    return o2.getValue().compareTo(o1.getValue());
                }
            });
            int i = 0;
            for(Map.Entry<String, Integer> m : list){
                i++;
                System.out.println(m.getKey() + " " + m.getValue());
                if(i == k) break;
            }
            Collections.sort(list, new Comparator<Map.Entry<String, Integer>>() {
                @Override
                public int compare(Map.Entry<String, Integer> o1, Map.Entry<String, Integer> o2) {
                    return o1.getValue().compareTo(o2.getValue());
                }
            });
            i = 0;
            for(Map.Entry<String, Integer> m : list){
                i++;
                System.out.println(m.getKey() + " " + m.getValue());
                if(i == k) break;
            }
        }
    }
}
```

