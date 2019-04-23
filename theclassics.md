### Crypto 1
#### Points: 10
**Answer**: This was challenge that involved a simple morse code. The flag was converted to morse code and put as a challenge. To decode it you could look for an online Morse Code decoder and get the flag: `BCUNIVFLAG{SHIP_NEEDS_HELP_76098029}`

#

### Ports 1
#### Points: 10
**Question**: What port does Remote Desktop Protocol run on? Answer format: bcunivflag{PORT_NUMBER}

**Answer**: You could either Google this or know it by memory. RDP runs on port `3389`.

#

### Cracking 1
#### Points: 10
**Question**: Crack this password: 5f4dcc3b5aa765d61d8327deb882cf99 Format: bcunivflag{CRACKED_PASSWORD}

**Answer**: The hash used to encrypt this password is `md5`. Hash cracking was not needed for this one. A simple Google search of the hash will give you the password which was `password`.

#

### Crypto 2
#### Points: 25
**Question**: I got 99 problem but 13 ain't one: `ophavisynt{FUVSG_GUR_A_0894731}`

**Answer**: This used a substitution cipher commonly known as Caesar Cipher. Caesar Cipher has different shifts that you can use to encode your message. As the question suggested it used the shift of 13. Decoding it with 13 as shift gave the flag: `bcunivflag{shift_the_n_0894731}`

#

### Hidden from plainsight
#### Points: 25
**Question**: Find the flag in 74.207.242.159:8080

**Answer**: This was a web service running on port 8080. You could find the flag two ways: 1) Guess the flag filename which was `flag.txt` or 2) Go to `/robots.txt` and find the file name there. Robots.txt is a text file found in websites with a rule that most crawlers follow. These rule dictate what the crawler can crawl and scan (`Allow`) and what it cannot scan (`Disallow`)

#

### Ports 2
#### Points: 50
**Question**: What port is running a web app in 173.255.218.99 Flag format: bcunivflag{PORT_NUMBER}

**Answer**: This was a way for us to help people who have never hacked know about a useful hacking tool. This tool is called `nmap` and is used to find open ports and services on a server. By running a nmap script like `nmap -p- 173.255.218.99`, you will find multiple ports open. One of them is `3000` which is running a web service (Rocketchat).

#

### Programming 1
#### Points: 50
**Question**: We found a weird file. Can you get the flag from this?

**Answer**: The file attached was a compiled python script (`.pyc` file). Once you decompile it, you could see the source code. This however did not give you the code. This script when ran would ask you to guess the flag and then tell you if your guess was correct or not. The value of the flag is stored in the array in which the integers value are the `ord` of each character of the flag xored to 300. To get the flag you go through each value and xor them to 300 again (vals[i]^300) and then put that val in `chr()` function like: chr(vals[i]^300) to get the correct alphabet. The flag was: `bcunivflag{rev_is_fun}`

#

### Valid Request
#### Points: 50
**Question**: Ask for the right thing and you might just get the flag: http://173.230.148.251/

**Answer**: This required messing with HTTP request headers. When you send a request, you tell the server what type of response you want. This is done through `Accept` header. By default, most requests will have `text/html`. In order to get the flag on this one, you needed to change that to `application/json`. This teaches a valuable lesson that sometimes a server will react differently to a request of different response type. Flag was: `bcunivflag{playing_with_content_9091874671}`

#

### Cracking 2
#### Points: 100
**Question**: We found some password format from a recent breach. It has the format of `BCUNI-XXXX-XXXX` where the Xs are alphabets. Crack this hash: `ede0e3cc80495c1e54d677810bc08567`. Flag format: bcuniflag{CRACKED_PASS}

**Answer**: Now this one was a little challenging. It was not a common password and all you were given was a md5 hash and the password format. There are multiple ways this can be solved: 1) You could write a script that will create md5 hash by filling the Xs with alphabets and iterating through it but it could take a long time. You could also use a password cracking tools in Kali and specify the password format. The password was: `BCUNI-HACKER-POWER` (case sensitive).

#

### Hacker Search
#### Points: 500
**Question**: What is the IP of Brycon Inc (check attached image) Format: bcunivflag{IP_ADDR}

**Answer**: In this case, you were provided an image of a server that was running an open unauth VNC. This was taken from Shodan.io hence the name Hacker Search for the challenge. We only had 2 solvers for this who also won 1st and 2nd place in the competition. 

First, you want to look for what ports do VNC run on. Once you have them down, go to shodan.io and look up that specific port `ports:{PORT}`. Then go through the images recorded by Shodan and see if you can find the Byrcon one. The IP will be there once you click on the image. `173.122.56.194`
