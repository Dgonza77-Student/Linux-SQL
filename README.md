# Controls and Compliance Assessment - Botium Toys

## Objective

Examine and manage the permissions of files in the /home/researcher2/projects directory for the reasercher 2 user

---

### Skills Learned

- Proficiency in conducting security audits following the **NIST CSF** framework.
- Ability to assess risk and assign risk scores based on current security controls.
- Understanding of compliance best practices (e.g., PCI DSS, GDPR) and their application in business environments.
- Knowledge of implementing various control types (preventive, corrective, detective, and deterrent).
- Experience in reviewing and improving password policies, access controls, and disaster recovery plans.

---

### Tools Used

- **Risk Assessment Tools**: For evaluating asset risks and assigning scores.
- **Compliance Checklists**: For tracking security controls and regulatory compliance (PCI DSS, GDPR).
- **Network Monitoring Tools**: Such as **Wireshark** for capturing and analyzing network traffic.
- **Firewall & IDS Configuration Tools**: To assess the effectiveness of firewall rules and intrusion detection systems (IDS).
- **Backup & Disaster Recovery Planning** Tools: To ensure business continuity in case of data loss.

---

## Scenario
This scenario is based on a fictional company:

Botium Toys is a small U.S. business that develops and sells toys. The business has a single physical location, which serves as their main office, a storefront, and warehouse for their products. However, Botium Toy’s online presence has grown, attracting customers in the U.S. and abroad. As a result, their information technology (IT) department is under increasing pressure to support their online market worldwide. 

The manager of the IT department has decided that an internal IT audit needs to be conducted. She's worried about maintaining compliance and business operations as the company grows without a clear plan. She believes an internal audit can help better secure the company’s infrastructure and help them identify and mitigate potential risks, threats, or vulnerabilities to critical assets. The manager is also interested in ensuring that they comply with regulations related to internally processing and accepting online payments and conducting business in the European Union (E.U.).   

The IT manager starts by implementing the National Institute of Standards and Technology Cybersecurity Framework (NIST CSF), establishing an audit scope and goals, listing assets currently managed by the IT department, and completing a risk assessment. The goal of the audit is to provide an overview of the risks and/or fines that the company might experience due to the current state of their security posture.

### Botium Toys: Scope, Goals, and Risk Assessment Report

### Scope

The entire security program at **Botium Toys** was assessed, which included their IT infrastructure, internal processes, compliance practices, and security controls. The assets reviewed included on-premises equipment, employee devices, internal networks, and systems for managing accounting, telecommunication, and security.

### Goals

To assess and complete a controls and compliance checklists that determins which practices need to best be implemented to improve the security posture of **Botium toys**

---

### Current Assets
--
Assets managed by the IT Department include:

● On-premises equipment for in-office business needs

● Employee equipment: end-user devices (desktops/laptops, smartphones),
remote workstations, headsets, cables, keyboards, mice, docking stations,
surveillance cameras, etc.

● Storefront products available for retail sale on site and online; stored in the
company’s adjoining warehouse

● Management of systems, software, and services: accounting,
telecommunication, database, security, ecommerce, and inventory
management

● Internet access

● Internal network

● Data retention and storage

● Legacy system maintenance: end-of-life systems that require human
monitoring

## Controls Assessment Checklist

Does Botium Toys currently have this control in place?

| Yes / No | Control | Explanation |
| :---: | :---: | :--- |
| No | Least Privilege | Least Privilege is not practiced, employees have access to all information in organization's database. Needs to be limited to prevent Breach. |
| No | Disaster Recovery Plans | In order to ensure business continuity, the organization needs to implement Disaster Recovery Plans. None currently present |
| No | Password policies |Password policy does exist but is NOT in line with current password complexity requirements. |
| Yes | Firewall | Firewall is properly installed with correct set of definitions and rules for filtering |
| Yes | Antivirus | The antivirus software is active and monitored regularly by the IT team. |
| No | Backups | Backup systems, much like disaster recovery plans, are not in place. Need to be set up to ensure business continuity and redundancy.|
| No | Encryption |No encryption has been set up. This is a massive security concern, especially for securing confidential customer data.|
| No | IDS | No intrusion detection system has been installed.|
| Yes | Storefront |Physical locks, CCTV surveillance and fire detection and prevention systems are present.|
| Yes | CCTV | Yes, Up and running.|
| Yes | Fire detection | Require maitenance but up and running|

---

## Compliance Checklist

Does Botium Toys currently adhere to this compliance best practice?

### Payment Card Industry Data Security Standard (PCI DSS)

| Yes / No | Best Practice | Explanation |
| :---: | :---: | :--- |
| No | Authorized users can access sensitive data such as customers credit card info| A violation of PCI DSS, authorized users can access customer credit card info without proper restrictions. There is no implementation of the least privilege principle. |
| No | Sensitive Info, such as credit cards, are stored,transmitted, processed and accepted securely| Cardholder data is not encrypted, violating PCI DSS standards. |
| No | Encryption standards | Encryption has not been implemented for sensitive data. |
| No | Password management policies | No password management present. |


### GDPR Compliance

| Yes / No | Best Practice | Explanation |
| :---: | :---: | :--- |
| No | Data for E.U Customers is kept private/secure | GDPR standards are not complied with, this places the organization at risk of fines. |
| Yes | Plan where E.U customers are notified within 72 hours if their data is compromised | Organization has a documented plan to notify E.U customers within 72 hours of a data breach |
| No |Ensure data is properly classified and inventoried|Assets have been documented and inventoried however, no classifications have been given at this time. |
| Yes | Enforcement of privary policies| IT members developed policies and procedures for policies and ensure they are enforced. |

### System and Organizations Controls

| Yes / No | Best Practice | Explanation |
| :---: | :---: | :--- |
| No | User access policies are established | Employees have access to all data, and there is no established access policy. |
| No | Sensitive data (PII/SPII) is confidential/private | Encryption is not currenlty used to better ensure PII/SPII confidentiality |
| Yes | Data integrity is consistent, complete, and accurate | Controls are in place for data integrity |
| No | Data is only accessible to authorized users | Data protection standards and principle, such as that of least privilege, are not practiced within the organization |

---

## Recommendations

After assessing the security posture at **Botium Toys**, several recommendations were made to enhance the protection of sensitive information and ensure compliance with industry standards:

1. **Implement Principle of Least Privilege**: Apply the principle of least privilege by restricting access to customer and sensitive data alongside a separation of duties.
2. **Development of a Disaster Recovery Plan**: Create a disaster recovery plan to ensure business continuity in case of system failure or data breach.
3. **Implementation of Modern Password Policies**: Update password policies must be implemented in order to meet current complexity requirements alongside the implementation of a centralized password management system.
4. **Implement Encryption**:  Sensitive data, especially cardholder information, must be encrypted to protect confidentiality and comply with regulations.
5. **Install Intrusion Detection System (IDS)**: Installation of an Instrusion detection system will mitigate risk, allow response to unathorized access or attacks.

---
First I opened the console and navigated to the projects directory under the researcher 2 user by using the LS command to list the directories and the cd command to change to the project directory

![image](https://github.com/user-attachments/assets/535f55a8-5940-4fdb-876d-4416cbb4fbd4)

To list the permissions of the files in the projects directory I utilized the "Ls -l" command

![image](https://github.com/user-attachments/assets/55d5bbeb-4983-406e-81aa-65a72e0e2aaa)
Following the command, many 10-character strings are listed such as "drwx--x---" which indicate the permissions set on the file. 

File permissions can be read as the following:
The 1st character lets the user know what the file type is. The user will see either a "d" for directory or a "-" for file
The 2nd-4th characters are permissions for the USER and indicate the read,write and execute permissions in that order (r,w,x). If a letter is not present and instead the user views a hyphen (-) then that permission is not granted to the user group.

Following the 2nd-4th characters, the 5th through seventh characters are used to indicate the read,write and execute permissions for the group. Much like user, if a letter is not present and instead replaced with a hyphen, then that permission is not granted to the group.

Lastly, the 8th through 10th characters indicate the read, write and execute functions for "Other". "Other" is used for all other users on the system aside from the user and the group

After taking a brief look at the files and their respective permissions, I execute "ls -la" to list all files (Including any potential hidden files) and their permissions

![image](https://github.com/user-attachments/assets/99640433-fa4f-4fd9-8715-8b0282081ab9)
After executing the command, .project_x.txt is shown.

With the information gathered, I begin to determine which of the files have incorrect permissions and make changes as needed. This is done in order to remove any users with unathorized access to the system and strengthen the security on the system overall.

One of the tasks assigned is that "Others" owner group should not have write permissions for any files in the projects directory.

![image](https://github.com/user-attachments/assets/02d45329-d94d-48fc-b01d-ac7aacbfa0db)

We can see here that the .project_k.txt file has both read and write permissions for the "Others" owner group

In order to remove the write permission from the "Others" Owner group I execute the command chmod o-w project_k.txt
The above command calls upon chmod (Change mode) o (others) -w (remove write) project_k.txt(The file to apply the command to)
After running the command and checking the directory, we can see that the write command has been removed from the "Others" Owner group for the file
![image](https://github.com/user-attachments/assets/992984c4-388e-4ba5-adba-186d977efe8a)

My next set of instructions is to make sure that the project_m.txt file is not readable or writeable by the group or "other" owner groups. The only group that should have those permissions is the user owner group.

To complete the task I first list out the files in the projects directory and see what permissions are already set to the project_m.txt file
![image](https://github.com/user-attachments/assets/ee93c76d-c501-459f-857c-6fd583bb4847)
In the above image I have highlighted the group owner permissions in blue and the "Other" owner group in pink.
As listed, the "Other" owner group has no permissions while the "group" owner group  only has the read permission.

Furthermore, we can see that the user group already has read and write permissions (Highlighed in yellow)

![image](https://github.com/user-attachments/assets/fceb3de5-1e09-4e10-ac52-617de1a25a50)

In order to meet project requirements, I remove the read permission from the "group" owner group via chmod g-r project_m.txt
![image](https://github.com/user-attachments/assets/9850598d-b065-4f76-913d-5260b3be8043)


Next I am tasked to determine if a hidden file has incorrect permissions and if they do, to change the permissions as needed. This action is done to further remove unauthorized access and strengthen security on the system

The file .prokect_x.txt is a hidden file that should not be written to by anyone, yet we can see write permissions for both the user owner group and the group owner group. (User highlighted in red and group highlighted in blue)

![image](https://github.com/user-attachments/assets/187e95a4-4768-4b0c-a53d-26676b87d865)

In order to properly remove the write permission from both the user and the group AND still allow both to read I executed the command chmod ug=r .project_x.txt

this command makes it so that any other permission aside from read is automatically removed and targets both the user and the group command. This is the most efficent option instead of doing a command for both user and group

![image](https://github.com/user-attachments/assets/9747aaca-76a6-468f-8faa-d303151dbe64)

(User is highlighted in red and group is highlighted in blue)


lastly I am tasked with changing the permissions of the "drafts" directory. In order to do so I use the CD command to change to the drafts directory
We can see the drafts directory being represented by "." and our previous directory (Projects) being represented by ".." alongside their respective permissions
![image](https://github.com/user-attachments/assets/e02d2c76-584a-41e9-9fd8-21175866c7bc)

When looking at the permissions we can also see that the user groups for the "Drafts" directory has permission to access the drafts directory and its contents

Our objective is then to remove the execute permission for the group from the drafts directory and we do that by running the command chmod g-x .
in which afterwards we can see the execute permission removed from the group owner group.
![image](https://github.com/user-attachments/assets/785fd851-6204-48bc-b328-8b149ac1809b)
