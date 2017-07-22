# The Value of a Hack

## The Scrap Value of a Hacked PC, Revisited

![Hack Value](http://krebsonsecurity.com/wp-content/uploads/2012/10/HackedPC2012.png)

## The Value of a Hacked Email Account

![Email Hack Value](http://krebsonsecurity.com/wp-content/uploads/2013/06/HE-1.jpg)

Credit: Brian Krebs

# The Top 3 Things You Need To Stay Safe Online

![Stay Safe Online](https://user-images.githubusercontent.com/17448407/27270766-24f6b47c-54f3-11e7-878f-e8ac01e9f37a.png)

Credit: Comparing Expert and Non-Expert Security Practices - Usenix

# Security Bugs / Vulnerabilities - The Vulnerability Landscape

- An error written into software that creates a potential for a threat agent, such as a hacker, to exploit it

> Complexity is the enemy of security

## Known Bugs

- Use **patch** to fix the problems

## Unknown Bugs

- Also known as **0 Days**

# Hackers, crackers and cyber criminals

## White Hat Hackers

- Hacking for good

## Black Hat Hackers

- simply call them **cyber criminals**

### Script Kitties

- The mast majority of hackers who have little skills, all they can do is run a script that someone has written

# Malware

- All the encompassing term that refers to all of the programs that written with malicious intent

## Macro Virus

- Written in a macro language, such as VBS
- Since many applications allow macro programs embedded in the document
- The programs run automatically when that document is opened, e.g. Word, Excel, ...

## Stealth Virus

- Hides the modification it has made
- Trick antivirus software by intercepting its request to the operating system and providing false and bogus information

## Polymorphic Virus

- Produces varied operational copies of itself
- May have no parts that remain identical between infections, making it very difficult to detect directly using signatures and antivirus software

## Self-garbling Virus

- Attempt to hide from antivirus software by modifying its code so it does not match pre-defined antivirus software

## Bots & Zombies

- A collection of hacked devices under a command and control of a hacker

## Worms

- The viruses simply spread from one machine to another, to another, ...

## OS Rootkit

- Usually embedded into the kernel of the operating system, so it can hide its existence completely from the OS 

## Firmware Rootkit

- e.g. within your hard drive's firmware chip, even formatting your drive and reinstalling the operating system won't shift it

## Key Logger

- Log your keystrokes

## Trojan

- Simple programs that appear to be one thing, but they are actually malware

## Remote Access Tool (RAT)

- Allow intruders to access your system remotely
- Popular ones: Havex, AlienSpy, ComRat

## Ransomware

- Covertly encrypt all your personal files with a decryption key only the hacker knows
- Your options are to pay the ransom, attempt to crack the encryption (minor success), or lose the files

## Malvertisement

- Online advertisement that is infected with a virus malware
- Hackers place their own ads that contain scripts
- To get around security checks, these scripts point to other scripts, which download other scripts from another location

## Drive-by Attack

- Simply visiting a website that contains code to exploit your machine

## Spyware

- Main purpose is to gather information and send it back to the attacker
- Don't generally want to cause damage directly, but want to compromise your privacy and anonymity

## Adware

- Some people consider it to be a form of spyware
- Undesirable software that forces advertisement on you
- Hijacks your default search engines, display ads in the browser, sometimes takes you to places it wants you to go to instead of where you want to actually go to when you click on links, actively defends itself from being removed -> **Browser Hijacking**

## Scareware

- A type of social engineering attack to trick a person into believing a threat that isn't really real

## Potentially Unwanted Programs (PUPs)

- The antivirus companies and people that attempt to remove these things aren't quite sure whether you want them or not
- Often bundled in the software when you install
- Make sure when you install software, you go through the custom install and make sure you remove any of these PUPs

# What is Phishing, Vishing and SMShing?

## Phishing

- A type of attack that typically attempts to trick the victim into clicking on a link or executing malware in some way
- Typically carried out by sending fake emails or instant messages as well
- Direct victims to a fake site, often resembles a legitimate site
- A form of **social engineering** (An attack against human weaknesses)
- Also relies on the lack of defenses the web technologies inherently have
- Generally done on a mass number
- If a targeted and specific attack: **spear fishing**

### Techniques

- Link Manipulation
    * Subdomains & Misspelt
        * http://www.google.com.evil.org
        * http://evil.org/sa/google.com/support/
        * http://www.rnicrosoft.com
    * IDN homograph attack
        * http://www.g00gle.com
        * http://www.goog1e.com
    * Hidden URLs
        * [Click Here](http://www.google.com.evil.org)
        * [https://www.google.com](http://www.google.com.evil.org)
    > Can also be combined with Open Redirect, XSS, CSFR, etc.

 ## Vishing

 - Phone or voice phishing

 ## Smishing

 - SMS phishing or sending text messages

### Related Resourses

- [Live Phishing Links](https://www.openphish.com/)
    
- [Homograph attack using internationalized domain name](https://hethical.io/homograph-attack-using-internationalized-domain-name/)

# Spamming & Doxing

## Spam

- Unsolicited messages most often coming in email
- Also comes from instant messages, forums, social media, and even text messages now
- Mostly it's to advertise some sort of products
- Small operating cost

## Doxing

-  Dox: An abbreviation of Document
- To do research on an individual, or orginization or company to find personal and private information
- Often in order to cause embarrassment, discredit, harass, coerce by publicly releasing the information or the threat to publicly release it
- Can be achieved by simply searching on the internet and looking up public records

### Related Resourses

- [Spam Stats](https://www.av-test.org/en/statistics/spam/)
- [Spam Example](http://www.consumerfraudreporting.org/spamexamples/OnlinePharmacy-spamexample.php)