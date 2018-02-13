- [OWASP Internet of Things Project](https://www.owasp.org/index.php/OWASP_Internet_of_Things_Project)
- [IoTSF](https://www.iotsecurityfoundation.org/)

## 物聯網設備是發動 DDoS 攻擊的完美平臺？為何如此？

Credit: https://www.ithome.com.tw/guest-post/112833

物聯網設備的特性：
- 常保可連結性：
    - 物聯網設備與互聯網的連結幾乎是 7/24 不中斷
- 具有不錯的運算能力：
    - 為了加速處理能力以提升服務品質下，有越來越多的物聯網設備，都配置了不錯的系統規格
- 安全不設防的設計：
    - 由於物聯網設備的多樣化與複雜性，因此，幾乎都沒有內載、安裝安全軟體。當然，沒有適合於物聯網型態的資安軟體，是因素之一，而另一層因素是為了避免影響效能。
- 嵌入式系統：
    - 物聯網設備主要採用 Linux 或 Windows 嵌入式系統設計，但嵌入式系統宛如複製人大軍，雖然方便物聯網設備大量生產或改造，但是被發現可利用的弱點時，也將會造成通盤崩壞的局面。

![The Current IoT Security Problem](https://user-images.githubusercontent.com/17448407/35478317-c463acb0-0414-11e8-9d41-e19e128c0a52.jpg)
Credit: RSA Conference 2015

# Jenx

New JenX IoT DDoS Botnet Offered Part of Gaming Server Rental Scheme 

https://t.co/QP4KYWVNoI

# Mirai

Credit: https://blog.cloudflare.com/inside-mirai-the-infamous-iot-botnet-a-retrospective-analysis/

- the infamous Internet-of-Things botnet that took down major websites via massive distributed denial-of-service using hundreds of thousands of compromised Internet-Of-Things devices

![Mirai Timeline](https://user-images.githubusercontent.com/17448407/35479353-28369106-0430-11e8-8619-b55d3d2254d1.png)
Credit: USENIX Security 2017 - Understanding the Mirai Botnet

## How Mirai works?

- A self-propagating worm
    - a malicious program that replicates itself by finding, attacking and infecting vulnerable IoT devices
- A botnet
    - the infected devices are controlled via a central set of command and control (C&C) servers. These servers tell the infected devices which sites to attack next

### Replication Module

- Responsible for growing the botnet size by enslaving as many vulnerable IoT devices as possible

1. (randomly) Scanning the entire Internet for viable targets and attacking
2. To compromise devices, the initial version of Mirai relied exclusively on a fixed set of 64 <b>well-known default login/password</b> combinations commonly used by IoT devices
3. Once it compromises a vulnerable device, the module reports it to the C&C servers so it can be infected with the latest Mirai payload

### Attack Module

- Responsible for carrying out DDoS attacks against the targets specified by the C&C servers
- Implements most of the code DDoS techniques such as
    - HTTP flooding
    - UDP flooding
    - TCP flooding
- This wide range of methods allowed Mirai to perform
    - volumetric attacks
    - application-layer attacks
    - TCP state-exhaustion attacks

## Countermeasures

- Eliminate default credentials: 
    - This will prevent hackers from constructing a credential master list that allows them to compromise a myriad of devices
- Make auto-patching mandatory:
    - IoT devices are meant to be “set and forget,” which makes manual patching unlikely. Having them auto-patch is the only reasonable option to ensure that no widespread vulnerability can be exploited to takedown a large chunk of the Internet.
- Implement rate limiting:
    - Enforcing login rate limiting to prevent brute-force attack is a good way to mitigate the tendency of people to use weak passwords. Another alternative would be using a captcha


## Annotate

- HTTP flooding
    - An application layer denial of service attack targeting websites and online services
    - main modes of the attack
        - HTTP GET flood
        - HTTP POST flood
    - HTTP GET flood
        - The attacker attempts to receive a large amount of data (images and scripts) using GET request from the server
        - By radomizing parameters and the HTTP GET request, attackers managed to bypass the CDN service, and to request the webpage directly from the backend servers
    - HTTP POST flood
        - The attacker is looking for forms in the target website
        - By using the form parameters
- TCP flooding
    - https://www.cisco.com/c/en/us/about/press/internet-protocol-journal/back-issues/table-contents-34/syn-flooding-attacks.html
    - https://security.stackexchange.com/questions/15368/syn-flooding-issue/15377