# Content Moderation Working Group (WIP)

The Content Moderation working group aims to build tools
and functionality that give providers control over
the applications that run on their systems.

## Contact

* todo: discord group

## Projects

### Remote Probing

#### Provider Requirements:

* Lease API:
  * Close Lease

* Moderation API:
  * block Akash address
  * block Docker Image
  * block Hostname

### In-Cluster Tooling

#### Provider Requirements:

* Lease API:
  * Close Lease

### KYC

#### Provider Requirements:

### Blocklist

* Akash address
* Image
* Hostname

### 

## Meetings

### 2022-11-16

#### Attendees

### 2022-12-07

#### Attendees

- Boz Menzalji
- Alani Kuye
- Scott Carruthers (scott@akash.network)
- Tyler Wright (tyler@akash.network)
- Adam Bozanich (adam@akash.network)
- Andrew Mello (andrew.mello@akash.network)
- Deval Patel (deval@praetorapp.com)
- Jigar Patel (jigar@praetorapp.com)

#### Notes

* KYC/KYB - preferred method
  * Who is the KYC provider?
    * they own the customer
  * How is that represented on chain?
    * kado, moon pay, etc... may be on-chain by default.
  * needed?
  * risks of centralization
  * How does a provider know of tenant KYC?
    * API
    * On-chain
    * **PCMS (Provider Content Moderation System)**
    * EIN/similar 
 * Types of KYC/B
   * Single-scope: baic payments (checkr, yardstick, Onfido, kado, moon pay, etc...)
   * Partner-based:
     * Binance, Ledger, general partner that has done KYC
   * Self-hosted KYC
   * Provider KYC
   * similar to auditor
 * Tenant KYC
   * liability
   * accountability
 * KYC Concerns
   * KYC **must** be optional
   * possible additional friction for new users (tenants) especially if most providers require kyc.
     * possible solution to restrict non-kyc deployments to limited resources/timelines.

#### Follow-Up

* KYC/B Provider Research
  * Kado: Deval Patel
* Provider Services: PCM Requirements
  * Non-KYC requirements
    * define "remote probing" api: Deval Patel
    * In-Cluster Security Scanning: Andrew Melo
    * Define (akash address, image, hostname) allowlist API: Adam Bozanich
      * "only allow awesome-akash manifests"
  * KYC requirements
    * KYC/B access Design:
      * On-Chain?
      * API?

#### 22-12-2022

#### Attendees

- Alani Kuye
- Scott Carruthers (scott@akash.network)
- Adam Bozanich (adam@akash.network)
- Andrew Mello (andrew.mello@akash.network)
- Deval Patel (deval@praetorapp.com)
- Jigar Patel (jigar@praetorapp.com)

#### Notes

 * Deval: Spoke with Kado
   * KYC/B API: WIP - Q1 2023
     * How could the provider integrate with this.
     * More flexible provider bid engine order evaluation.
   * Offload $AKT
 * Deval: Non-KYC
   * Lease Status api exposed to provider.
   * Allow providers to view and choose for themselves.
   * Potentially share offending (accounts, images) via block lists.
   * define "remote probing" api: Deval Patel - management api
     * hostnames for lease
     * close a lease
     * disallow tenant account, lease image
   * andrew: static blocking
     * awesome-akash apps only.
       * how to identify.
       * image-based filtering.
     * port, image, tenant address, hostname allowlist.
     * In-Cluster Security Scanning: TBD.

#### Follow-Up

* "Make this official" - Akash network community sig.
  * Discord chat
  * sig-providers: mission statement, members, etc...
  * wg-content-moderation: mission statement, members, etc...
    * Anil will help with this.
* PRD for statict blocking (Moderation API).
  * objective
  * motivation
  * use-case
  * High-level implementation options.
* Provider Management API
  * Lease Status
  * Close Lease
  * Moderation API configured separately.
  * Authentication?
