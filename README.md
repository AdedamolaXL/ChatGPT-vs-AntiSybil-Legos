# ChatGPT-vs-AntiSybil-Legos
An analysis of existing anti sybil legos within the Gitcoin protocol against malicious use of AI algorithims like ChatGPT

## PROLOGUE
The year is 2023, AI is blowing up, important stakeholders are concerned about its malicious use and how it affects our reality going forward. 
This paper for the Open Data Community is an exercise in that direction; an evaluation of the existing Anti Sybil Legos within the Gitcoin protocol and how well they can stand up to malicious AI incursions from algorithimc chatbots like the popular ChatGPT.

To start with, Sybil attacks are a type of attack where a single entity creates multiple fake identities or nodes in a network to gain control or influence over the system. Such attacks are typically considered fraudulent and can undermine the integrity, security, and fairness of blockchain networks and other online systems. 

For Gitcoin a decentralized protocol that aims to incentivize and support open source software development. One of its most important services is the ***Grant Program*** which provides funding to well-deserving projects. Sybils on their own part, tend to subvert this grant process by skweing the allocated funds in favour of some specific user or project, rather than efficiently distributing funds to genuine public goods.

Gitcoin's current defense system against Sybil attacks, is a set of modular tools also known as Legos. Legos are a set of algorithims applied to user data and existing disputes to detect sybil-like activity. Legos also provide important insights which serve as a sort of metric benchmark for judging and evaluating future sybil activity on the protocol. 

There are currently over 20 Legos within the Gitcoin system fighting sybil attacks, some of them more effective than the other, most of them are used in conjunction with each other due to the composable nature of the Legos themselves. For the purpose of this paper, each Lego will be treatred individually and a verdict given at the end showing their **vulnerability score**.


## LEGOIC EVALUATION

### 1. Address Correlation Lego

**How it works:** The "address correlation Lego" is a pattern-identification Lego that is intended to be used against previously known sybil patterns that will be stored in a readable format (currently using a pandas dataframe). Its purpose is to judge the correlation between the activities of an address and those of sybil addresses using the Spearman's rank correlation coefficient.

**How it can be exploited:**
  * Limited detection capabilities: This Lego relies solely on previously known sybil patterns stored in a readable format, which may not capture all possible patterns or new and evolving sybil techniques used by malicious chatbots. Malicious use of chatbots like ChatGPT can potentially exploit this by employing novel or sophisticated sybil techniques that are not yet known or detected by the protocol.
  
  * Lack of scalability: This Lego reliance on a pandas dataframe, may not be scalable or efficient in handling large amounts of data. This can potentially limit the protocol's ability to process and analyze data in real-time, especially in a high-transaction environment. One can exploit this particular vulnerability by overwhelming the system with a large number of transactions or activities to evade detection.
 
 * False positives or false negatives: The accuracy of pattern identification using Spearman's rank correlation coefficient is not 100% accurate. A malicious use of ChatGPT can exploit this in two ways by either evading detection generating false negatives or triggering false positives that result in legitimate addresses being wrongly flagged. This messes with the grant system.

**Vulnerability Score:** 5.25/10


## 2. FLAGGED ACTIVITY

**How it works:** Returns whether address is in close association with addresses flagged as phishing/scam on Etherscan (send or receive event; last 365 days).

**How it can be exploited:** 
 * Lack of real-time data: This Lego relies on data from Etherscan, which may not be real-time or up-to-date. A malicious use of ChatGPT can exploit this by performing malicious activities that are not yet flagged on Etherscan, or by using addresses that have not yet been associated with phishing/scam events.
 
 * False positives or false negatives: The accuracy of the phishing/scam flagging on Etherscan may not be 100% accurate. There may be false positives where legitimate addresses are flagged as phishing/scam, or false negatives where malicious addresses are not flagged. Malicious chatbot can as well exploit this by either evading detection or triggering false positives that result in legitimate addresses being wrongly flagged.
 
 * Limited scope of detection: The Lego may only consider send or receive events within the last 365 days, which may not capture all possible phishing/scam activities that could have occurred beyond that timeframe. An exploit can maneuver this loophole by using addresses that have been involved in phishing/scam activities prior to the last 365 days.

**Vulnerability Score:** 5.75/10


## 3. SCRIPT CALL TO API

**How it works:** Imitate Bankless' use of "bot-label" for any python, curl, etc. direct-access to Passport API

**How it can be exploited:* 

 * "Bot-label" manipulation: A malicious use of ChatGPT can manipulate the "bot-label" or forge it to gain unauthorized access to the Passport API. This allows the user to perform actions that are not allowed or intended, leading to potential misuse or abuse of the system.
 
 * Lack of multifactor authentication: The reliance solely on the "bot-label" without additional authentication mechanisms, such as multifactor authentication or token-based authentication, also increases the vulnerability of the protocol to malicious chatbots.

**Vulnerability Score:** 5.75/10


## 4. ON-TREND/OFF-TREND

**How it works:** Determines whether user donation array is within-range for statistical averages of the community

**How it can be exploited:** 

 *  Manipulation of donation array: Malicious chatbots can potentially manipulate the donation array to fall within the statistical averages of the community, even if the donations are not genuine or do not reflect the true intent of the user. This can lead to inaccurate results and manipulation of the protocol.

 * Automated donations: Malicious chatbots can make automated donations to manipulate the donation array and artificially influence the statistical averages of the community. This could lead to unfair results and manipulation of the protocol.

 * False positives/negatives: The Lego may generate false positives or false negatives in determining whether the user's donation array falls within the statistical averages of the community. Malicious chatbots could potentially exploit these false results to gain an unfair advantage or to bypass detection. 

**Vulnerability Score:** 5.75/10


## 5. UPALA

**How it works:** Upala is a decentralized digital identity. The protocol generates human uniqueness score for users. The score is measured in dollars. Each account score is determined by market. Incentives ensure that the score equals the costs of forging the account. The score directly reflects how valuable that identity is to the user and creates an entirely new way to measure reputability in the virtual and real world.

**How it can be exploited:** 

 * Fake identity creation: A malicious user of ChatGPT can potentially generate fake identities for the Upala protocol, thereby undermining the integrity of the social identity verification process.

 * Manipulation of social identity data: One can also manipulate social identity data or forge proof of identity, leading to inaccurate or fraudulent verification results.

 * Collusion with real users: A malicious user of ChatGPT can also collude with real users to fraudulently verify fake identities, leading to unfair distribution of trust scores and reputation within the Upala protocol.

**Vulnerability Score:** 6.25/10


## 6. POAP - Proof Of Attendance Protocol

**How it works:** The Proof of Attendance Protocol turns events or hackathons into collectibles. Using blockchain technology, POAP tokenizes your proof of participation, so they can be used as DIDs (decentralized Identifiers).

**How it can be exploited:** 

 * Fake event submissions: Malicious chatbots can potentially create fake events or hackathons and generate fake proof of attendance to collect POAP tokens, thereby undermining the integrity of the protocol.

 * Sybil attacks: Malicious chatbots can create multiple fake identities and participate in events or hackathons, thereby gaining multiple POAP tokens and manipulating the rewards or incentives associated with the protocol.

 * Manipulation of attendance data: Malicious chatbots can manipulate attendance data or forge proof of attendance to earn POAP tokens without actually participating in the events or hackathons, leading to inaccurate or fraudulent token distribution.

 * Collusion with real users: Malicious chatbots can collude with real users to fraudulently earn POAP tokens by providing fake proof of attendance or manipulating event data, leading to unfair distribution of tokens.

**Vulnerability Score:** 5.75/10


## 7. FUNDING WALLET IS UNIQUE

**How it works:** Returns Boolean for uniqueness of funding wallet.

**How it can be exploited:** 

 * Lack of multi-factor authentication: The Lego appears to rely solely on checking if a funding wallet is unique, which may not be a robust security measure. Malicious chatbots may be able to create multiple funding wallets or spoof unique wallet addresses, thus potentially evading detection.

 * Lack of comprehensive detection techniques: The Lego seems to rely solely on checking the uniqueness of the funding wallet, without considering other potential techniques that malicious chatbots may use, such as IP address manipulation, transaction amounts, network behavior, or transaction timing. This may make the protocol vulnerable to more sophisticated attacks that do not rely solely on wallet address uniqueness.

 * Lack of real-time monitoring: The Lego may not have real-time monitoring capabilities, and the uniqueness of the funding wallet may be checked based on historical data, which may not be updated in real-time. This could potentially allow malicious chatbots to create or manipulate funding wallets in real-time and evade detection based on this measure.

 * Lack of behavioral analysis: The Lego does not seem to consider behavioral analysis of the funding wallet, such as transaction patterns or transaction destinations, which could potentially be used to detect suspicious or malicious activity. This may make the protocol vulnerable to malicious use of ChatGPT togenerate legitimate-looking transactions procedures or carry out attacks using subtle transaction patterns.

**Vulnerability Score:** 6.25/10


## 8. SLAYSYBIL 

**How it works:** Tracking bulk transfers and donations to detect sybils with observing sequential behaviour pattern and asset-transfer graph. 

**How it can be exploited:** 

 * Reliance on sequential behavior patterns: The Lego relies on detecting sequential behavior patterns, which may be vulnerable to manipulation by sophisticated malicious chatbots. Advanced chatbots may be able to mimic legitimate sequential behavior patterns to evade detection, thus potentially bypassing this measure.

 * Reliance on asset-transfer graph: The Lego also relies on observing the asset-transfer graph to detect Sybil attacks. However, this approach may be susceptible to manipulation by malicious chatbots that can create fake asset-transfer graph patterns or mimic legitimate asset-transfer behavior, thus potentially evading detection.

 * Lack of real-time detection: The Lego may not have real-time monitoring capabilities, and the sequential behavior patterns and asset-transfer graph may be analyzed based on historical data, which may not be updated in real-time. This could potentially allow malicious chatbots to carry out attacks in real-time and evade detection based on these measures.

 * Lack of comprehensive detection techniques: This relies solely on sequential behavior patterns and asset-transfer graph observation, without considering other potential techniques that malicious chatbots may use, such as transaction amounts, network behavior, or transaction timing. This may make the protocol vulnerable to more sophisticated attacks that do not rely solely on sequential behavior patterns or asset-transfer graph observations.

**Vulnerability Score:** 6/10


## 9. ONCHAIN FOOTPRINT LEGO

**How it works:** The TDD (Transaction Date Mean Difference) metric is utilized by this Lego, and it is computed by subtracting each transaction date from the following one to obtain the difference, then dividing by the total number of transactions (i.e., the mean difference or average difference).

**How it can be exploited:** 

 * Reliance on transaction date mean difference: The Lego relies on the "transaction date mean difference" as a security measure. However, this approach may have some potential vulnerabilities. For instance, a sophisticated malicious chatbot could potentially manipulate the transaction dates to create a pattern that mimics legitimate transaction behavior, thus evading detection based on this measure.

 * Lack of real-time detection: The Lego may not have real-time monitoring capabilities, and the "transaction date mean difference" may be calculated based on historical transaction data, which may not be updated in real-time. This could potentially allow malicious chatbots to carry out attacks in real-time and evade detection based on this measure.

 * Lack of comprehensive detection techniques: The protocol seems to rely solely on the "transaction date mean difference" to counter Sybil attacks, without considering other potential techniques that malicious chatbots may use, such as transaction patterns, transaction amounts, or network behavior. This may make the protocol vulnerable to more sophisticated attacks that do not rely solely on transaction count-based security measures.

**Vulnerability Score:** 6/10


## 10. BrightID

**How it works:** BrightID is building an identity lego that allows users to prove to applications that they only exist once in any given system. It's one of the legos used in Gitcoin Passport. You can get 50% bonus matching for all your Gitcoin grants by joining BrightID and connecting it to your Gitcoin Passport. 

**How it can be exploited:** 
  
   * Validation process: Chatbots can be used to create multiple fake accounts on BrightID by simulating human-like interactions, such as submitting videos or other required information for verification. 
  
   * Collusion: These malicious chatbots can then vouch for each other, creating a network of fake accounts that creates a false sense of legitimacy which can then be used for various malicious activities, such as gaming the system for unfair advantages or manipulating the reputation score of genuine users.
   
   * Turing Test: BrightID protocol relies on users proving their uniqueness and existence through a global Turing test. While it's very hard for a chatbot to pass a Turing test, ChatGPT is quite capable of doing so under the right circumstances which indicates another vulnerability within this Lego.

**Vulnerability Score:** 6.25/10


## 11. LEVENSTEIN DISTANCE

**How it works:** Every user has a username - when they sign up to Gitcoin grants the similarity of their name can be compared against all other usernames to generate a likelihood of the username being auto-generated - evidence of a Sybil account. This Lego will be deprecated in the grants protocol because usernames will no longer be available - only Ethereum addresses, wallet IDs and grant/round nonce.

**How it can be exploited:** 

 * Sensitivity to username similarity: The Lego appears to rely on username similarity as a sole indicator of potential Sybil accounts. However, usernames can sometimes be similar among legitimate users due to various reasons, such as common names or naming conventions. This can potentially result in false positives or false negatives, as legitimate users with similar usernames may be flagged as potential Sybil accounts or actual Sybil accounts may go undetected if they use usernames that are not similar.

 * Lack of additional validation factors: The Lego does not seem to consider other validation factors beyond username similarity. Malicious actors can potentially use sophisticated techniques to create usernames that appear legitimate or avoid detection by using random or unrelated usernames.

 * Lack of contextual awareness: The Lego does not appear to consider other contextual factors, such as user behavior, transaction history, or social network analysis, which could provide additional insights into the legitimacy of an account. This could result in potential vulnerabilities as malicious actors can potentially mimic legitimate user behavior and evade detection.

 * Lack of dynamic updates: If the Lego does not have the capability to dynamically update the similarity thresholds or adapt to changing attack patterns, it may become obsolete over time, allowing malicious actors to evade detection.

 * Privacy concerns: Comparing username similarity could raise privacy concerns as it may involve collecting and analyzing user data, potentially leading to potential privacy violations if not handled properly.

**Vulnerability Score:** 7/10


## 12. ONCHAIN HISTORY

**How it works:** This Lego returns a Yes or No value if a user engaged in certain web3 activities in a specific timeframe.

**How it can be exploited:**

 * Lack of context-awareness: The Lego appears to rely solely on checking if a user has engaged in certain web3 activities within specific timeframes without considering other contextual factors. This could potentially result in false positives or false negatives, as malicious chatbots could potentially mimic legitimate user behavior within the specified timeframes or evade detection by not engaging in the expected activities.

 * Lack of behavioral analysis: The Lego does not seem to consider other potential behavioral analysis techniques beyond checking specific web3 activities within timeframes. Malicious chatbots can potentially use sophisticated techniques to hide their activities or mimic legitimate user behavior, leading to potential vulnerabilities.

 * Lack of dynamic updates: If the Lego does not have the capability to dynamically update the specific web3 activities or timeframes based on changing threats or attack patterns, it may become obsolete over time, allowing malicious chatbots to evade detection.

 * Overreliance on timeframes: The Lego's reliance on specific timeframes may not be effective in detecting sophisticated malicious chatbots that are designed to operate over extended periods of time or evade detection by varying their activity patterns.

**Vulnerability Score:** 7.25/10

## 13. MONEY MIXERS

**How it works:** Returns a Boolean if a user has interacted with known money-mixers.

**How it can be exploited:** 

 * Reliance on known money-mixers: The Lego appears to rely on a predefined list of known money-mixers to determine if a user has interacted with them. However, malicious chatbots or other types of attackers can potentially use new or previously unknown money-mixers that are not on the list, thus evading detection.

 * Lack of real-time updates: If the list of known money-mixers is not updated in real-time, the Lego may miss new or emerging money-mixers that are not on the list. Attackers can potentially take advantage of this time lag and use new or unknown money-mixers to evade detection.

 * False positives/negatives: Depending on the accuracy and comprehensiveness of the list of known money-mixers, the protocol may generate false positives or false negatives. False positives may result in legitimate users being flagged as potential malicious actors, while false negatives may result in malicious chatbots evading detection.

 * Lack of behavioral analysis: The protocol appears to rely solely on checking if a user has interacted with known money-mixers without considering other potential behavioral analysis techniques. Malicious chatbots could potentially use sophisticated techniques to hide their interactions with money-mixers or use alternative methods like to obfuscate their transactions, thus evading detection.

**Vulnerability Score:** 7.25/10


## 14. HIGH FREQUENCY TRADING

**How it works:** Returns boolean wallet activity timestamps over # of transactions

**How it can be exploited:** 

 * Over-reliance on a single indicator: The Lego appears to rely solely on the relationship between wallet activity timestamps and the number of transactions, specifically identifying high frequency trading as an indicator of bot-control or automatic wallet-vetting scripts. However, high frequency trading could also be a legitimate activity for human traders or other types of automated trading systems, leading to potential false positives or false negatives.

 * Lack of contextual analysis: The Lego does not seem to consider other contextual factors that could affect wallet activity timestamps, such as market conditions, trading strategies, or other legitimate reasons for high frequency trading. Malicious chatbots could potentially mimic legitimate trading behavior to evade detection, thus making the protocol vulnerable to false results.

 * Lack of behavioral analysis: The Lego does not seem to consider other potential behavioral analysis techniques beyond wallet activity timestamps, such as transaction patterns, transaction destinations, or other contextual factors. This may make the protocol vulnerable to malicious chatbots that can mimic legitimate transaction behavior or other activities, thus evading detection.

 * Lack of multi-factor authentication: The Lego appears to rely solely on wallet activity timestamps and the number of transactions as indicators, without considering other potential factors or implementing multi-factor authentication. Malicious chatbots could potentially find ways to circumvent or manipulate wallet activity timestamps, leading to inaccurate results and potential vulnerabilities.

**Vulnerability Score:** 6.75/10


## 15. SOCIAL PRESENCE

**How it works:** Returns Boolean if a project is within 1 standard deviation from the dynamic mean.

**How it can be exploited:** 

 * Lack of multi-factor authentication: The Lego appears to rely solely on the relationship between the number of unique donations received and the number of Twitter followers, without considering other potential factors that could affect this relationship. Malicious chatbots could potentially manipulate either the number of unique donations or the number of Twitter followers to create a false perception of legitimacy, thus evading detection.

 * Vulnerability to follower manipulation: The Lego relies on the number of Twitter followers as a key factor, which could be easily manipulated by malicious chatbots through purchasing fake followers or artificially inflating follower counts. This could lead to false results and inaccurate evaluations of legitimacy.

 * Sensitivity to standard deviation threshold: The Lego uses a standard deviation threshold to determine if a project is within an acceptable range, which may not be robust enough to accurately identify malicious chatbot activity. A small change in the standard deviation threshold could potentially lead to false positives or false negatives, resulting in inaccurate evaluations of legitimacy.

 * Lack of behavioral analysis: The Lego does not seem to consider other potential behavioral analysis techniques, such as transaction patterns, transaction destinations, or other social media activity, beyond the relationship between unique donations and Twitter followers. This may make the protocol vulnerable to malicious chatbots that can mimic legitimate transaction behavior or social media activity, thus evading detection.

**Vulnerability Score:** 5.75/10


## 16. FARMER BOOLEAN

**How it works:** Uses on-chain data to determine whether a user has >X ERC-20 tokens and an average transaction value <Y ETH)

**How it can be exploited:** 

 * Susceptibility to token manipulation: The Lego relies on on-chain data to determine if a user has a certain number of ERC-20 tokens and an average transaction value below a certain threshold. Malicious chatbots may manipulate token balances or transaction values to meet the criteria and evade detection. For example, they could artificially inflate token balances or conduct transactions with manipulated values to appear as legitimate users.

 * Lack of comprehensive detection techniques: The Lego seems to rely solely on the criteria of ERC-20 token balance and average transaction value, without considering other potential techniques that malicious chatbots may use, such as IP address manipulation, network behavior, transaction timing, or transaction patterns. This may make the protocol vulnerable to more sophisticated attacks that do not rely solely on meeting the criteria of ERC-20 token balance and transaction value.

 * Potential false positives/negatives: The Lego may generate false positives or false negatives due to the reliance on specific thresholds for ERC-20 token balance and average transaction value. Legitimate users who do not meet these criteria but are not malicious chatbots may be flagged as false positives, while malicious chatbots that can manipulate token balances or transaction values may evade detection as false negatives.

 * Lack of behavioral analysis: The Lego does not seem to consider behavioral analysis of the user beyond token balances and transaction values, such as transaction patterns, transaction destinations, or other on-chain activities. This may make the protocol vulnerable to malicious chatbots that can mimic legitimate transaction behavior or carry out attacks using subtle transaction patterns or destinations.

**Vulnerability Score:** 6/10


## 17. UBI - Universal Basic Income

**How it works:** Universal basic income (UBI) aims to address economic inequality and provide security through streamed cash to every human on Earth. It is built on top of Ethereum and the Proof of Humanity protocol. Every human that gets verified by submitting a video of themseleves.

**How it can be exploited:** 

 * Collusion with real users: A major vulnerability is the potential for a ChatGPT user to collude with a large number of real humans in order to increase its chances of receiving UBI. This could be done by creating a network of bots that interact with real human accomplices in order to earnb the bot's eligibility for UBI.
 
 * AI Deepfakes: Another possible vulnerability is the possibility of a chatbot being able to mimic a human in the video verification process. With advances in AI and deepfakes, it may become increasingly difficult to distinguish between a real human and a bot posing as a human in a video submission. This could potentially allow for bots to fraudulently receive UBI. 

**Vulnerability Score:** 4/10


## 18. Proof of Humanity

**How it works:** Humans who wish to be included in the registry submit information about themselves serving for verification. Then you can vouch for others and challenge suspicious users just like Kleros.

**How it can be exploited:** 

   * AI Deepfakes: Chatbots can potentially attempt to bypass the protocol by using pre-recorded videos or deepfake technology to create fake video submissions that appear to be from genuine users. This could pose a potential vulnerability to the protocol if not properly addressed.

**Vulnerability Score:** 2.25/10


*For UBI, BrightID and Proof of Humanity, considering the current limitations of chatbots versus Turing tests and the video submission requirement, the vulnerability of the protocol to malicious chatbots being able to pass as humans while evidently possible is relatively low.* 
 
 
 ## 19. IDENA - PROOF OF PERSON BLOCKCHAIN
 
**How it works:** The Idena blockchain is driven by Proof-of-Person consensus with every node linked to a cryptoidentity, one person with equal voting power. It suggests a novel way to formalize people on the Internet: Idena proves the humanness and uniqueness of its participants without collecting personally identifiable information by running a Turing test at the same time globally.
 
**Why it is so hard to be exploit:**
 
  * Turing tests: ChatGPT has recently passed the Turing test, but chatbots being automated conversational agents, are still slightly defiecient in human characteristics neccessary for maintaining human-like interactions. While it's evidently a potential red flag, the chances of a chatbot bypassing Idena's protocol is currently low.
 
 * Proof of consensus - One of the plus points of Idena's blockchain protocol is the multifactor authentication point. This means that even if a malicious chatbot manages to pass Turing tests on a few nodes, it would need to pass the consensus of all other nodes in the network to be verified. This adds an additional layer of security!

**Vulnerability Score:** 2/10


### LEGO RANKING

The average vulnerability score was evaluated over four major factors:
 * False positives/negatives - which refers to the vulnerability of the lego to returning false positive/negative values when evaluating user accounts for sybil behaviour.
 * Validation factor - this generally refers to the presence/absence of a multifactor authentication factor system within the lego i.e does the lego have the capacity to evaluate user accounts using more than one parameter ?
 * Contextual awareness - this refers to the awareness of other behavioural factors of user accounts which the lego should take into consideration when evaluating sybil behaviour
 * Real-time/Dynamic updates - this refers to the capacity of the lego do detect sybil behaviour in real time or to adapt to new behaviours in sybil attacks over a period of time.

![chart(2)](https://user-images.githubusercontent.com/66562380/236787176-2ad5fb6b-0381-49ff-bf85-2f9dc6b1dcda.png)


