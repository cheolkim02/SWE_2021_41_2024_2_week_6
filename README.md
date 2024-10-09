# SWE_2021_41_2024_2_week_6
--------------------
## Week 4 Assignment
__Task: Happy Numer__
* Starting with any positive integer, replace the number by the sum of the squares of its digits.
+ Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
- Those numbers for which this process ends in 1 are happy.

> ### Repository to my week 4 assignment
> > https://github.com/cheolkim02/SWE_2021_41_2024_2_week_4
My code:
```python
def isHappy(n):

  a = []
  found = False
  sum=int(0)
  while(True) :
    sum=0

    for i in str(n) :
      sum += (n%10)**2
      n=n//10

    for i in a :
      if(sum==i) :
        found = True

    if(sum==1) :
      print("True")
      return True
    elif(found) :
      print("False")
      return False
    else :
      n = sum
      a.append(sum)
```
__Explanation__
1. Iterate through each digit of n, and save the sum of each digit's sqaure at sum.
2. Append the sum to list a, set n=sum, and set sum=0. This allows us to now start step 1 with the new value.
3. Loop steps 1 and 2, until the same number of sum is found in list a, in which case function returns False.
4. If sum becomes 1 before it is found in list a, n is a happy number, and function returns True.
-------------------------
## Week 5 Assignment
__Task: Using Docker, set up environment for a container including:__
1. Linux OS
2. Git installed
3. Python3 installed
4. bind mount

> docker exec ossp-container cat /etc/os-release
* docker exec: allows to run a command inside a running container, and my container's name is <ossp-container>
* cat: outputs contents of the following directory (etc/os-release), where details about the OS is stored.
* my output shows the version, ID, URLs, LOGO, etc. about the Ubuntu that I'm using

> docker exec ossp-container git --version
* git --version: outputs the downloaded git version
* my output: git version 2.43.0

> docker exec ossp-container python3 --version
* python3 --version: outputs the downloaded python3 version
* my output: Python 3.12.3

> docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
* inspect --format="{{ .HostConfig.Binds }}" ossp-container: outputs mount directory
* my output: [./ossp_host_dir:/mnt/ossp_container_dir]

