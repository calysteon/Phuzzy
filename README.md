# Phuzzy
Phuzzy: Fuzzing Phishing Redirects via User-Agent Mapping

## Abstract
> The goal of this project is to fuzz suspected phishing links for malware enumeration. As malicious actors get more creative at targeted malware delivery to increase efficiency and reduce exposure what can we do to better identify these malicious exploits? This project will fuzz and log the results for further analysis.

## Obfscation Techniques
> Through our own analysis we've discovered that malicious actors have become more sophisticated in targeting specific environments like mobile devices. They also employ layered redirects using various techniques to make it less likely to be detected by cybersecurity tools, in some instances even returning 404 errors. 

## Priorities
We understand that bad actors can make these systems as complex as possible, like single use URLs. This would make enumeration impossible if once a URL is accessed it can't be used again. While this approach is highly unlikely as it would reduce the effectiveness of phishing campaigns, other rate limiting techniques may be employed. The amount of effort employed in protecting exploit payloads is likely directly proportional to the value of the exploit. Therefore, our initial approach is to employ user-agent strings that would be expected by the attacker, and likely supplied by the victim first. We also don't want to create too much noise by submitting hundreds a http requests simultaneously so we'll spread them out over time and employ techniques to obfuscate our activity.

## Data Sources
We managed to scrape a significant amount of user-agent strings from the folks at [UserAgentString.com](https://useragentstring.com/). This yeilded some interesting results that may cause us to pursue multiple areas for analysis. Combined with the data from our own user-agent harvester we are interested in seeing if web-crawlers are specifically targeted.
