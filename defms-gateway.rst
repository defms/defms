Gateway
=======

Function
--------

The defms gateway can retreive emails from an external POP or IMAP account 
provided by a third-party.

The gateway can also receive SMTP emails and forward them to the right 
Mailbox. In this scenario, defms replace the imap or pop protocol.


Libraries
---------

`<https://godoc.org/github.com/ipfs/go-ipfs>`_

`<https://github.com/NerdGGuy/go-imap>`_

`<https://golang.org/pkg/net/smtp/>`_

`<https://golang.org/pkg/net/mail/>`_


Flow
----

.. code::
   
                               .-------------------.  
                               | external mailbox  | 
                               '-------------------' 
                                         |   
                                        \ /  
       .-------------------.   .---------'---------.                   
       |   external smtp   |   |   external imap   |                   
       '-------------------'   '-------------------'                   
                 |                       |   
                \ /                     \ /  
    .------------'-----------------------'------------.
    |  .---------'---------.   .---------'---------.  | 
    |  |    go net/smtp    |   |    go-imap lib    |  |                
    |  '-------------------'   '-------------------'  |                
    |            '-----------.-----------'            |
    |                        |                        | 
    |                       \ /                       |
    |              .---------'---------.              |
    |              |    go net/mail    |              |
    |              '-------------------'              |
    |                        |                        | 
    |                       \ /                       |
    |              .---------'---------.              |
    |              |      go-ipfs      |              |
    |              '-------------------'              |
    '-------------------------------------------------'
                                               defms-gw


DEFMS email addresses
---------------------

@def.ms
