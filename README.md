# msgfreqcount
Message Frequency Count Assignment
Using the DSU pattern, write a program that reads through the mail box data and when you find a line that starts with “From”, extract the address information from the line. Count the number of messages from each person by using a dictionary. After all of the data has been read, print (i.e., print) a message to the user stating that the person with the highest number of sent messages is <email_address>, along with the number of sent messages associated with that email address (e.g., “with n messages”).

#

dict_addresses = dict()
lst = list()

fname = input('Please enter the file name:')
try: 
        fhand = open(fname)
except:
        print('File name does not exist:', fname)
        exit()

for line in fhand:
    words = line.split()
    if len(words) < 2 or words[0] != 'From':
        continue
    else:
        if words[1] not in dict_addresses:
            dict_addresses[words[1]] = 1
        else:
            dict_addresses[words[1]] += 1

for key, val in list(dict_addresses.items()):
    lst.append((val, key))

lst.sort(reverse=True)
for key, val in lst[:1]:

   max_lst = (val, key)
(e1, e2) = max_lst

print(('The email address with the most sent messages was'), (e1), ('with'), (e2))
