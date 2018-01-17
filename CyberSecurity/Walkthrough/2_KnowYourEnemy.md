# The Value of a Hack

## The Scrap Value of a Hacked PC, Revisited

![Hack Value](https://krebsonsecurity.com/wp-content/uploads/2012/10/HackedPC2012.png)

## The Value of a Hacked Email Account

![Email Hack Value](https://krebsonsecurity.com/wp-content/uploads/2013/06/HE-1.jpg)

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

- Simply call them **cyber criminals**

### Script Kitties

- The most majority of hackers who have little skills, all they can do is run a script that someone has written

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

# Social Engineering - Scams, cons, tricks and fraud

- A term used in the Security Industry to refer to attacks that center on weakneses in the human being

- [Top Ten Scams](http://www.consumerfraudreporting.org/current_top_10_scam_list.php)

# Darknets, Dark Markets and Exploit kits

- Also known as Darkweb, is a general term for any encrypted overlay network that you can only access with specific types of software or authorizations, or protocols, or ports
- The conventional internet like Facebook, Google would be called the **Clearnet** or **suface web** as a reciprocal term
- The main differense being you need to use specific encryption to access it
- Generally cannot be searched with Google but Tor might indexed it
- Used by governments, military, companies and anyone who needs privacy, plus criminals
- A tool to maintain anonymity and is in some sense, to maintain security
    - eg. Retroshare, Tor, I2P Anonymous, Gnunet framework, Freenet project
- Through the darknet, you can access dark markets and hack forums
    - [Darknet Market Comparison Chart](https://www.deepdotweb.com/dark-net-market-comparison-chart/)
    - [the Hidden Wiki - H/P/A/W/V/C](http://zqktlwi4fecvo6ri.onion/wiki/index.php/Main_Page#H.2FP.2FA.2FW.2FV.2FC) (Can only accessed with Tor)
    - [0day Forum](http://qzbkwswfv5k2oj5d.onion/)
- The number of exploit kits are growing exponentially, script kiddles can buy them on dark markets, making the average intruder knowledge is now low

# Governments, spies and secret stuff

- Active mass surveillance is happening accross many countries
- An agreement exists between these countries to co-operatively collect, analyze, and share intelligense
    - 5 Eyes
        1. the UK
        2. the US
        3. Australia
        4. Canada
        5. New Zealand
    - 9 Eyes
        
        6. Denmark
        7. France
        8. Netherlands
        9. Norway
    - 14 Eyes

        10. Belgium
        11. Germany
        12. Italy
        13. Spain
        14. Sweden
- Carnivore, ECHELON and NarusInsight, used to intercept and analyze immense amount of data that traverse the internet and telephone systems
- [Utah Data Center](https://en.wikipedia.org/wiki/Utah_Data_Center)
- [ANT catologue](https://nsa.gov1.info/dni/nsa-ant-catalog/ ), an elite document of the NSA's hacking and spying tool set circa around 2008
- [NSA Playset](http://www.nsaplayset.org/), Inspired by the NSA ANT catalog
- [NSA codenames](https://cryptome.org/2014/01/nsa-codenames.htm)
- Further listening: [Through a PRISM, Darkly Everything we know about NSA spying 30c3](https://www.youtube.com/watch?v=e4woRYs0mM4)

# Regulating encryption, mandating insecurity & legalizing spying

- [UK data communications bill](https://en.wikipedia.org/wiki/Draft_Communications_Data_Bill)
- [WhatsApp was Banned for 48 Hours in Brazil](https://www.pcmag.com/article2/0,2817,2496766,00.asp)
- [How India Regulates Encryption](https://cis-india.org/internet-governance/blog/how-india-regulates-encryption)
- [Kazakhstan's New Encryption Law Could Be a Preview of U.S. Policy](https://www.theatlantic.com/technology/archive/2015/12/kazakhstans-new-encryption-law-could-be-a-preview-of-us-policy/419250/)
- [Matt Blaze Speaking to a US congressional committee](https://youtu.be/zk78_zmH4QI?t=1870)
- [Report - Keys Under Doormats: Mandating insecurity by requiring government access to all data and communication](https://dspace.mit.edu/bitstream/handle/1721.1/97690/MIT-CSAIL-TR-2015-026.pdf?sequence=8)
- [The Case against Regulating Encryption Technology](https://people.csail.mit.edu/rivest/pubs/Riv98e.pdf)
- [A Worldwide Survey of Encryption Products - pdf](https://www.schneier.com/academic/paperfiles/worldwide-survey-of-encryption-products.pdf)
- [A Worldwide Survey of Encryption Products - xls](https://www.schneier.com/academic/paperfiles/worldwide-encryption-product-survey-data.xls)
- [NSA Admits It Collects Too MUCH Info to Stop Terror Attacks](http://www.washingtonsblog.com/2015/05/nsa-admits-it-collects-too-much-info-to-stop-terror-attacks.html)
- [US HOUSE OF REPRESENTATIVES
COMMITTEE ON GOVERNMENT OVERSIGHT AND REFORM
INFORMATION TECHNOLOGY SUBCOMMITTEE
ENCRYPTION TECHNOLOGY AND POSSIBLE US POLICY RESPONSES](http://www.crypto.com/papers/governmentreform-blaze2015.pdf)

# Trust & Backdoors

- One approach to avoid bugs is to create non-complex systems. But this is infeasible
- Another approach is to use what is called [Formal methods](https://en.wikipedia.org/wiki/Formal_methods), through testing and proving properties of that system (still too time consuming and cost prohibitive for most systems)
- We need to reduce attack surface, create isolation and compartmentalization and build layers of defense
- If something is Closed source, the only way to find backdoors is through a process called **Reverse engineering**

## How do we mitigate the risks from Backdoors?
- [reproducible builds](https://reproducible-builds.org/) --> Recommended OS: [Debian](https://www.debian.org/intro/why_debian)
- [deterministic builds](https://blog.torproject.org/blog/deterministic-builds-part-one-cyberwar-and-global-compromise)

### Related resourses
- [Proprietary Back Doors](https://en.wikipedia.org/wiki/Formal_methods) (take these with a pinch of salt)
- [Apple Removes Malware-Infected Apps From the App Store](https://variety.com/2015/digital/news/apple-removes-malware-infected-apps-from-the-app-store-1201598650/)
- [Here’s Why Apple Is Going To War Over FBI ‘Backdoor’ Order](http://fortune.com/2016/02/17/apple-backdoor-order/)
- [On the Juniper backdoor](https://blog.cryptographyengineering.com/2015/12/22/on-juniper-backdoor/)
- [Video on how to build your own software reproducibly](https://media.ccc.de/v/camp2015-6657-how_to_make_your_software_build_reproducibly)

# Censorship

- [Google Censorship Ruling in Canada Has Worldwide Implications](https://searchenginewatch.com/sew/news/2351154/google-censorship-ruling-in-canada-has-worldwide-implications)
- [Search removals under European privacy law
](https://transparencyreport.google.com/eu-privacy/overview)
- [Government requests to remove content](https://transparencyreport.google.com/government-removals/overview)

# Security News and Alerts – Stay Informed