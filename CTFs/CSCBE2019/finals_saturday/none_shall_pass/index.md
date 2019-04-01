# None Shall Pass!!! (Forensics - 150 pts)

### [~$ cd ..](../)

> Your job is to identify how to open the file, bypass it’s security control(s), and find the flag. Knowledge of security is not mandatory, but having some knowledge about programming concepts or languages will help. If you have a love for chitchat or lighthouses, you will have an extra edge.


For this challenge we received two files. The first one was [chitchat.image](chitchat.image) and the second one was [chitchat.changes](chitchat.changes).

the first thing we did was to make a `binwalk` on the image file, we then made a `cat` of it and finally executed the `strings` command on it before trying to mount it. 

we knew from the statement that the flag format of this challenge was CSC<STRINGS>

> ```sh
> strings chitchat.image | grep "CSC"
>	CSCBALLOON216767349
>```