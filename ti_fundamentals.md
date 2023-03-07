## Threat Intelligence Fundamentals
<a href="ti">Back</a>
<h3>Identifying Intelligence Requirements (IR)</h3>
<p>The first stage in the intelligence cycle is identifying the information that the decision makers need. The following example questions can help as a starting pointing when you're trying to identify the IR of an organization</p>
<ul>
    <li>What's the mission of my organization?</li>
    <li>What threat actors are interested in my organization's industry?</li>
    <li>What threat actors are known for targeting my area of operation?</li>
    <li>What threat actors could target my organization in order to reach another company we supply a server for?</li>
    <li>Has my organization been targeted previously? If so, what type of threat actor did it? What were its motivations?</li>
    <li>What asset does my organization need to protect?</li>
    <li>What type of exploits should my organization be looking out for?</li>
</ul>
<h3>Collection Management Framework (CMF)</h3>
<p>Once we have identified the intelligence requirements, we can begin collecting the raw data we need to fulfill them. There are two types of sources we can reference: internal sources (networks and endpoints), and external sources (blogs, threat intel feeds, reports, databases, etc.).</p>
<p>Using a collection management framework can aid with this process. Using a CMF allows you to identify data sources and track the info you are gathering for each.</p>
<ul>
<li><a href="https://www.dragos.com/wp-content/uploads/CMF_For_ICS.pdf" target="_blank">CMF example</a> - Dragos</li>
<li><a href="https://www.dragos.com/wp-content/uploads/CMF_For_ICS.pdf" target="_blank">CMIF example</a> - Software Engineering Institute</li>
</ul>
<h3>Intelligence Frameworks</h3>
<p>The following are three of the most commonly used intelligence frameworks that allow us to process and exploit the collected data so that it can be turned into intelligence.</p>
<h4>The Cyber Kill Chain</h4>
<p>Developed by Lockhead Martin, the Cyber Kill Chain is a means to identify the steps the threat actor should follow in order to achieve their objective. While this model does not fully encompass all the strategies involved in modern attacks, it does provide delimiting points at which an attack can be stopped. The seven steps include</p>
<ul>
    <li><strong>Reconnaissance:</strong> Getting to know the victim using non-invasive techniques.</li>
    <li><strong>Weaponization:</strong> Generating the malicious payload that is going to be delivered.</li>
    <li><strong>Delivery:</strong> Delivering the weaponized artifact.</li>
    <li><strong>Exploitation:</strong> Achieving code execution on the victim's system through the exploitation of a vulnerability.</li>
    <li><strong>Installation:</strong> Installing the final malware piece.</li>
    <li><strong>Command and Control (C2):</strong> Establishing a channel to communicate with the malware on the victim's system.</li>
    <li><strong>Actions on objectives:</strong> With full access and communication, the attacker achieves their goal.</li>
</ul>
<h4>The Diamond Model</h4>
<p>The Diamond Model provides a way to track breach intrusions by helping us establish the atomic elements involved. It compromises four main features: adversary, infrastructure, capability, and victim. These features are connected by the sociopolitical and technical axes.</p>
<p><a href="https://www.recordedfuture.com/diamond-model-intrusion-analysis" target="_blank">Applying Threat Intelligence to the Diamond Model of Intrusion Analysis</a> - RecordedFuture</p>
<h4>MITRE ATT&CK Framework</h4>
<p>The MITRE ATT&CK Framework is a descriptive model used to label and study the activity that a threat actor is capable of carrying out in order to get a foothold and operate inside an environment. One of the reasons this framework is so widely used, is that it provides a common taxonomy for the cybersecurity community to describe the adversary's behavior. This framework works as a common language that both offensive and defensive researchers understand.</p>
<p><a href="https://attack.mitre.org/" target="_blank">MITRE ATT&CK</a></p>

<p><em>Study notes and excerpts taken from <a href="https://www.amazon.com/dp/1838556370" target="_blank">Practical Threat Intelligence and Data-Driven Threat Hunting:</a> A hands-on guide to threat hunting with the ATT&CK™ Framework and open source tools, by Valentina Costa-Gazcón</em></p>