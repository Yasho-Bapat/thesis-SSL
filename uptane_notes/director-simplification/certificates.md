# Certificates and their types, jargon, etc

## X.509 certificate
An X.509 certificate is a digital certificate based on the widely accepted International Telecommunications Union (ITU) X.509 standard, which defines the format of public key infrastructure (PKI) certificates. <br>
**Public Key Infrastructure** includes public and private keys (for asymmetric cryptography). The most commonly used algorithms to generate public keys are RSA, ECC and DSA. <br>
Public keys are visible to the whole world. Private keys are generated and stored ONLY locally. Never public. <br>
* Public keys are used to encrypt, private to decrypt when encrypting messages meant only for someone specific. 
  * So if Alice wants to send only Bob a message, Alice will encrypt the message using Bob's public key. ONLY Bob's private key will be able to decrypt this message. 
* Private keys are used to SIGN, and the public key is used to verify this signature.
  * If Alice signs a message using her private key, anyone will be able to decrypt that message with Alice's public key. This will verify that Alice, and ONLY Alice has signed this message. 

## SSH Certificates

## OCSP - Online Certificate Status Protocol
This is an alternative to CRL (Certificate Revocation List), which tells you about the validity of a certificate.
