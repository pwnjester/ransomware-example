# toy-ransomware
Have you always looked at malware that encrypts files surprised, saying to yourself "Oh man, how the hell did they even craft this?". Well when I was younger, I truly did wonder! Ransomware samples were exactly what brought me into the malware researching part of computers... 

Today we're going to analyze exactly how ransomware attacks work: literally step-by-step! ...and then create our own, exclusively for entertainment and education usage. **This is an actual real-world ransomware coded in WinAPI C++ with the help of the Cryptography API made to encrypt a whole Windows installation.**

![Message](https://camo.githubusercontent.com/44aa733b02bd6ae937e44a9afa316e9c278195c5afe604b64985f129bc8109cf/68747470733a2f2f7261772e6d616c776172657061642e636f6d2f6d656469612f6769742f746f792d72616e736f6d776172652f706f7075702e706e67)
![Encrypted files](https://camo.githubusercontent.com/144c6c05a6dbcac1ee302d9242cc62431d7c0717304a5903b2fa56abf8240afb/68747470733a2f2f7261772e6d616c776172657061642e636f6d2f6d656469612f6769742f746f792d72616e736f6d776172652f66696c65732e706e67)

## Warning
### The code in this repository - paired with an actual server - is as destructive as it gets. Files WILL be encrypted and I'm not responsible for any damage made by this source code. This repository is made to educate people on ransomware attacks and help them find ways in order to prevent them. Malware should never be used for any other purpose!

## Stack
* [Windows API](https://en.wikipedia.org/wiki/Windows_API)
* [C++](https://en.wikipedia.org/wiki/C%2B%2B)
* [AES-128](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)

## Sources/Helpful resources
* [MSDN](https://learn.microsoft.com/en-us/windows/win32/apiindex/windows-api-list)
* [hasherezade's gist](https://gist.github.com/hasherezade/2860d94910c5c5fb776edadf57f0bef6)

## How can I use it
First ask yourself "why do I want to use it?". My answer will depend on that...
* **"I want to use it to prank my friends":** It will get picked up by their antivirus along with being completely unethical and illegal.
* **"I want to start a ransomware attack":** Yeah good luck with that buddy.
* **"I want to educate myself on the attacks":** Feel free to examine the source code without running any executable. To be extra safe don't even clone the repository, just use GitHub's editor.
* **"I am a professional and want to make a presentation for my students/company in a controlled environment":** To use the code I provided, you have to pair it with the correct server. In order to do that, you'll have to edit `GetEncryptionKey.cpp` and change the host and/or port. Your webserver should be able to respond to a simple `POST` request to `/victim` with `{ success: true, privateKey: "xyz" }` for encrypting and when re-sending it has to respond with `{ success: false }` to signal decryption mode.
