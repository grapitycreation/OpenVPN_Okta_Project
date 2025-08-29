# OpenVPN_Okta_Project

## 1. Introduction
**Objectives**
- Build a secure connection model via VPN.
- Integrate LDAP authentication and MFA for user management.
- Test and ensure access control and the security of the VPN model.

![iamge](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image3.png)

## 2. Context and Scope
### 2.1 Context for VPN Application:
- Remote access to the internal network.
- Ensure security and safety during connection.
- Require authentication methods for user management and prevention of unauthorized access.
- Serve as an optimal and cost-effective solution.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image5.png)

### 2.2 Scope of the Project:
- Install and configure OpenVPN, deployed in Google's cloud environment.
- Register and integrate a domain for the OpenVPN Web UI.
- Set up two-factor authentication (MFA) via TOTP.
- Utilize Okta and LDAP Authentication for user management.

## 3. Deployment
### 3.1 Technology used
#### 3.1.1 OpenVPN:
- OpenVPN is an open-source project widely trusted by many businesses and companies.
- OpenVPN can run on multiple operating systems: Windows, macOS, Linux, etc.
- OpenVPN uses robust encryption algorithms and connection protocols.
- Users have full customization options for OpenVPN, including encryption protocols, virtual network configuration, and authentication methods.

![image](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f5/OpenVPN_logo.svg/768px-OpenVPN_logo.svg.png)

#### 3.1.2 Okta Directory:
- A core component of Okta's Identity and Access Management (IAM) system.
- Can integrate with thousands of applications and services through standard protocols such as LDAP, SAML, OAuth, SCIM, or Okta's APIs.
- Benefits include centralized management, scalability, ease of use, and compatibility with various environments.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image7.png)

#### 3.1.3 VPN Remote Access Model

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image8.png)

**Server side:** 
- Two virtual machines share the same internal network.
- The virtual machine "atm-vpn-vm" serves as the VPN server, with OpenVPN Server installed.
- The virtual machine "ftp-server" is configured as an FTP server.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image9.png)

**Okta side:**
- An LDAP interface is created to connect to the Okta directory.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image10.png)

**Client side:**
- Any user device (PC, laptop, or mobile phone) can act as a client.

## 4. Functionalities:
### 4.1 Connect to server through VPN
- Create users on the server's web interface.
- Configure access permissions for users.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image11.png)


- Connect to the VPN server using the user's profile.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image12.png)

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image13.png)

- After successfully connecting, we check whether the VPN Server has faked the IP address of the device and encrypted the packets or not.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image13.2.webp)

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image13.1.webp)


- Download files from the FTP server.
- Upload files to the FTP server.

![iamge](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image14.png)

### 4.2 Configuring User Access using Okta Directory:

- Create an additional server within the network range 10.128.0.0/20.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image15.png)

- Add two users to the Okta Directory, assigning them to two different groups.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image16.png)

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image17.png)

- Use the two newly created users to access OpenVPN.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image18.png)

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image19.png)


- Add a Post-Auth Script to map Okta groups to OpenVPN.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image20.png)

- Configure access permissions for the groups and conduct testing.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image21.png)

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image22.png)

### 4.3 Testing Secure Connection:
- Use Tcpdump to capture packets and Wireshark to observe the VPN connection process.

![image](https://github.com/grapitycreation/OpenVPN_Okta_Project/blob/main/media/image23.png)

- Monitor the encryption and decryption of packets during communication through the VPN tunnel.

## 5. Evaluation and Development direction
### 5.1 Evaluation
Some drawbacks of OpenVPN Access Server include its demand for high server performance, vulnerability to poor internet connections, complexity in advanced configurations such as routing or clustering, and the lack of a connection interface on Linux.

### 5.2 Development direction
- Build an Access Server Cluster system.
- Research the implementation of a Zero Trust Network Access model or advance further with the development of a Secure Access Service Edge (SASE) model.

## 6. References
- https://openvpn.net/community-resources/
- https://help.okta.com/en-us/content/topics/directory/ldap-agent-main.htm





  
