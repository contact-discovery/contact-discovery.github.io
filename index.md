This website is also available [**in German**](https://contact-discovery.github.io/de/).

## News

### Second Prize in German IT-Security Award 2020

[Christian Weinert](https://encrypto.de/weinert), [Thomas Schneider](https://encrypto.de/schneider), [Matthias Senker](https://www.encrypto.cs.tu-darmstadt.de/home_page/news_feed/news_details_166274.en.jsp), [Daniel Kales](https://daniel.kales.io/) and [Christian Rechberger](https://www.iaik.tugraz.at/person/christian-rechberger/) won the second prize in the [8. German IT-Security Award 2020](https://www.deutscher-it-sicherheitspreis.de/) for their work on mobile private contact discovery.
See [here](https://www.encrypto.cs.tu-darmstadt.de/home_page/news_feed/news_details_222528.en.jsp) for details.

### Attacks on WhatsApp, Signal, and Telegram in the News

See [**https://encrypto.de/news/contact-discovery**](https://encrypto.de/news/contact-discovery) for an up-to-date press review.

## What is Mobile Contact Discovery & Why Should I Care?

Mobile contact discovery allows users of mobile messengers to conveniently connect with people in their address book: newly registered users can instantly start messaging existing contacts based on their phone numbers without exchanging additional information like usernames or email addresses.

Some of the world's most popular mobile messengers (with billions of users) like [WhatsApp](https://www.whatsapp.com/) perform contact discovery by [regularly uploading and storing the users' entire address books](https://www.whatsapp.com/legal/#terms-of-service), while more privacy-concerned messengers like [Signal](https://signal.org/) transfer only [short hashes of phone numbers](https://support.signal.org/hc/en-us/articles/360007061452-Does-Signal-send-my-number-to-my-contacts-) or rely on [trusted hardware](https://signal.org/blog/private-contact-discovery/). Unfortunately, the low entropy of phone numbers indicates that it is feasible to reverse such hash values and therefore, albeit all good intentions, [there is no gain in privacy](https://doi.org/10.18420/sicherheit2018_04).

In a research collaboration between [TU Darmstadt](https://encrypto.de), [TU Graz](https://www.iaik.tugraz.at/), and [University of Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/secure-software-systems-group/), we show that currently deployed contact discovery services severely threaten users' privacy.

### Leaking Social Graphs via "Curious" or Compromised Service Providers

Revealing essentially all personal contacts to a service provider is a significant privacy risk and legal challenge, as from the social graph of users a variety of personal information can be inferred. Most importantly, sensitive contact relationships can become known and could be used to scam, discriminate, or blackmail users, harm their reputation, or make them the target of an investigation. Service providers could also be compromised or forced by government agencies to hand out data, resulting in the exposure of such sensitive information.

When installing a mobile messenger, users also jeopardize the privacy of people who are not even connected to the particular service by [transmitting their contact information without consent](https://guild.co/blog/is-whatsapp-in-breach-of-the-gdpr-a-lawyers-view/). An illustrative
example of a severe breach of privacy can be seen in the case of WhatsApp, which was acquired by Facebook in 2014 and shared its database with the parent company: [Facebook users received friend recommendations of strangers who happened to see the same psychiatrists](https://splinternews.com/facebook-recommended-that-this-psychiatrists-patients-f-1793861472).

### Leaking Personal (Meta) Data via Crawling Attacks

Malicious users or hackers might also be interested in extracting information about others. Examples for personal (meta) data commonly stored in a user's messenger profile include profile picture(s), nickname, status message, and the last time the user was online. By tracking such data over time, it is even possible to [build accurate behavior models](https://onlinestatusmonitor.com/). Matching accounts with other social networks and publicly available data sources allows third parties to [build extremely detailed profiles](https://doi.org/10.1145/2994459.2994471). From a commercial perspective, such knowledge can be utilized for targeted advertisement or [scams](https://www.usenix.org/conference/usenixsecurity19/presentation/tu). Vicious individuals could furthermore abuse such information for discrimination, blackmailing, or planning a crime, whereas nation states could be interested in [closely monitoring or persecuting citizens](https://www.zdnet.com/article/hong-kong-protesters-warn-of-telegram-feature-that-can-disclose-their-identities/).

Even the mere fact that a specific phone number is registered with a certain messaging service can be sensitive in many ways, especially when it can be linked to a person. For example, in areas where some services are strictly forbidden, disobeying citizens can be identified and persecuted. Comprehensive databases of phone numbers registered to a particular service can allow attackers to cause harm at a larger scale, e.g., by [distributing compromised messages to quickly exploit security vulnerabilities in messaging applications](https://www.forbes.com/sites/zakdoffman/2019/11/16/new-whatsapp-threat-confirmed-android-and-ios-users-at-risk-from-malicious-video-files/).

Since there are no noteworthy restrictions for signing up with messaging services, any third party can create a large number of accounts to crawl the user database of a messenger for information by requesting data for (randomly) chosen phone numbers. Such enumeration attacks cannot be fully prevented, since legitimate users must be able to query the database for contacts. In practice, rate-limiting is a well-established measure to effectively mitigate such attacks at a large scale, and one would assume that service providers apply reasonable limits to protect their platforms.

### Our Work towards Mobile **Private** Contact Discovery

In our line of work, we demonstrate the severity of the privacy threats outlined above in currently deployed contact discovery methods. Moreover, we propose suitable countermeasures to effectively migitage crawling attacks and present efficient cryptographic protocols to privately perform mobile contact discovery while revealing as little information as possible.

## Large-Scale Abuse of Mobile Contact Discovery [HWSDS22, HWSDS21]

Our study of three popular mobile messengers (WhatsApp, Signal, and Telegram) shows that, contrary to expectations, large-scale crawling attacks are possible. Using an accurate database of mobile phone number prefixes and very few resources, we queried 10% of US mobile phone numbers for WhatsApp and 100% for Signal. For Telegram we find that its API exposes a wide range of sensitive information, [even about numbers not registered with the service](https://core.telegram.org/tdlib/docs/classtd_1_1td__api_1_1imported_contacts.html).

We present interesting (cross-messenger) usage statistics, which also reveal that very few users change the default privacy settings (which in most cases are not privacy-friendly at all). Regarding mitigations, we propose novel techniques to significantly limit the feasibility of our crawling attacks, especially a new incremental contact discovery scheme that strictly improves over Signal's approach.

Furthermore, we show that currently deployed hashing-based contact discovery protocols are severely broken by comparing three methods for efficient hash reversal of mobile phone numbers. For this, we also propose a significantly improved rainbow table construction for non-uniformly distributed inputs that is of independent interest. All our methods can reverse hashes of mobile phone numbers within milliseconds.

### Responsible Disclosure

We demonstrate methods that allow to invade the privacy of billions of mobile messenger users by using only very few resources. We therefore initiated the official responsible disclosure process with all messengers we investigated (WhatsApp, Signal, and Telegram) and shared our findings to prevent exploitation by maleficent imitators.
As a result, WhatsApp has improved their protection mechanisms such that large-scale attacks can be detected, and Signal has reduced the number of possible queries to complicate crawling. Telegram responded to our responsible disclosure by elaborating on additional data scraping countermeasures beyond the rate limits detected by us. They are allegedly triggered when attackers use existing databases of active phone numbers and higher conversion rates than ours occur.

## Efficient Private Set Intersection (PSI) for Mobile Contact Discovery [KRSSW19]

The currently most promising approach to privately perform contact discovery without relying on trusted hardware is based on cryptographic protocols for private set intersection (PSI). Such protocols allow users and service providers to find matching contacts while not revealing any information about unrelated entries in the users' address books or the service providers' user databases.

Unfortunately, even in a weak security model where clients are assumed to follow the protocol honestly, previous protocols and implementations turned out to be far from practical when used at scale. This is due to their high computation and/or communication complexity as well as lacking optimization for mobile devices.

In our work, we remove most obstacles for large-scale global deployment by significantly improving two promising protocols by [Kiss et al. (PoPETS'17)](https://eprint.iacr.org/2017/670) while also allowing for malicious clients and providing optimized implementations for mobile devices. Our fastest protocol privately checks 1000 client contacts against a large-scale database with 250 Million entries in only 2.92s measured on a smartphone via a real WiFi connection and 6.53s via LTE.

We summarize the addressed privacy threats of mobile contact discovery and explain details about our PSI protocols in an easily understandable as well as illustrative video on [YouTube](https://www.youtube.com/watch?v=4vgKHmNaAAw).

## Publications
 * [HWSDS22] **_Contact Discovery in Mobile Messengers: Low-cost Attacks, Quantitative Analyses, and Efficient Mitigations_** by Christoph Hagen (University of Würzburg), Christian Weinert ([Royal Holloway, University of London](https://pure.royalholloway.ac.uk/portal/en/persons/christian-weinert(08c053b5-5ccd-46d5-8c87-a26b6419877e).html)), Christoph Sendner ([University of Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/staff0/christoph-sendner/)), Alexandra Dmitrienko ([University of Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/staff0/alexandra-dmitrienko/)), and Thomas Schneider ([TU Darmstadt](https://encrypto.de/schneider)) in [ACM Transactions on Privacy and Security (TOPS'22)](https://dl.acm.org/journal/tops). Paper available on **[ePrint](https://eprint.iacr.org/2022/875)**. Implementation available on **[GitHub](https://github.com/contact-discovery)**.
 * [HWSDS21] **_All the Numbers are US: Large-scale Abuse of Contact Discovery in Mobile Messengers_** by Christoph Hagen (University of Würzburg), Christian Weinert ([TU Darmstadt](https://encrypto.de/weinert)), Christoph Sendner ([University of Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/staff0/christoph-sendner/)), Alexandra Dmitrienko ([University of Würzburg](https://se.informatik.uni-wuerzburg.de/secure-software-systems-group/staff0/alexandra-dmitrienko/)), and Thomas Schneider ([TU Darmstadt](https://encrypto.de/schneider)) in [28. Annual Network and Distributed System Security Symposium (NDSS'21)](https://www.ndss-symposium.org/ndss-2021/). Paper available on **[ePrint](https://eprint.iacr.org/2020/1119)**. Implementation available on **[GitHub](https://github.com/contact-discovery)**.
 * [KRSSW19] **_Mobile Private Contact Discovery at Scale_** by Daniel Kales ([TU Graz](https://www.iaik.tugraz.at/person/daniel-kales/)), Christian Rechberger ([TU Graz](https://www.iaik.tugraz.at/person/christian-rechberger/)), Thomas Schneider ([TU Darmstadt](https://www.encrypto.de/schneider)), Matthias Senker ([TU Darmstadt](https://www.encrypto.cs.tu-darmstadt.de/home_page/news_feed/news_details_166274.en.jsp)), and Christian Weinert ([TU Darmstadt](https://www.encrypto.de/weinert)) in [28. USENIX Security Symposium (USENIX Security'19)](https://www.usenix.org/conference/usenixsecurity19). Paper available on **[ePrint](https://eprint.iacr.org/2019/517)**. Implementation available on **[GitHub](https://github.com/contact-discovery)**.
 