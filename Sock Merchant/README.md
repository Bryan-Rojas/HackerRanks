```Java

    // Time Complexity: O(n)
    static int sockMerchant(int n, int[] ar) {
        //HashSet to avoid duplicates and better Time Complexity
        //Integer pairs keeps track of amount of pairs we have.
        Set<Integer> socks = new HashSet<Integer>();
        int pairs = 0;

        //Iterates through the size of the input array.
        //Checks if HashSet does NOT contains ar[i], if true, adds it to set.
        //Else, assumes it does contain it and increments pairs and removes it from set.
        for(int i = 0; i < n; i++){
            if(!socks.contains(ar[i])){
                socks.add(ar[i]);
            }
            else{
                pairs++;
                socks.remove(ar[i]);
            }
        }

        //Returns amount of pairs.
        return pairs;
    }

```