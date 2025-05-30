# Controls and Compliance Assessment

## Case Study

This scenario is based on a fictional company:

Botium Toys is a small U.S. business that develops and sells toys. The business has a single physical location, which serves as their main office, a storefront, and warehouse for their products. However, Botium Toy’s online presence has grown, attracting customers in the U.S. and abroad. As a result, their information technology (IT) department is under increasing pressure to support their online market worldwide. 

The manager of the IT department has decided that an internal IT audit needs to be conducted. She's worried about maintaining compliance and business operations as the company grows without a clear plan. She believes an internal audit can help better secure the company’s infrastructure and help them identify and mitigate potential risks, threats, or vulnerabilities to critical assets. The manager is also interested in ensuring that they comply with regulations related to internally processing and accepting online payments and conducting business in the European Union (E.U.).   

The IT manager starts by implementing the National Institute of Standards and Technology Cybersecurity Framework (NIST CSF), establishing an audit scope and goals, listing assets currently managed by the IT department, and completing a risk assessment. The goal of the audit is to provide an overview of the risks and/or fines that the company might experience due to the current state of their security posture.

Your task is to review the IT manager’s scope, goals, and risk assessment report. Then, perform an internal audit by completing a controls and compliance checklist. 

## Scenario

Botium Toys: Scope, goals, and risk assessment report

### Scope

The scope of this audit is defined as the entire security program at Botium Toys. This includes their assets like employee equipment and devices, their internal network, and their systems. 

### Goals

Assess existing assets and complete the controls and compliance checklist to determine which controls and compliance best practices that need to be implemented to improve Botium Toys’ security posture..

### Current Assets

Assets managed by the IT Department include:
* On-premises equipment for in-office business needs
* Employee equipment: end-user devices (desktops/laptops, smartphones), remote workstations, headsets, cables, keyboards, mice, docking stations, surveillance cameras, etc.
* Storefront products available for retail sale on site and online; stored in the company’s adjoining warehouse
* Management of systems, software, and services: accounting, telecommunication, database, security, ecommerce, and inventory management
* Internet access
* Internal network
* Data retention and storage
* Legacy system maintenance: end-of-life systems that require human monitoring

## Risk Assessment

### Risk Description

Currently, there is inadequate management of assets. Additionally, Botium Toys does not have all of the proper controls in place and may not be fully compliant with U.S. and international regulations and standards.

### Control Best Practices

The first of the five functions of the NIST CSF is Identify. Botium Toys will need to dedicate resources to identify assets so they can appropriately manage them.
Additionally, they will need to classify existing assets and determine the impact of the loss of existing assets, including systems, on business continuity.

### Risk Score

On a scale of 1 to 10, the risk score is 8, which is fairly high. This is due to a lack of controls and adherence to compliance best practices.

### Additional Comments

The potential impact from the loss of an asset is rated as medium, because the IT department does not know which assets would be at risk. The risk to assets or fines from governing bodies is high because Botium Toys does not have all of the necessary controls in place and is not fully adhering to best practices related to compliance regulations that keep critical data private/secure.

## Security Controls Assessments Checklist

Do they use these controls?

| Control | Yes / No / ? | Comments |
|  :---:  | :---: |  :---:   |
| Least Privilege | No | All current employees can veiw internall stored data, potentially including PII & SPII |
| Disaster Recovery Plans | No | No disaster Recovery plans |
| Password Policies | ? | Password policies are in effect, however they are not up-to date |
| Separation Of Duties | No | None have been implimented |
| Firewall | Yes | The IT department has a firewall |
| Intrusion Detection System (IDS) | No | Not installed |
| Backups | No | No Backups |
| Antivirus Software | Yes | Installed and regularly monitored by the IT department |
| Manual Monitoring, Maintenance, and Intervention for Legacy Systems | ? | There is no regualr schedule or clear intervention methods |
| Encryption | No | No encryption, even on sensitive data (PII or SPII ) |
| Password management system | No | Not in effect |
| Locks (Offices, Storefront, Warehouse) | Yes | All have locks | 
| Closed-circuit Television (CCTV) Surveillance | Yes | Located in Botium Toys' main offices, store front and warehouse |
| Fire Detection/Prevention (Fire Alarm, Sprinkler System, ect) | Yes | Located in Botium Toys' main offices, store front and warehouse |

## Compliance 

Are Botium Toys currently adhearing to the following compliance best practices?

### Payment Card Industry Data Security Standard (PCI DSS)
| Best Practice | Yes / No / ? | Comments |
| :---: | :---: | :---: |
| Only authorized users have access to customers’ credit card information | ? | Currently unsure whether all employees have access, but it is likely |
| Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment | No | This information is stored locally, however all employees may be able to access the data |
| Implement data encryption procedures to better secure credit card transaction touchpoints and data | No | No encryption safeguards are currently in place |
| Adopt secure password management policies | No | There is a password policy in place, however it is outdated and not enforced with a password management system |

### General Data Protection Regulation (GDPR)
| Best Practice | Yes / No / ? | Comments |
| :---: | :---: | :---: |
| E.U. customers' data is kept private/secured | Yes | Privacy policies, procedures and processes have been developed and enforced by the IT department |
| There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach | Yes | Established by the IT department |
| Ensure data is properly classified and inventoried | Yes | Established and enforced by the IT department |
| Enforce privacy policies, procedures, and processes to properly document and maintain data | Yes | Handled by the IT department |

### System and Organizations Controls (SOC type 1, SOC type 2)
| Best Practice | Yes / No / ? | Comments |
| :---: | :---: | :---: |
| User access policies are established | No | Access controls pertaining to least privilege and separation of duties have not been implemented |
| Sensitive data (PII/SPII) is confidential/private | No | All current employees, may have access regardless of job role |
| Data integrity ensures the data is consistent, complete, accurate, and has been validated | Yes | Data integrity procedures are in place |
| Data is available to individuals authorized to access it | ? | It is, however, all employees have access to all data without restrictions |

## Recommendations

During this audit, many security controls were found to be ineffective, unenforced, or entirely absent. As a result, Botium Toys currently has a weak security posture, leaving it vulnerable to both internal and external threats. With the company experiencing rapid growth, it may soon attract increased attention and become a potential target for cyber threats. In light of these findings, I recommend implementing the following controls to strengthen the organization’s overall security posture:
* Least privilege
  * Implementing least privilege ensures that users have access only to what is essential for their roles, thereby limiting the potential impact of insider threats or external compromise
*  Password policies & Password management systems
  * Implementing strong password policies enhances operational efficiency while significantly reducing the risk posed by internal misuse and external attacks
