Flow design
===========

Receive an email from legacy email protocl (MX to DEFMS)
--------------------------------------------------------

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

comments:


Send an email to legacy email system (DEFMS to MX)
--------------------------------------------------

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

comments:


Send an email to a DEFMS mailbox (DEFMS to DEFMS)
-------------------------------------------------

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

comments:

