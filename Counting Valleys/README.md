```Java

    // Time Complexity: O(n)
    static int countingValleys(int n, String s) {
        //Variables to keep track of current level and valleys
        int valleys = 0;
        int currentLevel = 0;

        //We iterate through the size of String s and save that
        //character as currentChar. Then, we check if it's 'U' then
        //we increase currentLevel by 1. Else, we decrease it by 1.
        //After we've modified the currentLevel we're going to check
        //if valleys needs to be incremented by 1. We know that a valley is
        //counted when our currentLevel is zero and we've come up.
        //So, we check if currentLevel == 0 and if currentChar == 'U'.
        for(int i = 0; i < n; i++){
            char currentChar = s.charAt(i);
            if(currentChar == 'U'){
                currentLevel++;
            }
            if(currentChar == 'D'){
                currentLevel--;
            }

            if(currentLevel == 0 && currentChar == 'U'){
                valleys++;
            }
        }

        //Finally, return our total valleys.
        return valleys;
    }

```