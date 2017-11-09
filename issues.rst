Issues
======

How to be compatible with pop3, imap and smtp protocols ?
---------------------------------------------------------

- Non distributed (Postfix?) gateways that encrypt (or not) exhanged emails 
  and forward them to DEFMS.
  * email going through a defms-gateway will never know what a hard drive is.

How to distribute Mailbox in a secure and scalable way?
-------------------------------------------------------

- [?] orbit-db is a distributed database over ipfs,
  * can't be unique bc not scalable
  * having one database per every thread or mailing list shared accros 
    relevent stakeholders may be to explore.
  * https://github.com/orbitdb/orbit-db/blob/master/examples/keyvalue.js

- [?] ipfs api now propose pub/sub functions that can be usefull
  * more dev
  * https://github.com/orbitdb/orbit-db-pubsub

- 

How to manage if an email is encrypted or not ?
-----------------------------------------------

- what kind of emails should be public:
  * public mailing lists
  * opensource development notification emails
  * NewsLetters
  * 

- what kind of emails should be encrypted ?
  * all personal communication
  * all mails from legacy email system not mentioned above
  * everything else.

- [?] defms would understand a metadata flag 

- [?] 
