# Return-nonexist-alphabet
Request:
Change the input into lower case
If all the alphabet exist, return NULL
Or print out the missing letters


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
