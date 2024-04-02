# Isomorphic-Strings
Given two strings s and t, determine if they are isomorphic.

Two strings s and t are isomorphic if the characters in s can be replaced to get t.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.

 

Example 1:

Input: s = "egg", t = "add"
Output: true




Initialization: Two hash maps (unordered_map in C++) mapS2T and mapT2S are initialized. These maps store the character mappings from s to t and from t to s, respectively.

Iteration: The algorithm iterates through each character in the strings s and t simultaneously, using an index i.

Mapping Validation:

For each character charS in s at index i, the algorithm checks if there is an existing mapping in mapS2T.
If there is an existing mapping, it checks if charS is correctly mapped to charT (the character in t at the same index). If not, the strings are not isomorphic, and the function returns false.
If there is no existing mapping for charS, it checks if charT is already mapped to a different character in mapT2S. If so, this means that charT is expected to map to two different characters, which violates the one-to-one mapping rule, and the function returns false.
Creating New Mappings: If the checks pass, it means the current characters charS and charT can be mapped to each other. The algorithm then adds these new mappings to mapS2T and mapT2S.

Completion: If the algorithm successfully iterates through all characters without returning false, it means that all character mappings are valid, and the strings are isomorphic. The function then returns true.

Complexity Analysis
Time Complexity: O(N), where N is the length of the strings. The algorithm iterates through each character of the strings exactly once. The operations within each iteration (accessing and updating the hash maps) are on average constant time, O(1), thanks to the nature of unordered_map in C++. Thus, the overall time complexity is linear in the size of the input strings.

Space Complexity: O(N), in the worst case. This is because, in the worst-case scenario, each character in the strings s and t could be different, requiring each character to be stored in both mapS2T and mapT2S. However, since the domain of characters (for example, ASCII characters) is limited, this space complexity could also be considered O(1) in practice if the character set is fixed and limited in size.
