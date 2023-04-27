# ChatGPT-vs-AntiSybil-Legos
An analysis of existing anti sybil legos within the Gitcoin protocol against malicious use of AI algorithims like ChatGPT

## 1. Address Correlation Lego

How it works: The "address correlation Lego" is a pattern-identification Lego that is intended to be used against previously known sybil patterns that will be stored in a readable format (currently using a pandas dataframe). Its purpose is to judge the correlation between the activities of an address and those of sybil addresses using the Spearman's rank correlation coefficient.

How it can be exploited:
  * Limited detection capabilities: The protocol relies solely on previously known sybil patterns stored in a readable format, which may not capture all possible patterns or new and evolving sybil techniques used by malicious chatbots. Malicious use of chatbots like ChatGPT can potentially exploit this by employing novel or sophisticated sybil techniques that are not yet known or detected by the protocol.
  *Vulnerability Score*: 7/10
 
