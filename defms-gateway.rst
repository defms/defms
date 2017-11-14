Gateway
=======

Functioning
-----------

The defms gateway can retreive emails from an external POP or IMAP account 
provided by another third-party or DEFMS itself.

It use Getmail as retriever.
`<https://wiki.archlinux.org/index.php/Getmail>`_

The defms gateway can only use an external SMTP service to send emails to the 
usual mail network.

It use EXIM as a forwarding


DEFMS legacy email addresses
----------------------------

If you have a def.ms mail address and still wish to receive and send legacy 
emails we provide usual POP/IMAP and SMTP service integrated with our gateway.

Emails are deleted from the server as soon as gathered by the gateway and
written in IPFS.

* use DEFMS SMTP servers

  - EXIM mail `<https://wiki.archlinux.org/index.php/Exim>`_
  - Rate limiter

* use DEFMS POP/IMAP servers

  - Dovecot `<https://wiki.archlinux.org/index.php/Dovecot>`_
  - Rate limiter

