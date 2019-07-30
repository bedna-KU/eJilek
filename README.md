# eJilek
Jan Jilek from http://www.abclinuxu.cz/lide/janjilek electronically (GPT-2)

#Import list of blogs from Jan Jilek
import abclinuxuapi
import urllib3
urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)

blog_count = len (abclinuxuapi.user.User("strider").get_blogposts ())

f = open ("user_out.txt","w+")

for i in range (blog_count - 1):
  output = abclinuxuapi.user.User ("strider").get_blogposts ()[i].url
  f.write(output)
  print (str(i +1) + "/" + str(blog_count) + " " + output)
f.close()
