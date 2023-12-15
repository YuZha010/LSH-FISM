# LSH-FISM
This is a duplication detection algorithm which uses Locally sensitive hashing (LSH) with a novel method called the Feature intersection similarity method (FISM). 
- First, we start by pre processing the titles of the data
- Then we apply the LSH on the splitted model words of the data
- We only compare those products that hash to the same bucket
- Then, we apply FISM on those.

Structure code:
- We group certain functions in the same block if they are small. Larger blocks are defined in their own blocks. All blocks until the final one are defitions of functions. The last one is the execution file.


How to use the code?
- Run every function, and you can then execute the main file which is the last block.
- The bootstrap count can be changed here: bootstraps = bootstrap_sampling(fullMatrix, num_bootstraps=20), which is in the final block.
- To tune FISM, we recommend to go the the FISM function, and modify: normalized_levenshtein.distance(alpha1, alpha2) < 1.1, and thus change 1.1 to a value between [0,1].
- To tune t_i, modify: if (len(intersectMW) < 5) in the FISM function. Hence, change 5. This means that if the intersect of the modelwords is less then 5, we don't consider them as duplicates. 
