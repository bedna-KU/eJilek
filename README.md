# eJilek
Jan Jilek from http://www.abclinuxu.cz/lide/janjilek electronically (GPT-2)

## Import list of blogs from Jan Jilek

```
import abclinuxuapi
import urllib3
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)

user_name = "strider"

blog_count = len (abclinuxuapi.User(user_name).get_blogposts ())

f = open ("user_blogs.txt","w+")
fb = open ("user_all_text.txt","w+")

for i in range (blog_count - 1):
  print ("Read path to blog")
  blog_url = abclinuxuapi.User (user_name).get_blogposts ()[i].url
  f.write (blog_url + "\n")
  print (str(i +1) + "/" + str (blog_count) + " " + blog_url)
  print ("Read blog")
  text = abclinuxuapi.Blogpost (blog_url, lazy=False).text
  print ("Write blog")
  fb.write (text + "\n")
  fb.write ("<|endoftext|>\n")
f.close ()
fb.close ()
```
