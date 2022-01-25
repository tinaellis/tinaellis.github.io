<h2>Data Encapsulation</h2>
<a href="networks">Back</a>

<h2>Data Encapsulation: TCP/IP and OSI Protocol Suites</h2>
<p> Data encapsulation occurs as data from a sender is sent to a receiver. At each logical step of the data encapsulation process, the data becomes larger as new information is added to it. The data encapsulation process can change depending on the data type and sender’s location. An overview of data encapsulation reveals that communication of data is determined by a set of defined rules commonly referred to as “protocols”. Layered protocol stacks provide a framework for governing the transmission of data. The most used protocol stacks are the Transmission Control Protocol/Internet Protocol (TCP/IP) suite and the Open Systems Interconnection (OSI) model, (Padallan, 2019, p. 45).  Both the TCP/IP and OSI models use data encapsulation processes to facilitate and regulate how data transmission should occur over a network.</p>
<div class="intro">
    <h3>TCP/IP Protocol Suite</h3>
</div>
<div class="steps">
    <p>The TCP/IP protocol suite is a theoretical model that provides us with a way to discuss and understand network communications. The communication mission of the TCP/IP protocol suite focuses on the functions that are performed by protocols located within the Internet layer and Transport layer. It is commonly used when discussing TCP/IP protocols specifically. The four layers within the TCP/IP protocol suite and their functions are presented in Table 1.</p>
    <h4>TCP/IP Protocol Suite</h4>
    <img src="/assets/images/table1.PNG" alt="Table 1 TCP/IP Protocol Layers">
    <p>The protocols within the TCP/IP stack that are responsible for performing these functions may spread across multiple layers. The layer assignment is typically selected based upon when that protocol is first initiated. This provides network professionals with a reference point when discussing TCP/IP protocol functions.</p>
    <p>The TCP/IP model applies a four-step data encapsulation process that directly corresponds to the four layers of the TCP/IP protocol suite. At each layer, the appropriate protocols examine and prepare the data for transmission to the next layer in the stack by adding or removing fields from the data header. An overview of the TCP/IP data encapsulation process is presented in Table 2.</p>
    <h4>TCP/IP Data Encapsulation</h4>
    <img src="/assets/images/table2.PNG" alt="Table 2 TCP/IP TCP/IP Data Encapsulation">
    <p>De-encapsulation occurs on the destination host as the four-step data encapsulation process is performed in reverse. Frames at the Link layer are transformed into packets at the Internet layer, packets revert into segments at the Transport layer, and segments become the original raw data at the Application layer. The TCP/IP data encapsulation model provides network administrators with a way to ensure that data is delivered accurately using clearly defined operational processes which facilitate both error detection and correction, (Cole, 2020, p. 98).</p>
</div>
<div class="intro">
    <h3>OSI Protocol Stack</h3>
</div>
<div class="steps">
    <p>The OSI protocol stack is a reference model that classifies how data is theoretically prepared and transported across a network. It is the most widely used method to discuss and understand network communication. The seven layers within the OSI protocol stack and their functions are presented in Table 3.</p>
    <h4>OSI Protocol Stack</h4>
    <img src="/assets/images/table3.PNG" alt="Table 3 OSI Protocol Stack">
    <p>The protocols within the OSI model stack that are responsible for performing these functions may spread across multiple layers. The layer assignment is typically selected based upon when that protocol is first initiated. This provides network professionals with a reference point when discussing or troubleshooting OSI protocols functions.</p>
    <p>The OSI model provides us with a seven-step process for data encapsulation which corresponds to the seven layers of the OSI protocol stack. Throughout the data encapsulation process, data is referred to as Protocol Data Units (PDU). These labels help to identify and communicate information about a unit of data at any given layer. An overview of the OSI model data encapsulation process is presented in Table 4.</p>
    <h4>OSI Data Encapsulation</h4>
    <img src="/assets/images/table4.PNG" alt="Table 4 OSI Data Encapsulation">
    <p>De-encapsulation occurs on the destination host as the seven-step data encapsulation process is performed in reverse. Bits PDU are accepted at the Physical layer and are converted into Frame PDU at the Data Link layer, then into Packet PDU at the Network layer, and Segment PDU at the Transport layer. Segment PDU becomes data at the Session layer which is then decrypted at the Presentation layer. The original raw data is then realized at the Application layer where it is delivered to the intended operating system for processing, (StudyCCNA, 2021).</p>
</div>
<div class="intro">
    <h3>Comparing Processes</h3>
</div>
<div class="steps">
    <p>The TCP/IP and OSI data encapsulation processes are executed similarly with respect to the differences found within their individual protocol stacks. In the Application layer of the TCP/IP model, data is processed similarly to the Session, Presentation, and Application layers of the OSI model. The data segmentation process performed at the Transport layer of the TCP/IP model is comparable to the Transport layer of the OSI model. At this layer, data is broken into segments or Segment PDU, and sequencing information is added to the segment headers. The Internet layer of the TCP/IP model can be compared to the Network layer of the OSI model. Here we see segmented data converted into packets, or Packet PDU, as addresses and routing decisions are added to the data. Lastly, the Link layer of the TCP/IP model is comparable to the functions realized at the Physical and Data Link layers of the OSI model. At this phase of the data encapsulation process, data packets are converted into frames and bits, or Frame PDU and Bit PDU. Here we see the physical layout and message formatting descriptions added, and the actual transmission of bits over the transmission medium, (Testout, 2.1.3).</p>
    <p>The TCP/IP protocol suite is a theoretical model that provides us with a way to discuss and understand network communications. The OSI protocol suite is a reference model that provides us with a way to understand and communicate how data is prepared and transported across a network. Both the TCP/IP and OSI models use data encapsulation processes and standards to facilitate and regulate how data transmission should occur over a network. The TCP/IP model adheres to a four-step data encapsulation process that is comparable to the seven-step data encapsulation process used by the OSI model. Both models provide network administrators with a way to discuss, troubleshoot, and understand network communications.</p>
</div>
<p>Sources</p>
<p>StudyCCNA (2021, June 24). Encapsulation. Study CCNA. Retrieved October 27, 2021, from https://study-ccna.com/encapsulation/.</p>
<p>TestOut Corp. (2020, January 14). TestOut Routing and Switching Pro (section 2). Retrieved from http://www.testout.com/.</p>
<p>Padallan, J. O. (2019). Chapter 2 Principles and Protocols in Computer Networks. In Computer Networks and Communications (pp. 26–51). essay, Arcler Press.</p>
<p>Cole, T. D. (2020). Designing Wireless Sensor Network Solutions for Tactical ISR. Artech House.</p>