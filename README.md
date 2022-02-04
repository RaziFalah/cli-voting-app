# cli-voting-app
basic voting app back end written, without GUI

<h1>About</h1>
Voting app made in python
imports: sleep from time, glob form glob, os
GUI: none
Console app: True

<h1>Tech view</h1>

Master function
```
def process(counter):
 while 1 != 0:
  ider =  int(input("Enter your id number: "))
  if ider in can_vote:
      name = can_vote[ider]["name"]
      print(f"Hello {name}")
      i = 0
      while 1 != i:
        action = input("press 1 and enter to View candidates menu/ press 2 and enter to vote for a candidate / press 3 to read session / press 4 to end session / press 5 to view votes: ")
        if action == "1":
            _1 = candidates[0::]
            _2 = candidate_ans[0::]
            print("candidates : " + str(_1))
            print("Vote ids: " + str(_2))
        elif action == "2":
            ask_4 = int(input("Who are you voting for insert candidate vote id: "))
            cand_name = candidates[ask_4]
            if ider in can_vote:
              f = open(f"{vote_name}_vote.enc", "a")
              f.write(f"{counter}): {name} voted for {cand_name}\n==========\n")
              f.close()
              counter = counter + 1
              voted.append(ider)
              can_vote.pop(ider)
              print(f"Successfuly voted for {cand_name}")
              i = i + 1
              print("preparing for the next voter...")
              sleep(1)
              os.system("clear")
              process(counter)
            else:
                print("You have alrady voted!")
        elif action == "3":
            f = open(f"{vote_name}_vote.enc", "r")
            print(f.read())
        elif action == "4":
            print("ending session...")
            sleep(2)
            print("Bye")
            exit()
        elif action == "5":
            #search_word_count = input('Enter the id of the candidate: ')
            #file = open(f"{vote_name}_vote.enc", "r")
            #read_data = file.read()
            #word_count = read_data.lower().count(search_word_count)
            #searchofr = int(search_word_count)
            #candaa_name = candidates[searchofr]
            #candaa_namea = str(candaa_name)
            #print(f"The total votes for votes for {candaa_namea} is: {word_count}.")
            print("Program error: i will fix it soon!")
        else:
            print("Unkown action!")
  else:
      if ider in voted:
          print("You have alrady voted!")
      else:
          print("We couldn't find this id at our end!")
      
```

Prestart manager

```
from glob import glob
import os
from time import sleep
print("Hello, in order to start the game you will need to ajust some settings first: ")
count_candidates = input("How many candidate will there be? ")
i = 0
global candidates
candidates = []
global candidate_ans
candidate_ans = []
global candidates_votes
candidates_votes = []
while int(count_candidates) > i:
    ask = input(f"Name of candidate {i}: ")
    candidates.append(ask)
    candidate_ans.append(i)
    ii = 0
    candidates_votes.append(ii)
    i = i + 1

vote_name = input("What is the session name: ")
```
