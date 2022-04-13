<h2>OSI Model</h2>
<a href="networks">Back</a>

<h2>Functions and Protocols at a Glance</h2>
<img src="/assets/images/table3.PNG" alt="Table 3 OSI Protocol Stack">

<div class="intro">
    <h3>Application (L7)</h3>
</div>

<div class="steps">
    <p>PDU: Data</p>
    <p>Layer 7: works closest to the user and provides file transmissions, message exchanges, terminal sessions, and much more. This layer does not include the actual applications, but rather the protocols that support the applications.</p>
    <ul>
        <li>Defines the interface to user processes</li>
        <li>Provides standardized network services</li>
    </ul>
    <h4>L7 PROTOCOLS</h4>
    <p>Protocol Function: The protocols at the application layer handle file transfer, virtual terminals, network management, and fulfilling networking requests of applications.</p>
    <ul>
        <li>File Transfer Protocol (FTP)</li>
        <li>Network Time Protocol (NTP)</li>
        <li>Simple Mail Transfer Protocol (SMTP)</li>
        <li>Internet Message Access Protocol (IMAP)</li>
        <li>Hypertext Transfer Protocol (HTTP)</li>
        <li>Dynamic Host Configuration Protocol (DHCP)</li>
        <ul>
            <li>UDP-based Protocol</li>
            <li>DHCP manipulates L2 based on responses arriving through L7</li>
        </ul>
        <li>Domain Name System (DNS) - DNS is an application layer protocol, because DNS query and answer is the application level communications.</li>
    </ul>
</div>

<div class="intro">
    <h3>Presentation (L6)</h3>
</div>
<div class="steps">
    <p>PDU: Data</p>
    <p>Layer 6: receives information from the application layer protocol and puts it in a format that any process operating at the same layer on a destination computer following the OSI model can understand. This layer provides a common means of representing data in a structure that can be properly processed by the end system. The presentation layer is concerned not with the meaning of data but with the syntax and format of that data.</p>
    <ul>
        <li>Specifies architecture-independent data transfer format</li>
        <li>Encodes and decodes data; Encrypts and decrypts data; Compresses and decompresses data</li>
    </ul>
    <p><b>Presentation Layer works as a Translator</b></p>
    <p>It translates the format an application is using to a standard format that can be sent over the network. It adds information to tell the destination computer the file type and how to process and present it.</p>
    <p><b>L6 PROTOCOLS (no protocols, just services)</b></p>
    <p>The services of the presentation layer handle translation into standard formats, data compression and decompression, and data encryption and decryption. No protocols work at this layer, just services. The following lists some of the presentation layer standards:</p>
    <ul>
        <li>American Standard Code for Information Interchange (ASCII)</li>
        <li>Tagged Image File Format (TIFF)</li>
        <li>Joint Photographic Experts Group (JPEG)</li>
        <li>Motion Picture Experts Group (MPEG)</li>
        <li>Musical Instrument Digital Interface (MIDI)</li>
    <ul>
</div>

<div class="intro">
    <h3>Session (L5)</h3>
</div>

<div class="steps">
    <p>PDU: Data</p>
    <p>Layer 5: is responsible for establishing a connection between the two applications, maintaining it during the transfer of data, and controlling the release of this connection. When the conversation is over, this path is broken down and all parameters are set back to their original settings. This process is known as dialog management (dialog control).</p>
    <ul>
        <li>Manages user sessions and dialogues</li>
        <li>Controls establishment and termination of logical links between users</li>
    </ul>
    <p><b>L5 PROTOCOLS</b></p>
    <p>The session layer protocols set up connections between applications; maintain dialog control; and negotiate, establish, maintain, and tear down the communication channel. Some of the protocols that work at this layer include:</p>
    <ul>
        <li>Layer 2 Tunneling Protocol (L2TP)</li>
        <li>Network Basic Input Output System (NetBIOS)</li>
        <li>Password Authentication Protocol (PAP)</li>
        <li>Point-to-Point Tunneling Protocol (PPTP)</li>
        <li>Remote Procedure Call (RPC)</li>
    </ul>
    <p><b>L5 PROTOCOL SECURITY</b></p>
    <p>Session layer protocols are the least used protocols in a network environment; Many of them should be disabled on systems to decrease the chance of them being exploited. RPC, NetBIOS, and similar distributed computing calls usually only need to take place within a network; thus, firewalls should be configured so this type of traffic is not allowed into or out of a network. Firewall filtering rules should be in place to stop this type of unnecessary and dangerous traffic.</p>
    <p><b>L5 MODES</b></p>
    <p>The session layer protocol can enable communication between two applications to happen in three different modes:</p>
    <ul>
        <li><b>Simplex Communication</b> - takes place in one direction, though in practice this is very seldom the case.</li>
        <li><b>Half-duplex Communication</b> - takes place in both directions, but only one application can send information at a time.</li>
        <li><b>Full-duplex Communication</b> - takes place in both directions, and both applications can send information at the same time.</li>
    </ul>
    <p><b>L5 VERSUS L4</b></p>
    <p>The functionality of the session and transport layers is similar insofar as they both set up some type of session or virtual connection for communication to take place. The difference is that protocols that work at the session layer set up connections between applications, whereas protocols that work at the transport layer set up connections between computer systems.</p>
    <ul>
        <li>Session layer protocols control application-to-application communication.</li>
        <li>Transport layer protocols handle computer-to-computer communication.</li>
    </ul>
</div>

<div class="intro">
    <h3>Transport (L4)</h3>
</div>

<div class="steps">
    <p>PDU: Segment</p>
    <p>Layer 4: When two computers are going to communicate through a connection-oriented protocol, they first agree on how much information each computer will send at a time, how to verify the integrity of the data once received, and how to determine whether a packet was lost along the way. The two computers agree on these parameters through a handshaking process at the transport layer.</p>
    <ul>
        <li>Provides reliable and sequential end-to-end packet delivery</li>
        <li>Provides connectionless oriented packet delivery</li>
    </ul>
    <p><b>L4 PROTOCOLS</b></p>
    <p>The protocols at the transport layer handle end-to-end transmission and segmentation of a data stream. The following protocols work at this layer:</p>
    <ul>
        <li>Transmission Control Protocol (TCP)</li>
        <li>User Datagram Protocol (UDP)</li>
        <li>Stream Control Transmission Protocol (SCTP)</li>
        <li>Resource Reservation Protocol (RSVP)</li>
        <li>QUIC (not an acronym)</li>
    </ul>
</div>

<div class="intro">
    <h3>Network (L3)</h3>
</div>

<div class="steps">
    <p>PDU: Packet</p>
    <p>Layer 3: The main responsibilities of layer 3, are to insert information into the packet’s header so it can be properly addressed and routed, and then to actually route the packet to its proper destination. In a network, many routes can lead to one destination. The protocols at the network layer must determine the best path for the packet to take. Routing protocols build and maintain their routing tables.</p>
    <ul>
        <li>Routes packets according to unique network addresses</li>
    </ul>
    <p><b>L3 PROTOCOLS</b></p>
    <p>The responsibilities of the network layer protocols include internetworking service,addressing, and routing. The following lists some of the protocols that work at this layer:</p>
    <ul>
        <li>Internet Protocol (IP)</li>
        <li>Internet Control Message Protocol (ICMP), (ping utility)</li>
        <li>Internet Group Management Protocol (IGMP)</li>
        <li>Routing Information Protocol (RIP)</li>
        <li>Open Shortest Path First (OSPF)</li>
    </ul>
</div>

<div class="intro">
    <h3>Data Link (L2)</h3>
</div>

<div class="steps">
    <p>PDU: Frame</p>
    <p>Layer 2: Different networking technologies can use different protocols, network interface cards (NICs), cables, and transmission methods. Each of these components has a different header data format structure, and they interpret electromagnetic signals in different ways. The data link layer is where the network stack knows in what format the data frame must be in order to transmit it properly over Ethernet, wireless, or frame relay links.</p>
    <ul>
        <li>Defines procedures for operating the communication link</li>
        <li>Provides framing and sequencing</li>
    </ul>
    <p><b>L2 PROTOCOLS</b></p>
    <p>The protocols at the data link layer convert data into LAN or WAN frames for transmission and define how a computer accesses a network. This layer is divided into the Logical Link Control (LLC) and the Media Access Control (MAC) sublayers. Some protocols that work at this layer include the following:</p>
    <ul>
        <li>Address Resolution Protocol (ARP)</li>
        <li>Reverse Address Resolution Protocol (RARP)</li>
        <li>Serial Line Internet Protocol (SLIP)</li>
        <li>Ethernet (IEEE 802.3)</li>
        <li>Wireless Ethernet (IEEE 802.11)</li>
    </ul>
    <p><b>The data link layer can be further divided into two functional sublayers:</b></p>
    <ul>
        <li>Logical Link Control (LLC), whose job is to interface with the network layer above, and</li>
        <li>Media Access Control (MAC), which is designed to interface with the physical layer below</li>
    </ul>
    <p><b>Logical Link Control (LLC) Sublayer</b></p>
    <p>The LLC sublayer takes care of flow control and error checking. Data coming from the network layer passes down through the LLC sublayer and goes to the MAC sublayer.</p>
    <p>Generally, LLC is implemented in software (as a device driver)</p>
    <p><b>Media Access Control (MAC) Sublayer</b></p>
    <p>The technology at the MAC sublayer knows if the network is Ethernet, wireless, or frame relay, so it knows how to put the last header and trailer on the packet before it “hits the wire” for transmission.</p>
    <p>MAC is built-in firmware on a physical device</p>
    <p><b>Network Interface Card (NIC)</b></p>
    <p>NICs bridge the data link and physical layers. Data is passed down through the first six layers and reaches the NIC at the data link layer. Depending on the network technology being used, the NIC encodes the bits at the data link layer, which are then turned into electricity states at the physical layer and placed onto the wire for transmission.</p>
    <p><b>Layer 2 Security Standards, include defending against:</b> Packet sniffing, modifying headers, and spoof traffic.</p>
</div>

<div class="intro">
    <h3>Physical (L1)</h3>
</div>

<div class="steps">
    <p>PDU: Bits</p>
    <p>Layer 1: converts bits into electromagnetic signals for transmission.</p>
    <ul>
        <li>Defines the physical means of sending data over network devices.</li>
    </ul>
    <p><b>L1 PROTOCOLS</b></p>
    <p>Network interface cards and drivers convert bits into electrical signals and control the physical aspects of data transmission, including optical, electrical, and mechanical requirements. The following are some of the standard interfaces at this layer:</p>
    <ul>
        <li>RS/EIA/TIA-422, RS/EIA/TIA-423, RS/EIA/TIA-449, RS/EIA/TIA-485</li>
        <li>10Base-T, 10Base2, 10Base5, 100Base-TX, 100Base-FX, 100Base-T, 1000Base-T, 1000Base-SX</li>
        <li>Integrated Services Digital Network (ISDN)</li>
        <li>Digital subscriber line (DSL)</li>
        <li>Synchronous Optical Networking (SONET)</li>
    </ul>
    <p><b>CONVERTING BITS INTO ELECTRONIC SIGNALS</b></p>
    <p>Signals and voltage schemes have different meanings for different LAN and WAN technologies. If a user sends data through the radio transceiver on a smartphone, the data format, electrical signals, and control functionality are much different than if that user sends data through an Ethernet NIC and onto an unshielded twisted pair (UTP) wire for LAN communication. The mechanisms that control this data going onto the radio waves, or the UTP wire, work at the physical layer.</p>
    <ul>
        <li>This layer controls synchronization, data rates, line noise, and transmission techniques.</li>
        <li>Specifications for the physical layer include the timing of voltage changes, voltage levels, and the physical connectors for electrical, optical, and mechanical transmission.</li>
    </ul>
</div>