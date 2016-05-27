# Assignment-10.2
Chapter 10 Tuples :)
#Write a program to read through the mbox-short.txt and figure out the distribution by hour of the day for each of the messages. You can pull the hour out from the 'From ' line by finding the time and then splitting the string a second time using a colon.
From stephen.marquard@uct.ac.za Sat Jan  5 09:14:16 2008
Once you have accumulated the counts for each hour, print out the counts, sorted by hour as shown below.

name = raw_input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"
handle = open(name)
text = handle.read()
words = list()
for line in handle:
    if not line.startswith('From '):
        continue
    line = line.rstrip()
    line = line.split()
    time = line[5]
    
    hour = time.split(':')
    words.append(hour[0])
counts = dict()
for word in words:
    counts[word]=counts.get(word,0)+1

for word, count in sorted(counts.items()):
    print word,count
    
