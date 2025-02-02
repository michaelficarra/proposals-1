# W3C Anti-Fraud Community Group - Use Cases & Threat Models

Our goal is to capture a non-exhaustive, but highly diverse list of fraud and abuse that has at least partial reliance on online workflows/technologies that are in the scope of the W3C Anti-Fraud Community Group (CG). The CG will use this to help focus future discussions and proposals, but just because a certain abuse tactic or fraud method is not explicitly included does not mean that it is out of scope for the CG.


Use Cases
* Account Creation
* Account Takeover
  * Credential Cracking
  * Credential Stuffing
  * Phishing
  * Phone Takeover (e.g. phone porting or SIM Swap)
  * Token Theft
* Invalid Traffic (IVT) in Advertising
* Ecommerce Fraud
  * Scalping
  * Sniping
* Payment Fraud
  * Carding
  * Card Cracking
  * Cashing Out
  * Check Kiting
  * Promotion Abuse
* Sensitive Data Scraping
  * Scraping
* Online Spam & Fake Engagements
  * Skewing
  * Spamming
* Denial of Service
  * Denial of Service
* Theft of Intellectual Property
* Unauthorized access





# Use Cases


## Account Creation

Account authentication and account creation workflows are abused from bad actors who manually or programmatically attempt to create accounts that they can subsequently use to abuse a platform.

Bad actors misrepresent their identities during the account creation process. There are three main approaches, known in the fraud industry as:



* **Identity theft** - wherein a bad actor claims to be somebody that they are not, using a legitimate identity that was previously compromised
* **Synthetic identity** - wherein a bad actor uses a combination of fake and real identity attributes to create a new ‘synthetic’ identity that can be partially verified, thus bypassing verification controls
* **1st party fraud** - wherein a person submits their own data, perhaps with minor alterations and then subsequently claims to be a victim of identity theft.


## Account Takeover

Bad actors use a variety of techniques to obtain access to an account. Once an account is compromised, user credentials or profile data (address, email, phone, etc) are often modified to elongate the window of opportunity for abuse. Changes to account profile attributes or passwords are often the first sign that an account has been hijacked. From there, bad actors can instigate all sorts of financial crimes, which are naturally specific to the compromised institutions. This includes payments fraud, crypto-jacking, online ecommerce, benefits fraud, and compromised lines of credit.


### Credential Cracking

See [OAT-007 Credential Cracking](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-007_Credential_Cracking.html).


### Credential Stuffing

See [OAT-008 Credential Stuffing](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-008_Credential_Stuffing.html).


### Phishing

Phishing is a type of social engineering where an attacker sends a fraudulent (e.g., spoofed, fake, or otherwise deceptive) message designed to trick a person into revealing sensitive information to the attacker or to deploy malicious software on the victim's infrastructure like ransomware ([https://en.wikipedia.org/wiki/Phishing](https://en.wikipedia.org/wiki/Phishing))


### Phone Takeover (e.g. phone porting or SIM Swap)

Bad actors bypass identity verification controls at mobile carriers to temporarily take control of a telephone number. Subsequently, they either port the telephone number to a new carrier and device that they control, or they initiate a SIM swap, wherein the target’s phone number is assigned to a new device which is also on the carrier’s network. These attacks can be initiated online, in store, over the phone. Telco’s typically ask for additional information to validate the abuser’s identity, however their controls may be inadequate. Other less common methods include call forwarding, voicemail compromise, compromise of a phone carrier website (to access text messages and selectively forward calls), and malware.

Once a phone number is compromised, MFA can be bypassed, often resulting in huge monetary losses. This is the primary attack vector that we see in crypto-jacking, but it is also a common pattern in payments/account transfer fraud. 


### Token Theft

Session credentials for authenticated users are traditionally stored as cookies, which are trivially extracted by malware running with user privileges. Services traditionally defend against this by associating certain invariant client properties (screen size, webGL renderer, etc) with a user’s cookie, and rejecting the session credential (forcing the use to re-authenticate) if it appears that the cookie is used on a new device.


## Invalid Traffic (IVT) in Advertising

Invalid traffic is any activity that doesn't come from a real user with genuine interest. It can include accidental clicks caused by intrusive ad implementations, fraudulent clicking by competing advertisers, advertising botnets and more (per [Google’s](https://www.google.com/ads/adtrafficquality/invalid-activity) definition).

See [TAG IVT Taxonomy](https://f.hubspotusercontent40.net/hubfs/2848641/Invalid%20Traffic%20Taxonomy%20(IVT)/IVT%20Taxonomy%20v2.0.pdf) and [Invalid Traffic Detection and Filtration Standards Addendum](http://mediaratingcouncil.org/IVT%20Addendum%20Update%20062520.pdf) for more details in the underlying threat models in advertising.

## Ecommerce Fraud

Automation is used to abuse the purchase workflows of digital or physical goods. Bad actors are able to complete purchases faster (e.g. sneaker bots, auction sniping) and at larger quantities compared to other buyers.


### Scalping

See [OAT-005 Scalping](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-005_Scalping.html).


### Sniping

See [OAT-013 Sniping](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-013_Sniping.html).


## Payment Fraud

Payment workflows are abused using automated or manual techniques in order to buy merchandise using stolen payment cards, validate stolen payment cards, brute force and crack payment cards, or abuse promotions.


### Carding

See [OAT-001 Carding](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-001_Carding.html).


### Card Cracking

See [OAT-010 Card Cracking](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-010_Card_Cracking.html).


### Cashing Out

Fraud in eCommerce channels typically takes advantage of compromised credit cards, or compromised accounts linked to credit cards. Fraudsters will purchase high value items such as laptops with the intent of reselling them. As a result, merchants incur ‘doubled’ losses - the loss of the merchandise and then another loss due to a payment chargeback. In other cases, fraudsters utilize these schemes to purchase gift cards which are then resold on various marketplaces. Gift cards are often employed as a money laundering tactic, and as means of converting stolen credit cards to cash.

Fraudsters frequently employ remailer services in order to cover their tracks. Remailers are innocent 3rd parties who provide an address for shipping and then send the goods on to another location.

Also see [OAT-012 Cashing Out](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-012_Cashing_Out.html).


### Check Kiting

Kiting is commonly defined as intentionally writing a check for a value greater than the account balance from an account in one bank, then writing a check from another account in another bank, also with non-sufficient funds, with the second check serving to cover the non-existent funds from the first account. The purpose of check kiting is to falsely inflate the balance of a checking account in order to allow written checks to clear that would otherwise bounce. If the account is not planned to be replenished, then the fraud is colloquially known as paper hanging.” - Wikipedia

Check kiting and related forms of fraud have not historically relied on digital channels. However, with the emergence of online-only neobanks and other fintechs, this practice has become endemic to digital banking. The problem is further exacerbated when fintechs offer incentives, like accelerated deposit schedules, in order to get a competitive advantage. The problem is made worse because online banks like Chime often make debit cards available in digital channels. This means that anonymous users can load up account balances on these cards and then turn around and abuse them at merchants. 


### Promotion Abuse

Brands will frequently offer promotions to accelerate adoption by new users. Once fraud rings realize that they can successfully exploit sign up flows at scale, they begin to target these organizations with high volumes of new accounts, in order to reap promotional benefits.

Paypal was recently the victim of such an attack. Paypal announced that 4.5 million fake accounts were created to take advantage of a promotion where new users received a free balance of $5 or $10. Paypal announced this in the Q4 2021 earnings call. This news, along with slow growth in legitimate users, was followed by a 25% drop in stock price.


## Sensitive Data Scraping

Sensitive data (e.g. user profiles, product prices, user generated content) that is available in the public domain (account authentication may or may not be required) is programmatically exfiltrated at scale for use elsewhere.


### Scraping

See [OAT-011 Scraping](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-011_Scraping.html).


## Online Spam & Fake Engagements

Mass spammy user generated content (videos, reviews, comments, likes, audio/video playback). Bypassing creator's restrictions on accessing content. A particular subclass is fake engagement where the attacker wishes to inflate (or deflate) the listing’s reputation or ranking via automated, inorganic engagement with the page.  Engagements may be active (e.g. A click) or passive (e.g. an impression, or time spent on site). In some cases, filtration decisions need to be made in real-time (e.g. to report live-stream concurrent viewership).

Fake engagements may be _simulated _(i.e. generated by something other than the claimed platform), _automated_ or _hijacked _(i.e. generated on the claimed platform, but without genuine user intent), or _incentivized _(i.e. generated by a human in exchange for an undisclosed incentive).


### Skewing

See [OAT-016 Skewing](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-016_Skewing.html).


### Spamming

See [OAT-017 Spamming](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-017_Spamming.html).


## Denial of Service

Unwanted traffic sent for the purpose of making a service unavailable for legitimate users.


### Denial of Service

See [OAT-015 Denial of Service](https://owasp.org/www-project-automated-threats-to-web-applications/assets/oats/EN/OAT-015_Denial_of_Service).


## Theft of Intellectual Property

Attackers are sometimes after the developer’s intellectual property. It may materialize as scraping the developer’s database (product catalog, map tiles, search results), or re-selling the service under a different brand (e.g. video stream pulled into a foreign player).


## Unauthorized access

Attackers seeking private data (e.g. bearer tokens, passwords, form entries, emails) belonging to a user will attempt to compromise the system holding this data. In addition to the mechanisms listed in the “account takeover” category, this may be possible through malware or exploitation of security bugs. 


# References
* [OWASP automated threats](https://owasp.org/www-project-automated-threats-to-web-applications/)
* [TAG IVT Taxonomy](https://f.hubspotusercontent40.net/hubfs/2848641/Invalid%20Traffic%20Taxonomy%20(IVT)/IVT%20Taxonomy%20v2.0.pdf)


# Glossary
* **Manual fraud** - Fraud executed manually by a human without the use of software, scripts, or other tools that automate the process.
* **Remailers** - An anonymous remailer is a server that receives messages with embedded instructions on where to send them next, and that forwards them without revealing where they originally came from.
