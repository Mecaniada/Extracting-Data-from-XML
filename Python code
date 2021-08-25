import urllib.request, urllib.error, urllib.parse
from bs4 import BeautifulSoup
import xml.etree.ElementTree as ET

url = input('Enter url: ')
if len(url) < 1:
    url = 'http://py4e-data.dr-chuck.net/comments_1333855.xml'
XML = urllib.request.urlopen(url).read()

print(XML.decode())

tree = ET.fromstring(XML)
comments_list = tree.findall('comments/comment')
counts = tree.findall('.//count')
num_list = list()
Sum = 0
Sum_list = 0
for number in counts:
    Sum += int(number.text)

    #Reminder ! If I put the following code:
    # num = float(number) or num = int(number) it won't work cause I must declare the type of "number" extracted from XML file.
    #That's why I have to put int(number.text) or float(number.text)

    #Second option is by making a list and I must do the same as mentioned in the comments above

    num_list.append(int(number.text))
print(num_list)
for numbers in num_list:
    Sum_list += numbers
print('The sum from list:', Sum_list)

print('Retrieved', len(XML),'characters')
print('Count:', len(counts))
print('Sum:', Sum)
