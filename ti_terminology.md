## Terms
<a href="ti">Back</a>
<p>A place to record some common terms in no particular order.</p>
<p><strong>Intelligence</strong> is a broad term that refers to the gathering and analysis of information to inform decision-making. It can include a wide range of activities, such as collecting and analyzing data about geopolitical risks, economic trends, or military activities.

<p><strong>Threat Intelligence (TI)</strong> is a subset of intelligence that focuses on gathering and analyzing information about potential threats to an organization's security. This can include information about cyber threats, physical threats, geopolitical risks, and other types of risks. The goal of TI is to provide insights into the nature and scope of potential threats, and to inform security measures and incident response.</p>

<p><strong>Cyber Threat Intelligence (CTI)</strong> is a subset of TI that focuses on the collection, analysis, and dissemination of information about cyber threats. This can include information about malware, vulnerabilities, threat actors, attack techniques, and other aspects of the cyber threat landscape.</p>

<p><strong>Threat Hunting (TH)</strong> is a proactive approach to cybersecurity that involves actively searching for signs of potential threats or malicious activity within an organization's network or systems. It involves using advanced analytics and other tools to identify anomalous behavior, suspicious patterns, and other indicators that may suggest a security breach or attack. The goal of TH is to detect and respond to threats before they can cause significant harm.</p>

<p><strong>Threat Modeling</strong> is a process used in cybersecurity to identify and evaluate potential security threats to a system or application. It is a proactive approach that helps organizations to understand their security risks and to implement measures to address those risks before they can be exploited.</p>

<p><strong>Incident Response (IR)</strong> is the process of detecting, investigating, and responding to security incidents in an organization's information technology (IT) environment. The goal of incident response is to minimize the damage caused by a security incident and to restore normal operations as quickly as possible.</p>

<p><strong>Incidents</strong> can be any event that poses a threat to an organization's security, such as a cyber attack, data breach, or physical security breach. Incident response involves a coordinated set of procedures and practices that are designed to respond to a security incident and mitigate its impact.</p>

<p><strong>Indicator of Compromise (IOC)</strong> is a piece of information that indicates a potential security threat. IOCs can take many forms, including network traffic, file hashes, IP addresses, domain names, or email addresses. They are often used in TI to help identify and respond to security incidents.</p>

<ul>
    <li><strong>Static IOCs</strong> are pieces of information that are not expected to change, such as a file hash or a domain name.</li>
    <li><strong>Dynamic IOCs</strong> are pieces of information that may change over time, such as an IP address or a user agent string.</li>
</ul>

<p><strong>Threat Actor</strong> A threat actor is an individual or group that is responsible for carrying out a security threat, such as a cyber attack or physical security breach. Threat actors can range from amateur hackers to nation-state actors and can use a variety of tools, tactics, and techniques to carry out their attacks.</p>

<p><strong>Advanced Persistent Threats (APTs)</strong> refers to a specific type of long-term, targeted cyber attack that is typically carried out by a well-funded and highly skilled threat actor. APTs are often characterized by their persistence, in that they may spend months or even years conducting reconnaissance and gathering information before carrying out an attack.</p>

<p><strong>Nation-state actors</strong> are a specific type of threat actor that refers to a government or government-sponsored entity that carries out cyber attacks for political, economic, or military purposes. Nation-state actors are often well-funded and highly skilled, and they may have access to sophisticated tools and techniques that are not available to other types of threat actors. Because of their resources and capabilities, nation-state actors can be extremely difficult to detect and defend against. They may use advanced tactics such as custom malware, zero-day vulnerabilities, and social engineering to carry out their attacks, and they may be able to evade traditional security controls.</p>

<p><strong>Tactics, Techniques, Procedures (TTPs)</strong> it is a framework used in the field of cybersecurity to describe the methods used by threat actors to carry out attacks. TTPs are used to provide insight into how an attack was carried out and what steps were taken to compromise a system. TTPs are not static and can evolve over time. Threat actors may modify their tactics and procedures in response to new security measures, making it important for organizations to stay up-to-date on the latest threat intelligence and best practices for information security.</p>

<ul>
    <li><strong>Tactics</strong> refer to the overall objectives or goals of an attack. For example, an attacker may use a social engineering tactic to trick a user into revealing their login credentials.</li>
    <li><strong>Techniques</strong> refer to the specific methods used to carry out an attack. For example, a common technique used by attackers is the use of malware to gain access to a system.</li>
    <li><strong>Procedures</strong> refer to the step-by-step processes used by attackers to execute their attack. For example, an attacker may use a specific procedure to deliver malware to a system, such as using a phishing email to trick a user into downloading a malicious attachment.</li>
</ul>

<p><strong>MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge)</strong> is a framework that provides a structured approach for understanding and categorizing the tactics, techniques, and procedures (TTPs) used by threat actors in cyber attacks. This framework is widely used in the cybersecurity industry as a reference for understanding and describing cyber attacks. It is used by threat intelligence analysts to identify potential attacks and by security teams to design and implement effective defenses. One of the key benefits of the <a href="https://attack.mitre.org/" target="_blank">MITRE ATT&CK</a> framework is that it provides a common language for describing cyber attacks, which can help to improve collaboration and information sharing between different organizations.</p>

<p><strong>Living off the Land Binaries (LOLBins)</strong> are legitimate executables or scripts that are present on most Windows systems and can be used by attackers to carry out malicious activities. LOLBins are often used as part of a tactic known as "fileless malware," which involves running malicious code directly in memory, rather than writing files to disk. Attackers use LOLBins to evade detection by traditional security tools, since the legitimate executables and scripts used in LOLBin attacks are often whitelisted or deemed as "safe" by security software.</p>

<ul>
    <li><a href="https://lolbas-project.github.io/" target="_blank">LOLBAS Project</a> - The goal of the LOLBAS project is to document every binary, script, and library that can be used for Living Off The Land techniques.</li>
    <li><a href="https://gtfobins.github.io/" target="_blank">GTFOBins</a> - UNIX version of the LOLBAS project. Includes a curated list of Unix binaries that can be used to bypass local security restrictions in misconfigured systems.</li>
    <li><a href="https://www.loldrivers.io/" target="_blank">LOLDrivers</a> - a consolidated resource of driver-related security risks.</li>
</ul>