```Java
    // Time Complexity: O(n)
    // Had to look at the solution for this answer.
    // Will comment later. Happy Thanksgiving! - Bryan 11/22/2018 
    /*
               .--.
              /} p \             /}
             `~)-) /           /` }
              ( / /          /`}.' }
               / / .-'""-.  / ' }-'}
              / (.'       \/ '.'}_.}
             |            `}   .}._}
             |     .-=-';   } ' }_.}
             \    `.-=-;'  } '.}.-}
              '.   -=-'    ;,}._.}
                `-,_  __.'` '-._}
              jgs   `|||
                   .=='=,

    */
    static long repeatedString(String s, long n) {
        if(!s.contains("a")){
            return 0;
        }
        
        long count = 0;
        long mod = s.length() > 0 ? (n % s.length()) : 0;
        long remainder = 0;
        boolean strLonger = false;

        for(int i = 0; i < s.length(); i++){
            if(i >= n){
                strLonger = true;
                break;
            }
            if(s.charAt(i) == 'a'){
                if(mod > i){
                    remainder++;
                }
                count++;
            }
        }

        if(!strLonger){
            count = count * Math.max(n/ s.length(), 1) + remainder;
        }

        return count;
    }
```