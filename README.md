Electronic medical records (EMRs) are critical, highly sensitive private information in healthcare, and need to be
frequently shared among peers such as healthcare providers, insurance companies, pharmacies, researchers, patients
families, among others. Blockchain provides a shared , immutable and transparent history of all the transactions
to build applications with trust, accountability and transparency. This provides a unique opportunity to develop
a secure and trustable EMR data management and sharing system using blockchain.

Using blockchain technology for primary patient care can help to address the following problems
of the current healthcare systems:

A patient often visits multiple disconnected hospitals. He has to keep the history of all his data and maintain the
updates. This leads to the situation when required information may not be available.

# Due to the unavailability of the data, patient may have to repeat some tests for laboratory results. This is common
when the results are stored in another hospital and can not be immediately accessed.
# The healthcare data are sensitive and their management is cumbersome. Yet, there is no privacy-preserving system
in clinical practice that allows patients to maintain access control policy in an efficient manner.
# Sharing data between different healthcare providers may require major effort and could be time consuming.
Relying on centralized entity that would store and manage the patients’ data and access control policies means having
single point of failure and a bottleneck of the whole framework.

The possibility of using blockchain for healthcare data management has recently raised a lot of attention.In our work,
we focus on a practical implementation of a system that uses blockchain technology and can be integrated in clinical
practice. We employ permissioned blockchain technology to maintain metadata and access control policy. Combining these technologies allows us to guarantee data security and
privacy as well as availability with respect to the access control policy defined by the patient.

# 1. Background on Blockchain:
Blockchain is a peer-to-peer distributed ledger technology that was initially used in the financial industry. Based
on how the identity of a user is defined within a network, one could distinguish between permissioned and permissionless
blockchain systems. A permissionless system is one in which the identities of participants are either pseudonymous
or even anonymous and every user may append a new block to the ledger. In contrast, in case of a permissioned blockchain,
the identity of a user is controlled by an identity provider. The identity provider is trusted to maintain access
control within the network and the user’s rights to participate in the consensus, or validate a new block. Next we
introduce two most well-known implementations of the blockchain technology: Ethereum and Hyperledger.

# The Hyperledger blockchain network is permission-based and requires users to sign up to use it. Permissioning on the
network is controlled using Hyperledger modelling and access control languages. Hyperledger Fabric is a platform
for distributed ledger solutions underpinned by a modular architecture delivering high degrees of confidentiality,
resilience, flexibility and scalability. Medical information is often highly sensitive, in both a social and legal
sense, so a closed blockchain such as Hyperledger Fabric helps to retain the necessary privacy required for such
an application. Hyperledger Fabric is a better solution for managing access to health records, as it accommodates
for multiple layers of permission, meaning the owner of a set of data can control which parts of their data is accessed.

# Potential Blockchain Application in Healthcare:
Blockchain provides a unique opportunity to support healthcare.

Our EHR Solution enables the user to give healthcare professionals access to their personal health data. EHR Solution
then records interactions with this data in an auditable, transparent and secure way on systems distributed ledger.

Lastly, Our EHR Solution is a platform for others to use that complement and improve the user experience. Users will
be able to leverage their medical data to power a plethora of applications and services. Our Solution improves care
for people by placing the patient at the centre of the digital transformation of healthcare. In order to be provided
with the best care patients not only can, but must have control over their own data.

# Technical Explanation
Participants Definitions and Permissions:

With a plethora of different actors, identity management and access to data is key to our EHR solution. A dynamic system
has been developed that identifies actors and gives them the appropriate scope over a health record, contingent on
the patient’s permission.

# Participant $ Permissions

# Patient
@ Create/READ/Update Own record
@ Revoke permission from Practitioners/Institutions.
@ Permission a Practitioner/Institution to Read/Write EHR or a portion of their EHR
@ Write certain attributes to EHR :
- Amount of tobacco consumed daily
- Alcohol consumed weekly
- Weekly exercise
@ Able to search avaialble Clinicians/Labs in network.

#Clinician / Labs
@ Read/Write on permissioned EHRs
@ Able to search avaialble Clinicians/Labs in network.

# Transactions
Patient Granting Access:

• Patient A grants access to EHR to Practitioner A</p>
• Practitioner A’s ID is added to Patient A’s authorised asset on the ledger</p>
• Patient A’s ID is added to Practitioner A’s authorised asset on the ledger</p>
• The Symmetric key for the EHR is decrypted with Patient A’s private key</p>
• Symmetric key is then encrypted with Practitioner A’s public key </p>

Patient Revoking Access:

• Patient A revokes access from Practitioner A</p>
• Practitioner A’s ID is removed from Patient A’s authorised asset</p>
• Patient A’s ID is removed from Practitioner A’s authorised asset</p>
• Patient A’s private key is used to decrypt Symmetric key for EHR which is used to decrypt the EHR</p>
• The EHR is encrypted with a new Symmetric key</p>
• The new Symmetric key is encrypted with Patient A’s public key and the public keys of all the remaining IDs that
have permission


# Data Structure:

Hyperledger’s modelling language will be used to define the domain model for the network. Below are some examples
from the .CTO file of how models will be defined and stored on the chain. These are subject to change depending
upon different regulations and requirements in order to make the platform HIPPA compliant.
