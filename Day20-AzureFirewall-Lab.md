**What is Azure Firewall?**

Azure Firewall is a cloud-based security service that protects your Azure virtual network resources from incoming and outgoing threats.

<img width="490" height="331" alt="image" src="https://github.com/user-attachments/assets/c509fed7-a674-4bbb-bd74-72f9043b54cd" />

Azure Firewall is available in three SKUs: Basic, Standard, and Premium.

**Azure Firewall Basic** ----> Azure Firewall Basic is designed for small and medium-sized businesses (SMBs) to secure their Azure cloud environments. It provides essential protection at an affordable price.

Key limitations of Azure Firewall Basic include:

Supports Threat Intel alert mode only
Fixed scale unit with two virtual machine backend instances
Recommended for environments with an estimated throughput of 250 Mbps

----------------------------------------

**Azure Firewall Standard** ------> Azure Firewall Standard offers L3-L7 filtering and threat intelligence feeds directly from Microsoft Cyber Security. It can alert you to and block traffic from or to known malicious IP addresses and domains. It updates in real time to protect against new and emerging threats

---------------------------------------

**Azure Firewall Premium** -----> Azure Firewall Premium provides advanced capabilities, including signature-based IDPS for rapid attack detection by identifying specific patterns. These patterns can include byte sequences in network traffic or known malicious instruction sequences used by malware. With over 67,000 signatures in more than 50 categories, updated in real time, it protects against new and emerging exploits such as malware, phishing, coin mining, and Trojan attacks.

===============================================================================================================================

**How Azure Firewall protects an Azure virtual network**

To understand how Azure Firewall protects your virtual network, know that there are two key characteristics to any Azure Firewall deployment:

The firewall instance has a public IP address to which all inbound traffic is sent.
The firewall instance has a private IP address to which all outbound traffic is sent.
That is, all traffic—inbound and outbound—goes through the firewall. By default, the firewall denies access to everything. Your job is to configure the firewall with the conditions under which traffic is allowed through the firewall. Each condition is called a rule, and each rule applies one or more checks on the data. Only traffic that passes all the firewall's rules is allowed to pass through.

How Azure Firewall manages network traffic depends on where the traffic originates:

For allowed inbound traffic, Azure Firewall uses DNAT to translate the firewall's public IP address to the private IP address of the appropriate destination resource in the virtual network.
For allowed outbound traffic, Azure Firewall uses SNAT to translate the source IP address to the firewall's public IP address.

=============================================================================================================================

**Azure Firewall rule types**

The following describes the three types of rules you can create for an Azure firewall.

Ruletype  	Description
NAT	 -----> Translate and filter inbound internet traffic based on your firewall's public IP address and a specified port number. For example, to enable a remote desktop connection to a virtual machine, you might use a NAT rule to translate your firewall's public IP address and port 3389 to the private IP address of the virtual machine.
Application----> Filter traffic based on an FQDN. For example, you might use an application rule to allow outbound traffic to access an Azure SQL Database instance using the FQDN server10.database.windows.net.
Network	------> Filter traffic based on one or more of the following three network parameters: IP address, port, and protocol. For example, you might use a network rule to allow outbound traffic to access a particular DNS server at a specified IP address using port 53.

=============================================================================================================================

**When to use Azure Firewall**

Azure firewall should be and below are the crtitera when you should consider using it

You want to protect your network against infiltration.
You want to protect your network against user error.
Your business includes e-commerce or credit card payments.
You want to configure spoke-to-spoke connectivity.
You want to monitor incoming and outgoing traffic.
Your network requires multiple firewalls.
You want to implement hierarchical firewall policies.


