# Return-nonexist-alphabet
Request:
Change the input into lower case
If all the alphabet exist, return NULL
Or print out the missing letters

Tips:
1. "".join(..) = list to string
2. sorted(..) = order
3. set(..) = remove repetitive objects
4. s.lower() = to lower case
5. s.strip() = remove whitespace



1） Self：
            import string

            def panAnagram(s):
                l = "".join(sorted(set(s.lower()))).strip()
                # build lower case, sorted alphabet from input
                alphabet = string.ascii_lowercase
                # build alphabet
                dict = {}
                for i in range(len(alphabet)):
                    key = alphabet[i]
                    if key not in dict:
                        dict[key] = i
                # print(dict) - build a dict
                if len(l) == len(alphabet):
                    return NULL
                for j in range(len(l)):
                    if l[j] in dict:
                        del dict[l[j]]
                return list(dict.keys())

            s = "A slow yellow fox crawls under the proactive dog"
            print(panAnagram(s)) 
     
     
2）Simplify：

            <no need to eliminate space and sort, just check whether the answer is in target and then delete/ replace>

            def panAnagram(s):
                alpha = "abcdefghijklmnopqrstuvwxyz"
                for char in s:
                    if char.lower() in alpha:
                        alpha = alpha.replace(char.lower(), "")
                        # mutate alpha, so use =
                        # for str, use s.replace("", "")
                return alpha

            s = "A slow yellow fox crawls under the proactive dog"
            print(panAnagram(s)) 


3）Simplify:
   
            def panAnagram(s):
                dict = {'a': 0, 'b': 1, 'c': 2, 'd': 3, 'e': 4, 'f': 5, 'g': 6, 'h': 7, 'i': 8, 'j': 9, 'k': 10, 'l': 11, 'm': 12, 'n': 13, 'o': 14, 'p': 15, 'q': 16, 'r': 17, 's': 18, 't': 19, 'u': 20, 'v': 21, 'w': 22, 'x': 23, 'y': 24, 'z': 25}
                for char in s.lower():
                    if char in dict:
                        del dict[char]
                return list(dict.keys())    

            s = "A slow yellow fox crawls under the proactive dog"
            print(panAnagram(s)) 
