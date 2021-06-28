# PII Leak Prevention Guide
#### How to identify & prevent PII leaks -- learnings from 25+ major data breaches.

Today, personally identifiable information (PII) faces a wide variety of threats. In order to secure PII from leakage and exposure, organizations need to understand the nature of these threats as well as the tools they have at their disposal to ensure that their data remains secure. In this guide we'll cover what you need to know about PII, including what it is, how its definition has evolved over time, and how threat actors' techniques have adapted to the emergence of trends like PII's migration to the cloud. 

#### Table of contents

1. [What is Personally Identifiable Information (PII)?](#what-is-personally-identifiable-information-pii)
    * [Why is personally identifiable information important?](#why-is-personally-identifiable-information-important)
    * [What are the categories of personally identifiable information?](#what-are-the-categories-of-personally-identifiable-information)
2. [How is PII exposed?](#how-is-pii-exposed)
    * [What do insider threats look like?](#what-do-insider-threats-look-like)
        - [Example of insider threats](#example-of-insider-threats)
        - [Preventing insider threats](#preventing-insider-threats)
    * [What do external threats look like?](#what-do-external-threats-look-like)
        - [Example of external threats](#example-of-external-threats)
        - [Preventing external threats](#preventing-external-threats)
    * [What do security misconfigurations look like?](#what-do-security-misconfigurations-look-like)
        - [Example of security misconfigurations](#example-of-security-misconfigurations)
        - [Preventing security misconfigurations](#preventing-security-misconfigurations)
3. [An encyclopedia's worth of data security lessons](#an-encyclopedias-worth-of-data-security-lessons)
    * [How have data breaches changed?](#how-have-data-breaches-changed)
4. [Looking at hacker attack flows and the anatomy of breaches](#looking-at-hacker-attack-flows-and-the-anatomy-of-breaches)
    * [Common attack approaches](#common-attack-approaches)
    * [4 ways to protect PII and other sensitive data](#4-ways-to-protect-pii-and-other-sensitive-data)
    * [Adopt a data-centric security posture to keep PII top of mind](#adopt-a-data-centric-security-posture-to-keep-pii-top-of-mind)
5. [About Nightfall](#about-nightfall)

------------------------------------------------------

## What is Personally Identifiable Information (PII)?

Personally Identifiable Information (PII) [is formally defined as](https://www.dol.gov/general/ppii) "any representation of information that permits the identity of an individual to whom the information applies to be reasonably inferred by either direct or indirect means." This includes information that directly identifies an individual (e.g., name, address, Social Security number, or other identifying numbers or codes, telephone numbers, email addresses, etc.) or "by which an agency intends to identify specific individuals in conjunction with other data elements, i.e., indirect identification." These data elements may include a combination of gender, race, date of birth, geographic indicators, and other descriptors.

### Why is personally identifiable information important?

PII is a legal term concerning information that can help identify individuals in context. In many cases this information exists as electronic records maintained and stored by organizations. Storing and transmitting these records securely has proven to be a challenge for organizations. Since 2005 we've seen drastic increases of data breach incidents exposing PII, resulting in increased identity theft, financial fraud, and other cybercrime adversely affecting consumers. Some estimates, like those by U.S. nonprofit [The Identity Theft Resource Center](https://www.statista.com/statistics/273550/data-breaches-recorded-in-the-united-states-by-number-of-breaches-and-records-exposed/) (ITRC), suggest that between 2005 and 2019 there was a 930% increase in data breach events. Though these numbers have since leveled off since peaking in 2017, data breaches still remain more frequent today than at any point before 2016. While there were fewer breach incidents in 2020 other sources indicate that despite the decrease the [total number of records exposed last year exceeded 36 billion](https://www.helpnetsecurity.com/2020/10/30/records-exposed-2020/), the highest number on record.

In addition to data breaches becoming relatively more common, they're also somewhat more expensive today than they have been in the recent past. For example, IBM has found that the average cost of a data breach for companies has [increased by 10% since 2014](https://www.csoonline.com/article/3434601/what-is-the-cost-of-a-data-breach.html). Javelin estimates that in 2019 consumers lost [$16.9 billion to fraud](https://www.javelinstrategy.com/coverage-area/2020-identity-fraud-study-genesis-identity-fraud-crisis), a slight increase over the past 6 years. These costs make the consequences of data breaches staggering for both companies and consumers, making it all the more important to prevent them from happening.

### What are the categories of personally identifiable information?

**Many types of PII can be described in the following ways:**

1.  **Identity**: name, date of birth, signature, gender, race, familial situation
2.  **Contact information**: address, phone number, email address
3.  **Professional information**: job, company, position, date of hire, HR evaluation, salary
4.  **Administrative documents:** ID, passport number, driver's license, vehicle identification number (VIN), Social Security number
5.  **Healthcare**: biometric data, medical records
6.  **IT related:** Internet Protocol (IP) address, password(s), cookies, logs

[Back to top](#pii-leak-prevention-guide)

## How is PII exposed?

PII breaches or exposures can happen in a wide variety of ways which can make it difficult to prepare for data security threats and protect sensitive information. Generally, threats to PII fall under at least one of the three following categories:

1.  **Insider threat**. This results from someone from within your systems intentionally or unintentionally viewing or providing access to restricted data. Early in 2020, we talked about how work in a remote-first world could lead to insider threats becoming [an increased risk for organizations](https://nightfall.ai/resources/insider-threats-cybersecurity-threat-landscape-2020/).
2.  **External threat**. This involves someone outside your organization deliberately tampering with or modifying systems in order to exfiltrate data. 
3.  **Security misconfigurations.** Thesegenerally occur within an application that captures user data or in the environment where the sensitive data is stored. Security misconfigurations can result in data exposures on their own or can be exploited by internal or external threat actors to exfiltrate data.

### What do insider threats look like?

Insider threats are a persistent threat faced by organizations. [Verizon's annual data breach investigation reports](https://enterprise.verizon.com/resources/reports/dbir/) periodically find that the percent of breaches caused by insiders usually hovers around 30 to 33 percent. Verizon often stresses the importance of not overstating the impact of insider threats, but given the consistent rate at which they occur, it makes sense for companies to invest resources towards successfully identifying and mitigating them. 

Insider threats often come in two flavors, accidental or deliberate threats. 

Accidental insider threats can stem from:

-   Ignorance of internal data security policies or an otherwise poor understanding of cybersecurity best practices. 
-   Genuine human error.

Intentional threats can come from disgruntled employees and contractors or insiders who have incentive to steal from their company. These incentives tend to be financial in nature but don't necessarily have to be.

#### Example of insider threats

-   One common bad practice involves employees sending PII, protected student records, or financial data via email in plain text, or sent in unprotected attachments. This puts data at risk should it be intercepted while in transit. With regards to certain types of PII, like Social Security numbers, companies should not request that customers send data of this nature over email.
-   Another practice involves insiders with access to privileged information sending this data to themselves. For example, in November 2020 a Brazilian hospital employee [uploaded a spreadsheet with Protected Health Information (PHI) to GitHub](https://www.zdnet.com/article/personal-data-of-16-million-brazilian-covid-19-patients-exposed-online/). Such behavior may not be malicious and could be simply to continue work on a personal device or when away from the office. Regardless of intentions, though, it can create a breach of sensitive data.
-   In instances where a malicious insider has privileged access to systems, they can exfiltrate data with deliberate intent and cover their tracks. This is most common in corporate espionage cases (see [GE](https://www.fbi.gov/news/stories/two-guilty-in-theft-of-trade-secrets-from-ge-072920) and [Waymo](https://www.latimes.com/business/story/2019-08-27/ex-google-engineer-anthony-levandowski-is-charged-with-trade-secrets-theft)). Privileged insiders pose equal threat to customer and employee PII as well.

#### Preventing insider threats

Insider threats of all types can be difficult to deal with because they can stem from unexpected sources. Malicious insiders specifically might have knowledge of organization-wide security measures as well as physical access to hardware, making them especially difficult to deal with. One of the best ways to address insider threats is with preventative measures. For example, educating employees about the proper ways to handle sensitive data and [tying these practices to your organizational values](https://nightfall.ai/resources/culture-of-security-remote-work/) will make any employee who treasures their job feel strongly about their responsibility to protect data. We go into greater detail about how to do this in section A of our [2021 Security Playbook for Remote-first Organizations](https://nightfall.ai/download-2021-security-playbook-remote-first-orgs/).

In addition to developing robust employee education programs, putting into place access controls can help determine when sensitive data is being shared, accessed, viewed, or modified effectively allowing you to intervene or mitigate a data security incident. For example, Nightfall AI provides cloud-native data loss prevention (DLP) which specifically helps companies deal with sensitive data exposure and exfiltration risks in SaaS and IaaS systems like Slack, Google Drive, GitHub, and Atlassian. You can learn more about access controls like cloud DLP in section B in our aforementioned security playbook, and you can learn more about Nightfall [here](https://nightfall.ai/resources/nightfall-forrester-2020/).

### What do external threats look like?

External threats make up the lion's share of the threats faced by organizations. They encompass a wide range of activities, making them more difficult to define. Generally, though, an external threat actor has one of two ways they can steal data. They can either attack a system directly or, if that proves too difficult, bypass an organization's security.

Direct attacks on a system often take the form of exploiting known vulnerabilities in software or hardware used by the target organization. This can include systems that haven't been updated, encrypted, or that have internet-facing permissions. More sophisticated hackers might use techniques like [buffer overflow](https://www.csoonline.com/article/3513477/what-is-a-buffer-overflow-and-how-hackers-exploit-these-vulnerabilities.html) attacks, [SQL injections](https://cyware.com/news/sql-injection-is-still-a-critical-attack-vector-e535dcc3), [server side request forgery](https://www.darkreading.com/edge/theedge/ssrf-101-how-server-side-request-forgery-sneaks-past-your-web-apps-/b/d-id/1337121), HTTPS downgrading, cookie hijacking, or other types of attacks that require technical knowledge of a target system or attacking key stakeholders who have access to a target system.

Attacks that bypass an organization's security can include:

-   Social engineering to obtain credentials or sensitive information
-   Certain malware like keyloggers and packet sniffers that passively collect information from customers or employees who have privileged access
-   Using credential stuffing to brute force into target systems with a [cache of previously leaked credentials](https://www.helpnetsecurity.com/2020/10/08/corporate-credentials-dark-web/)

None of these examples are meant to provide an exhaustive illustration of what hackers can do, but they do highlight some of the most common attack vectors they might try to exploit. The [MITRE ATT&CK knowledge base](https://attack.mitre.org/#) categorizes a wide variety of techniques that an external actor might use to gain [initial access](https://attack.mitre.org/tactics/TA0001/) into a system.

#### Example of external threats

-   An application encrypts credit card numbers in a database using automatic database encryption. However, this data is automatically decrypted when retrieved, allowing a hacker to use a SQL injection flaw to retrieve credit card numbers in clear text.
-   An API for a social media site supports unauthenticated requests with no rate limit. By using simple GET requests, an attacker can harvest the location data of users in real time. The most striking example of a vulnerability like this was with the service [LocationSmart](https://krebsonsecurity.com/2018/05/tracking-firm-locationsmart-leaked-location-data-for-customers-of-all-major-u-s-mobile-carriers-in-real-time-via-its-web-site/).
-   A password database uses unsalted or simple hashes to store everyone's passwords. A file upload flaw allows an attacker to retrieve the password database. All the unsalted hashes can be exposed with a rainbow table of pre-calculated hashes. Hashes generated by simple or fast hash functions may be cracked by GPUs, even if they were salted. 
-   A spear phishing campaign targeting a human resources manager is successful, allowing a hacker to view company employee information. In order to get even greater access within the company's systems, the attacker studies the employment information of a specific employee who works in the IT department to spear phish this employee to get access to critical systems.
-   An attachment in a mass phishing campaign centering around a request to schedule a follow-up appointment after the target has received their second COVID vaccination shot gets clicked. The payload introduces persistent malware on the device. Hackers are using [timely events](https://threatpost.com/linkedin-spear-phishing-job-hunters/165240/) to provide detailed pretexts for their scams. While the immediate targets might not be corporate devices or systems, it's likely that some of the infected devices may eventually connect to corporate networks where they'll be used to introduce malware that can embed ransomware or extract data.

#### Preventing external threats

Many of the same fundamentals that apply to preventing and mitigating insider threats are also relevant to addressing external ones. Ensuring employees understand and appreciate security best practices and organizational security policies makes them more resilient to phishing and other forms of social engineering. Access controls can make sure that an attacker is blocked from taking actions that violate company policy, even if they hijack privileged access from an authorized account. In addition to these considerations, ensuring that your organization has security processes in place will allow for deft responses to disruptive incidents. These are things like business continuity processes, as well as preventative processes like vulnerability and third party risk management. We discuss some of these topics in section C of our [2021 Security Playbook for Remote-first Organizations](https://nightfall.ai/download-2021-security-playbook-remote-first-orgs/).

### What do security misconfigurations look like?

According to IBM's *Cost of a Data Breach Report*, cloud misconfigurations remain one of the [top causes of data exposure](https://www.ibm.com/downloads/cas/QMXVZX6R). While internal and external threat actors can take advantage of these to exfiltrate data, often such incidents can result in data breaches without the involvement of a threat actor as sensitive data becomes exposed to the open internet. These types of misconfigurations can appear in both cloud and non-cloud systems for a variety of reasons including:

-   Human error.
-   Default settings that obfuscate insecurities. For example in 2017 AWS introduced [several feature and UI changes](https://www.helpnetsecurity.com/2019/09/23/s3-bucket-security/) to make exposed S3 buckets more apparent to users. This was followed by a [decrease](https://threatpost.com/files-exposed-record-misconfigs/145177/) in the number of buckets exposed on the open internet. This issue can apply within SaaS environments as well, usually with regard to overly broad permissioning of files or content within the application (eg: a Google Doc file with PII containing public permissions). 
-   Bad organizational practices that allow for points of failure, like no two factor authentication for protecting sensitive systems or hard coding credentials into code repositories.

#### Example of security misconfigurations

-   Sometimes PII is left in photos, PDFs, or word processing documents that are unencrypted or otherwise publicly accessible. This could be because of permissions being too broad in a SaaS application like Google Drive or a [misconfiguration in a web application](https://krebsonsecurity.com/2019/05/first-american-financial-corp-leaked-hundreds-of-millions-of-title-insurance-records/).
-   Some sites and applications might still be using legacy cryptographic algorithms by default or leaving these in older code that's still accessible.
-   Another scenario, which often happens by accident, involves saving files containing PII or protected student data in a web folder or database that is publicly accessible online. Developers need to ensure that folders and databases that store sensitive customer information are not web-facing.

#### Preventing security misconfigurations

Preventing security misconfigurations is no different from preventing insider or external threats. Training employees well and having visibility and access controls in environments with sensitive data will be critical to this process. While our security playbook can help with this, in the final section of this guide we'll briefly cover some of the most important security controls for protecting PII in a variety of environments.

[Back to top](#pii-leak-prevention-guide)

## An encyclopedia's worth of data security lessons

As the Internet matured, organizations saw a dramatic increase in their attack surface. The last two decades have provided many incidents which can still serve as a lesson today. Below is a list of 25 organizations who experienced major breaches in the last 16 years. The following 25 stories should illustrate many of the PII risks we've highlighted above.

1.  **Aadhaar data breach -- Early 2018 (approx. 1 billion records)**

In early 2018, it was discovered that India's government identification database, which contains records on nearly all Indian citizens, [was leaking PII.](https://www.zdnet.com/article/another-data-leak-hits-india-aadhaar-biometric-database/) By using the Aadhaar number of a citizen, which functions much like an American Social Security number, anyone could exploit the API of state-owned utility company Indane to download the PII of Aadhaar holders. Some of this data was being sold through black markets as confirmed by India's Tribune. This isn't the [only incident surrounding the system](https://techcrunch.com/2019/01/31/aadhaar-data-leak/), but remains one of the most prominent.

2.  **Amazon data breaches -- 2018, 2019**

The [2018 Amazon data breach](https://techcrunch.com/2018/11/21/amazon-admits-it-exposed-customer-email-addresses-doubles-down-on-secrecy/) is notable, not because of Amazon's reputation or even because of the extent of the breach (which is unknown). This data breach is noteworthy because of the way Amazon handled it. Just before Black Friday of 2018, the company quietly notified some customers of a technical error on their website, which exposed customer email addresses. Security experts criticized not just the secrecy around the disclosure of the breach, but the [manner in which customers were notified](https://twitter.com/briankrebs/status/1065219981833617408). In an unrelated story in 2019, it was discovered that Amazon team members auditing Alexa user commands in some cases had the permissions to [associate a user with their address](https://www.techradar.com/news/amazon-alexa-team-can-see-users-home-addresses-report-claims).

3.  **America Online (AOL) data breaches -- 2004, 2006 (over 90 million total records)**

AOL's data security woes were a harbinger of the types of security incidents that were to come in following years. In 2004 a software engineer at the company stole and sold a list of [92 million AOL screen names](https://money.cnn.com/2004/06/23/technology/aol_spam/) to scammers who then spammed these accounts. 

The company would later get into hot water in the summer of 2006 for what became known as "Data Valdez." The company released a report on user search patterns. The report "anonymized" the search queries of over 650,000 users with a simple numerical identifier. The identifier was tied to a search query, with some queries containing PII. This ultimately allowed for many [users' identities to be exposed](https://www.nytimes.com/2006/08/09/technology/09aol.html).

4.  **Anthem Blue Cross Blue Shield data breaches -- 2015, 2017 (over 80 million total customers)**

In 2014, [Anthem employees became the target of a sophisticated phishing](https://krebsonsecurity.com/2015/02/anthem-breach-may-have-started-in-april-2014/) campaign that was eventually [attributed to Chinese nation-state hackers.](https://www.nytimes.com/2019/05/09/technology/anthem-hack-indicted-breach.html) By December 2014, this hacker group had acquired the credentials and access they needed to exfiltrate PII from Anthem's corporate data warehouse. In total [nearly 80 million individuals](https://money.cnn.com/2015/02/04/technology/anthem-insurance-hack-data-security/) had their PII accessed. The massive request for this data was logged and Anthem discovered the incident in early 2015.

In July 2017, an Anthem employee appeared to have emailed a file with information about Anthem companies' members to a personal email address, which may have exposed more than [18,500 Anthem Medicare members'](https://www.cnbc.com/2017/07/31/new-anthem-data-breach-by-contractor-affects-more-than-18000-enrollees.html) Social Security numbers and Medicare identification data.

5.  **BlueKai (Oracle) data breach -- June 2020 (several billion records)**

BlueKai, a marketing technology company acquired by Oracle in 2014, [was involved in a massive data leak](https://techcrunch.com/2020/06/19/oracle-bluekai-web-tracking/) in 2020. BlueKai uses cookies and other technology to track and fingerprint users across the web. Estimates suggest that BlueKai [tracks up to 1.2% of all web traffic](https://www.forbes.com/sites/jessedamiani/2020/06/19/oracles-bluekai-spilled-billions-of-records-of-web-tracking-data/?sh=3cfd34c42c47). While BlueKai is not a data broker in the traditional sense --- it does not sell personal data, merely processes it and provides anonymized analytics to marketers to use for targeted marketing --- the unencrypted database involved in the leak contained raw data divulging factoids about the people BlueKai had been targeting. This included details like where they were located, how they liked to spend their money, and purchase intent data. The breach is fairly similar to others like [the breach that affected then unknown data broker Exactis](https://www.wired.com/story/exactis-database-leak-340-million-records/) in 2018 or one involving a server belonging to an unknown entity which leaked PII for [up to 65% of American households](https://techaeris.com/2019/04/29/report-says-80-million-american-households-affected-by-unknown-data-breach/). The combination of cloud misconfigurations and the growth of highly detailed demographic and psychometric databases like these will likely be a boon for phishers and scammers who can use this data to create more complex and highly individualized social engineering campaigns or even blackmail.

6.  **CAM4 data breach -- May 2020 (10.88 billion records; hundreds of users)**

The adult platform CAM4 was found [leaking data through an Elasticsearch misconfiguration](https://www.wired.com/story/cam4-adult-cam-data-leak-7tb/). Along with AWS S3, Elasticsearch is one of the most common sources of cloud misconfigurations. The researchers who discovered the leak determined that the leaking server was a log aggregation server from many sources. Alongside this user data, researchers found password hashes for company systems. This user data was apparently aggregated as a result of a developer looking to debug an issue, possibly as a result of a stack trace.

7.  **Capital One data breach -- July 2019 (106 million customers)**

One of the biggest financial data breaches since the Equifax hack, [the Capital One breach](https://krebsonsecurity.com/2019/07/capital-one-data-theft-impacts-106m-people/) compromised the personal data of roughly 100 million Americans, and approximately 6 million Canadians. Capital One has said that roughly 140,000 Social Security numbers were exposed. The breach resulted from a misconfigured web application firewall which permitted external requests to resources inside of Capital One's AWS environment. In 2020, on the one-year anniversary of the hack, we wrote a detailed review of some [important takeaways from the incident](https://nightfall.ai/resources/3-cloud-security-lessons-capital-one-breach/).

8.  **Democratic Senatorial Campaign Committee -- July 2019 (6.2 million voters)**

Researchers [discovered an unprotected S3](https://techcrunch.com/2019/08/06/democratic-senate-millions-emails/) Bucket containing a spreadsheet titled "EmailExcludeClinton.csv" which was uploaded in 2010. The spreadsheet contained the email addresses of over 6 million Americans. It's unclear how long the bucket was exposed for or if anyone had accessed the data. Unlike the other database misconfiguration-based breaches mentioned in this list, the data only contained emails. 

9.  **Department of Veteran Affairs data breaches -- 2006, 2010 (over 26 million total veterans)**

In May of 2006, a burglar broke into the home of a Veteran Affairs (VA) computer analyst and stole their laptop which contained unencrypted records of over [26 million veterans, reserve, and active duty military personnel](https://www.healthcareitnews.com/news/6-lasting-effects-2006-va-data-breach-privacy-security). Similar incidents affecting a much smaller number of veterans [would happen again in 2010](https://thehill.com/policy/technology/97817-va-loses-another-laptop-with-veterans-personal-information). Although the VA has since faced a number of [breaches](https://www.cnn.com/2020/09/14/politics/veterans-affairs-data-breach/index.html), this early breach is notable for [transforming the culture of the VA](https://fcw.com/articles/2013/08/21/veterans-affairs-data-breaches.aspx) and serving as a useful illustration of a risk more salient in our present remote work culture.

10.  **DSW data breach -- April 2005 (1.4 million customers)**

The DSW Inc. breach is notable because it's one of the first recorded breach disclosures impacting over a million customers' payment details. This hack is among those perpetrated by [Albert Gonzales](https://www.nytimes.com/2010/11/14/magazine/14Hacker-t.html), a 2000s-era hacker who specialized in targeting payment systems and corporate networks (many of which were [often unencrypted](https://www.darkreading.com/attacks-and-breaches/wardriving-burglars-hacked-business-wi-fi-networks/d/d-id/1100324)). While data exfiltration has always existed, this breach highlighted the sheer scale of data which threat actors could target. Although the number of compromised credit cards was staggering at the time, it would be quickly eclipsed as this [Washington Post infographic illustrates](https://www.washingtonpost.com/graphics/business/the-scale-of-large-hacks/). Gonzales himself would go on to steal [over 45 million credit card numbers](https://www.computerworld.com/article/2544306/tjx-data-breach--at-45-6m-card-numbers--it-s-the-biggest-ever.html) in the infamous TJX Companies hack just a little over a year later.

11.  **eBay data breaches -- 2014, 2017 (possibly 145 million customers or more)**

In May of 2014, eBay disclosed that hackers had unauthorized access to corporate systems between late February and early March of that year. eBay was unable to determine if specific accounts were accessed and notified [its then 145 million users](https://www.databreachtoday.com/ebay-breach-145-million-users-notified-a-6858). The breach is believed to have resulted from a spear phishing campaign that targeted [at least three eBay corporate employees](https://www.businessinsider.com/cyber-thieves-took-data-on-145-million-ebay-customers-by-hacking-3-corporate-employees-2014-5).

eBay experienced another incident just three years later. In December of 2017 the EcommerceBytes Blog notified the company that customers' first and last names along with their purchase history [appeared on Google Shopping](https://www.ecommercebytes.com/C/blog/blog.pl?/pl/2017/12/1512941047.html). While many stores aggregate reviews to Google Shopping, typically reviews only contain user names or first names with initial. [Google responded](https://www.ecommercebytes.com/C/blog/blog.pl?/pl/2017/12/1513004607.html) to the outlet's inquiry by masking customer names once they'd been notified. As this was not a formal breach, eBay does not appear to have provided details on the scope of the account affected; however, it could have impacted anyone who submitted a review to eBay until Google addressed the issue.

12.  **Equifax data breach -- September 2017 (over 147 million customers)**

The Equifax data breach likely needs no introduction. It's a story that will be used for years to come as a cybersecurity, business, and PR [case study](https://www.researchgate.net/publication/337916068_A_Case_Study_Analysis_of_the_Equifax_Data_Breach_1_A_Case_Study_Analysis_of_the_Equifax_Data_Breach) and has been [heavily analyzed by industry experts](https://www.bankinfosecurity.com/postmortem-behind-equifax-breach-multiple-failures-a-11480). The key detail here is that Equifax experienced a slow burn as hackers lingered in company databases for months as a result of a known CVE (CVE-2017-5638) in Apache Struts. Equifax purportedly had several systems in place that should have notified them of the vulnerability like routine system scans, a network traffic monitoring device, and an email notice of the U.S. CERT alert on the CVE. Equifax was also [warned by a security researcher](https://www.vice.com/en/article/ne3bv7/equifax-breach-social-security-numbers-researcher-warning) who was able to query one of the company's databases for plaintext PII over the internet as early as 2016. Ultimately, however, these notifications and systems failed for Equifax. These failures now serve as a great reminder that redundancy and periodic vigilance are required to manage an effective security program.

13.  **Estée Lauder data breach -- Feb 2020 (440 million records)**

[The Estée Lauder leak](https://www.forbes.com/sites/daveywinder/2020/02/11/estee-lauder-data-leak-440-million-records-exposed/?sh=2703e7e12590) serves as an interesting case study in how breaches could result in supply chain attacks, as the leak exposed mostly data from the company's content management system. The data include things like ports, IP addresses, pathways, and storage info that would be useful for infiltrating the company's systems and exposing users to malware.

14.  **Facebook data breaches -- 2013 to 2019**

Facebook is no stranger to controversy. In the last decade the company been in the news every year for a multitude of reasons, with security chief among them. As early as 2012, Facebook's site was [leaking data](https://www.huffpost.com/entry/facebook-leak-data_n_3510100) to users using the "Download Your Information" tool. Similar glitches with other parts of Facebook's [site](https://www.wired.com/story/facebook-bug-14-million-users-posts-public/) and [features](https://www.vox.com/2018/9/28/17914598/facebook-new-hack-data-breach-50-million) have occurred as well and Facebook has been called out for years. Aside from this, in 2019 it was discovered that Facebook had been storing hundreds of millions of user's [passwords in plaintext](https://krebsonsecurity.com/2019/03/facebook-stored-hundreds-of-millions-of-user-passwords-in-plain-text-for-years/) for both Facebook and [Instagram](https://mashable.com/article/instagram-passwords-exposed-by-facebook/), as far back as 2012 for some records. 

Facebook has also faced scrutiny over practices like [leveraging 2FA numbers for advertising purposes](https://techcrunch.com/2018/09/27/yes-facebook-is-using-your-2fa-phone-number-to-target-you-with-ads/) as well as providing advertisers with [shadow profiles](https://mashable.com/2013/06/26/facebook-shadow-profiles/#FtgTUa780ZqY) (consumer data [not formally provided by users](https://gizmodo.com/facebook-is-giving-advertisers-access-to-your-shadow-co-1828476051)). Finally, Facebook has gotten into trouble several times regarding the amount of data it provides to developers on its platform via its APIs. This most notably was illustrated with 2018's Cambridge Analytica story; however, even after Facebook began limiting the amount of data provided to developers stories like the [Cultural Colectiva](https://www.theverge.com/2019/4/3/18293978/facebook-app-developers-leak-user-records-data-cloud-servers) AWS S3 leak illustrated that third-party developers could still put Facebook user data at risk with poor security practices.

15.  **Google data breach -- Oct 2018 (possibly up to 52 million users)**

As a result of an undisclosed bug, Google+ leaked private user data between 2015 and 2018, according to [the Wall Street Journal](https://www.wsj.com/articles/google-exposed-user-data-feared-repercussions-of-disclosing-to-public-1539017194). A [second bug](https://www.zdnet.com/article/google-hit-by-second-api-bug-impacting-52-5-million-users/) was discovered that could have used the Google+ API to use apps to harvest specific types of personal information like name, email, occupation, and more. As a result of these bugs, Google moved to close Google+ in April of 2019.

16.  **LinkedIn data breach -- 2012 & 2016 (up to 167 million users)**

In 2016 a number of breaches that occurred earlier in the 2010s came to light, with the LinkedIn breach being one of them. Although LinkedIn was aware of a breach in 2012, which it [reported to its users](https://blog.linkedin.com/2012/06/06/linkedin-member-passwords-compromised), the true scope of the breach wouldn't be known until May of 2016. At the time LinkedIn became aware of the breach only 6.5 million users were identified as victims, but the true number was [closer to 167 million users](https://www.vice.com/en/article/78kk4z/another-day-another-hack-117-million-linkedin-emails-and-password). Hackers had simply posted a fraction of the passwords they'd stolen online, keeping the rest of the breached records close to the vest. Like many of the resurfaced password breaches that came to light in 2016; the passwords in the LinkedIn breach were not salted and only encrypted with SHA1. As a result most of the passwords were cracked pretty quickly. The LinkedIn breach revealed a multi-part failure. Beyond the weak encryption, what's most surprising is that LinkedIn had no way of knowing how many records were exfiltrated until hackers disclosed the information. Later in 2016, Lynda.com, which was purchased by LinkedIn in 2015 [experienced a breach in December](https://www.zdnet.com/article/linkedins-lynda-com-suffers-database-breach/).

17.  **Microsoft data breach -- January 2020 (250 million)**

Microsoft is no stranger to [data breaches](https://www.pcworld.com/article/214775/microsoft_cloud_data_breach_sign_of_future.html). In December of 2019 security researchers discovered no less than five servers containing duplicate records. These servers were unsecured and contained Elasticsearch instances with records going back as far as 2005. Although a lot of the PII in these records was redacted, some records weren't redacted entirely allowing for partial leakage of IP addresses, emails, and in some cases names. It's worth noting that in 2021, [Microsoft Exchange Servers](https://krebsonsecurity.com/2021/03/at-least-30000-u-s-organizations-newly-hacked-via-holes-in-microsofts-email-software/) have been hit by what might be nation state actors who've found backdoors into customers' email systems. This specific incident is ongoing as of the time of this writing; however its scope is predicted to be massive.

18.  **Novestrat data breach -- September 2019 (over 20 million Ecuadorians)**

Marketing analytics firm Novestrat managed [an unsecured server](https://www.cnn.com/2019/09/17/americas/ecuador-data-leak-intl-hnk-scli) that leaked out full names, dates, places of birth, education, phone numbers, and national identity numbers of millions of Ecuadorians. At the time of the breach, Ecuador's population was just shy of 17 million, indicating that the breach could have very well impacted the entire population of the country as well as deceased Ecuadorians.

19.  **The Republican National Committee (RNC) data breach -- June 2017 (over 198 Americans)**

Deep Root Analytics, a contractor hired by the RNC hosted [over 1 TB of PII](https://gizmodo.com/gop-data-firm-accidentally-leaks-personal-details-of-ne-1796211612) on a publically accessible S3 instance. The database contained not just contact information like names, dates of birth, addresses, and phone numbers but preferences like religious affiliation and other more personal details that were likely meant to build high level psychographic profiles. Although similar to other breaches listed in this guide, this one is notable for being one of the first of this scale.

20.  **Snapchat data breaches -- 2014, 2016, 2018, & 2019**

In 2014, Snapchat faced two breach incidents. [The first](https://www.theguardian.com/media/2014/jan/03/phone-hacks-snapchat-breaks-silence), occurring around New Years involved apparent greyhat hackers who were enraged by Snapchat's slow response to a security report posted by researchers on Christmas day. This report elaborated on vulnerabilities that the researchers had discovered earlier in 2013. On December 27, Snapchat issued a statement saying that they implemented safeguards to make it more difficult for their system to be abused. In response, the hackers launched a site called SnapchatDB which used these vulnerabilities to scrape as many as 4.6 million users from the app. Later in 2014, unauthorized third-party apps [exposed hundreds of thousands of Snapchat photos](https://techcrunch.com/2014/10/10/snapchat-our-servers-were-not-breached-in-the-snappening-blame-3rd-party-apps/).

Snapchat would come under scrutiny later in the decade as well. In 2016 the company fell victim to a phishing campaign [impersonating the company's CEO](https://www.theverge.com/2016/2/29/11132988/snapchat-employee-data-breach-payroll-phishing). A separate 2018 phishing attempt would target over [50,000 of Snapchat's users](https://www.theverge.com/2018/2/16/17017078/snapchat-phishing-attack-klkviral-dominican-republic). Finally, in 2019 it was revealed that some Snapchat employees have access to internal tools like SnapLion which allowed employees to spy on users. Several current and former employees at the time confirmed [instances in which these tools were abused](https://www.vice.com/en/article/xwnva7/snapchat-employees-abused-data-access-spy-on-users-snaplion).

21.  **SolarWinds data breach -- November 2020 (18,000 customers)**

The SolarWinds hack headlined 2020 as one of the most notable hacks of the year. Unlike most of the other breaches on this list, the SolarWinds incident is a supply-side attack staged by nation state actors to embed advanced persistent threats within foreign infrastructure, making it the most unique hack on this list. The scope of the breach keeps expanding as we learn more. From what we know, it appears SolarWinds had lax security practices. For example, [an extremely weak password to an FTP server](https://www.cnn.com/2021/02/26/politics/solarwinds123-password-intern/index.html) is believed to have been in a GitHub repo in plain text for up to a year, if not longer. This password is not believed to have [resulted in the hack](https://www.theregister.com/2020/12/16/solarwinds_github_password/), but serves as an indication of security troubles the company faced. A Reuters report highlights [other concerning trends](https://www.reuters.com/article/global-cyber-solarwinds/hackers-at-center-of-sprawling-spy-campaign-turned-solarwinds-dominance-against-it-idUSKBN28P2N8), like SolarWinds taking days to take down the malicious modifications uploaded to its servers after the attack was discovered. Ultimately, this highlights that no company can afford to take security for granted. That goes for companies providing services as well as customers who are vetting third-party risk.

22.  **Twitter data breaches -- 2018, 2019, 2020**

Twitter has experienced multiple security incidents in its history. In May of 2018, Twitter urged all of its followers to change their passwords after its log system began [saving passwords in plaintext](https://www.theverge.com/2018/5/3/17316684/twitter-password-bug-security-flaw-exposed-change-now). The issue was quickly caught and fixed. In 2019 there were several incidents, like a bug that allowed account location [to be shared with ad partners](https://techcrunch.com/2019/08/07/twitter-fesses-up-to-more-adtech-leaks/), a bug that might have made [Android users' private tweets public](https://www.theverge.com/2019/1/17/18187143/twitter-bug-android-protected-tweets-turned-off) for years, an insider threat involving two employees who [spied for the Saudi Arabian government](https://www.npr.org/2019/11/06/777098293/2-former-twitter-employees-charged-with-spying-for-saudi-arabia), and what appears to have been an attempt by state actors to use Twitter's APIs [to identify users by phone number](https://inc42.com/buzz/twitter-data-breach-govt-accounts-tried-to-access-user-phone-numbers/).

In July of 2020, Twitter would experience its biggest hack which involved [the hijacking of multiple high-profile and celebrity accounts](https://www.dfs.ny.gov/Twitter_Report) on the platform. The attack was initiated through social engineering scams targeting Twitter employees. Although the phishing attempt did not immediately grant the attackers the access they needed, they used the first account they compromised to stage the next phase of their attack. Eventually they had the credentials they needed to access a Slack channel that [held credentials to Twitter's "backend" or administrator panel](https://ia.acs.org.au/article/2020/here-s-how-twitter-got-hacked.html). In all 130 high profile Twitter user accounts were targeted.

23.  **Uber data breach -- 2016 (57 million users)**

Like some of the other technology companies on this list, Uber has been in hot water regarding its privacy stances. For example, up until 2016, the app's controversial "God View" allowed executives [to track riders in real time](https://www.usatoday.com/story/tech/2016/01/06/uber-settles-god-view-allegations/78383276/). The same year, Uber would become known for an infamous cover up of a data breach, going as far as to pay hackers through its bug bounty program [to keep the hack quiet](https://money.cnn.com/2017/11/22/technology/uber-hack-consequences-cover-up/index.html). The hack leveraged [unencrypted AWS keys in one of its GitHub repositories](https://www.inc.com/adam-levin/heres-how-your-favorite-services-will-be-hacked-in-2018.html), a common threat vector we've often [warned about](https://nightfall.ai/guide-to-data-loss-prevention-dlp-secrets-detection-on-github/). A similar attack vector was used by the very same hackers to [conduct the Lynda.com breach](https://www.infosecurity-magazine.com/news/two-plead-guilty-to-uber-and/).

24.  **Venmo data breach -- 2018 & 2019**

Although not a data breach in a traditional sense, Venmo was [forced to settle with the FTC](https://www.ftc.gov/news-events/press-releases/2018/02/paypal-settles-ftc-charges-venmo-failed-disclose-information) in 2018 over GLBA privacy violations among other things. The FTC complaint brought against the fintech startup indicated that the company misled users about their privacy on the platform. By default, [all Venmo transactions were public,](https://www.theguardian.com/world/2018/jul/17/venmo-payments-app-default-privacy-settings-public-information) and the UI to set these transactions private was fairly convoluted. As a result of this settlement, Venmo was supposed to make certain changes to prioritize user privacy. However, in 2019, a security researcher found that the live feed of user activity on Venmo's login page could be scraped. By using a simple script, the researcher [leveraged Venmo's APIs to make unauthenticated requests](https://techcrunch.com/2019/06/16/millions-venmo-transactions-scraped/) to retrieve user information to demonstrate this issue.

25.  **Yahoo! data breaches -- 2013 & 2014 (3 billion users)**

No list of data breaches would be complete without mentioning Yahoo, which experienced the largest breach on record. In 2013 Yahoo was breached and the credentials of all 3 billion of their user base were affected. The full scope of this data breach wouldn't surface until 2017. Yahoo, like LinkedIn (listed above), Dropbox and [MySpace](https://www.vice.com/en/article/pgkk8v/427-million-myspace-passwords-emails-data-breach) was part of a cohort of tech companies [that had been hacked in the early 2010s](https://www.cpomagazine.com/cyber-security/the-data-dump-of-2-2-billion-breached-accounts-what-you-need-to-know/) and had user data end up [in the same dark web marketplace](https://www.vice.com/en/article/aeknw5/yahoo-supposed-data-breach-200-million-credentials-dark-web). Unlike LinkedIn, Yahoo wouldn't discover any trace of the 2013 hack until 2016, when it'd become alerted to an entirely separate breach, [occurring in 2014](https://www.bbc.com/news/world-us-canada-37447016). Through this investigation it discovered the 2013 breach, which it initially believed only impacted 1 billion users. After completing its investigation in 2017 Yahoo revised the number to 3 billion. The Yahoo hack is notable for the same reasons as the aforementioned LinkedIn 2012 breach because Yahoo didn't know the full extent of the breach until years later. Passwords stolen from Yahoo used the MD5 cryptographic hashing algorithm which was relatively weak, even at the time of the breach. Despite these similarities, the Yahoo data breach stands above as a stark reminder of just what's at stake when security fails.

### How have data breaches changed?

Nightfall's own investigation into the biggest breaches of the past 16 years correlate with the trends we discovered others like the ITRC reporting on. Data breaches have undoubtedly grown larger in the past 16 years. One thing has been consistently true: Since 2004 we've seen more "mega breaches" involving the exposure of over 1 million records. In many cases the number of records exposed corresponds to the number of individuals impacted, but this isn't always the case. Even when the number of individuals impacted is low or unknown, a disproportionate number of records can be exposed. In these instances, the amount of data associated with a given individual can be very high. 

Take for instance the Oracle/BlueKai breach which we mentioned above. While billions of records were leaked, it's unlikely that billions of people were affected. What this likely means is that each individual impacted by this breach could have dozens or hundreds of details associated with their identity. This in some ways might be worse because while there are fewer individuals impacted, the amount of data on each person victim will be highly detailed and intricate psychometric data. This kind of information can be utilized effectively in spear phishing campaigns or blackmail.

Below are graphs highlighting the most important data breach trends in the past 16 years:

![](https://nightfall.ai/wp-content/uploads/2021/05/image-1-1024x632.png)

Looking at the largest breaches on record since 2004, we found that while most years after 2003 have mega breaches, they became increasingly common after 2015. These breaches, however, can vary wildly in the number of individuals they impact.

![](https://nightfall.ai/wp-content/uploads/2021/05/image-1024x633.png)

System misconfigurations, in which data is leaked without the involvement of a threat actor are by far the most common cause of PII exposures, even in the largest breaches that have occurred over the past 16 years. External threat actors are the second most common cause of PII exposures involving mega breaches.

For our analysis we looked at the largest breaches that took place between 2004 and 2020. The primary metric is the number of records exposed, although we also looked at the number of individuals affected as well. Where possible, we also looked at other details like primary and secondary causes of a breach as well as its cost. A full report of our findings is forthcoming.

[Back to top](#pii-leak-prevention-guide)

## Looking at hacker attack flows and the anatomy of breaches

### Common attack approaches

Based on the our research into data breaches, the following attack vectors stand out:

1.  A very common target, especially in the earliest days of data breaches, were passwords. Hackers would either indirectly attack crypto or steal keys. This could be done through man-in-the-middle attacks (today this is nearly impossible without downgrading HTTPS), compromising the client's browser or system, or stealing records from the server they're stored on. Any previously retrieved password records or databases could be brute forced and cracked. To the best of our knowledge this is what happened with the Yahoo, LinkedIn, and Myspace breaches. Password databases were stolen from these companies' servers and hackers took their time cracking passwords; many of which used weaker forms of encryption like SHA-1, or MD5. Because users and sometimes employees reuse passwords, it's possible that old caches of passwords could be used to start future breaches.

2.  Attacks have moved on from targeting just passwords, but the common flaw of simply not encrypting sensitive data remains an issue. This is best illustrated by the fact that many of the biggest data breaches of the past several years have involved databases that were simply exposed to the open internet. Overly permissive settings in systems like AWS S3 or Elasticsearch may allow databases to either be indexed or found by anyone scanning open ports. This is illustrated by the number of AWS S3 Buckets and Elasticsearch clusters that have been found using tools like [Shodan](https://www.csoonline.com/article/3276660/what-is-shodan-the-search-engine-for-everything-on-the-internet.html) or BinaryEdge.

3.  Exposed APIs also prove to be a common risk vector, as hackers leverage these to make (often unauthenticated) requests for data that might be handled by an application or sensitive system.

4.  Phishing remains a common way to exfiltrate target data that lies within a corporate network. Phishing can take a wide variety of forms, with more complex schemes relying on spear phishing or highly tailored campaigns designed to take the credentials of a target with specific credentials. Hackers don't need to target someone who has the exact credentials they need to exfiltrate data, however. Once an initial target is compromised, hackers can move laterally throughout an organization until they stumble across a vulnerability that lets them gain further access or possibly another person who they can phish. Subsequent phishing attempts might be even more powerful as hackers can leverage internal information or compromised accounts to convincingly approach a second or even third target in a phishing attempt.

### 4 ways to protect PII and other sensitive data

We want to wrap up this guide by discussing some important technologies you can use to protect PII and other types of sensitive data. Below is a non-exhaustive list of the technologies that can prevent unauthorized access to your systems and data.

1.  **Encryption**. Encryption is defined as the conversion of something to code or symbols so that its contents cannot be understood if intercepted. When sending a confidential email, you should use a program to encrypt its content. Additionally, encrypting data at rest is an important best practice for securing data at rest in databases and other sensitive systems. 

2.  **Identity and access management (IAM).** As the number of services and systems required by organizations and their employees increases, the value of identity and access management (IAM) has increased. IAM allows organizations to manage the accounts and permissions of employees at scale. With IAM, companies can enforce two factor authentication or multi-factor authentication and rapidly provision and deprovision accounts with ease. We talk in detail about IAM and why it matters in our [security playbook](https://nightfall.ai/download-2021-security-playbook-remote-first-orgs/).

3.  **Endpoint management.** Endpoint managers provide a wide variety of functions, from managing device firmware and monitoring hardware activity to providing on-device security in the form of antivirus protection. We also talk in greater detail about endpoint management in our security playbook.

4.  **Data Loss Prevention.** Data loss prevention, which we mentioned earlier in this guide, is a way to monitor the data flowing in and out of your environments. In our security playbook we make a case for leveraging cloud native data loss prevention to detect and classify business critical data in your SaaS applications and cloud infrastructure. Nightfall specifically uses machine learning detectors that are capable of object character recognition (OCR) and natural language processing (NLP) to classify strings, files and images that contain PII, PHI and a wide variety of sensitive data. From there we implement rules that let you monitor who has access to this data and control when to redact or remove it. Such a technology is invaluable for ensuring your data can live in the cloud safely.

### Adopt a data-centric security posture to keep PII top of mind

As the various compliance regimes across the world mature, and as digital transformation expands, the way organizations will have to think about security must change. Ultimately, this guide is designed to highlight the areas where security and compliance meet by illustrating a data-centric approach to information security. This essentially means prioritizing security by taking inventory of the types of data you're trying to secure. This requires visibility into where your data is, how it's stored, and who has access to it as well as understanding the threats facing your data. We hope this guide provides a starting point for you to begin thinking about the resources that can help you secure your data.

[Back to top](#pii-leak-prevention-guide)

## About Nightfall

[Nightfall](https://www.nightfall.ai) is the industry's first cloud-native DLP platform that discovers, classifies, and protects data via machine learning. Nightfall is designed to work with popular SaaS applications like [Slack](https://nightfall.ai/solutions/product/slack), [Google Drive](https://nightfall.ai/solutions/product/google-drive), [GitHub,](https://nightfall.ai/solutions/product/github) [Confluence](https://nightfall.ai/solutions/product/confluence), [Jira,](https://nightfall.ai/solutions/product/jira) and many more via our [Developer Platform](https://nightfall.ai/developer-platform). If you have any questions about Nightfall or our guide feel free to contact us at [support@nightfall.ai](mailto:support@nightfall.ai).
