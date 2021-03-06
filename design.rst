
Design
======

Objects
-------

thread objects
""""""""""""""

Originator fields ( rfc5322#section-3.6.2 )

.. code::

    from            =   "From:" mailbox-list CRLF
    sender          =   "Sender:" mailbox CRLF
    reply-to        =   "Reply-To:" address-list CRLF


Destination Address Fields ( rfc5322#section-3.6.3 )

.. code::

    to              =   "To:" address-list CRLF
    cc              =   "Cc:" address-list CRLF
    bcc             =   "Bcc:" [address-list / CFWS] CRLF


Informational Fields ( rfc5322#section-3.6.5 )

.. code::

   subject         =   "Subject:" unstructured CRLF
   comments        =   "Comments:" unstructured CRLF
   keywords        =   "Keywords:" phrase \*("," phrase) CRLF


The Identification Fields ( rfc5322#section-3.6.3 ) are not implemented here. 
Instead, the thread object contains a list of sorted hash pointing to the 
different messages.


mail objects
""""""""""""


data replication model
""""""""""""""""""""""

- | [ ] ditributed centralized mono db
  | (1 database owning all mailboxes)

  * security issues
  * scalability issue
  * no replication issue


- | [ ] user centric mailbox database
  | (1 database per users mailbox)

  * replication issues (replication only between user device and service
    provider is not enough)
  * no scalability issue
  * easier security
  * sounds shitty


- | [X] thread centric database
  | (1 database per email thread)

  * reduced footprint
  * replication is ideal (between sender and receivers for all exchanges)
  * more complex to implement
  * more security possibilities (more complex?)



Flow design
-----------


Receive from legacy (MX to DEFMS)
""""""""""""""""""""""""""""""""""

.. code::

        .------.
        | IMAP |
        '------'
           |
          \ /
           '
    .---------------. 
    | defms-gateway | 
    '---------------' 
           |
          \ /
           '
    .---------------. 
    | defms mailbox | 
    '---------------' 
           |
          \ /
           '
    .--------------. 
    | defms-daemon | 
    '--------------' 
           |
          \ /
           '
        .------. 
        | IPFS | 
        '------' 


Send to legacy (DEFMS to MX)
""""""""""""""""""""""""""""

.. code::

    .--------------.      
    | defms-daemon |  ---------------. 
    '--------------'                 |
           |                         | 
          \ /                       \ /
           '                         ' 
    .---------------.         .---------------.
    | defms-gateway |         | defms-sentbox |
    '---------------'         '---------------'
           |                         |    
          \ /                       \ /   
           '                         '    
        .------.                  .------.
        | SMTP |                  | IPFS |
        '------'                  '------'


Send to DEFMS (DEFMS to DEFMS)
""""""""""""""""""""""""""""""

.. code::

    .--------------. 
    | defms-daemon | 
    '--------------' 
           |
          \ /
           '
    .---------------. 
    | defms mailbox | 
    '---------------' 
           |
          \ /
           '
    .--------------. 
    | defms-daemon | 
    '--------------' 
