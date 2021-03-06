.. _mailforwarding:

################
forwarding mails
################

configure forwarding
====================

You can use forwardings in the form of ``$MAILBOX@$USER.uber.space``. If you have :ref:`set up additional domains <mail-domains>`, ``$MAILBOX@$DOMAIN`` will also work.

.. warning::
    We do not forward mails with a :doc:`spam score >= 15 <mail-spam>`. This is crucial due to policy reasons at nearly any mail provider and makes sure the reputation of our servers stays fine.

Add forwards for a mailbox
--------------------------

You can configure forwardings with the ``uberspace mail user forward set <mailbox> <mail address>`` command.

To forward all mails from ``forwardme`` to ``mail@allcolorsarebeautiful.example`` run the following command:

.. code-block:: bash

 [isabell@philae ~]$ uberspace mail user forward set forwardme mail@allcolorsarebeautiful.example
 Mail to forwardme will be forwarded to mail@allcolorsarebeautiful.example.
 [isabell@philae ~]$

.. tip::
    ``uberspace mail user forward set`` overwrites existing configurations.

List existing forwards for a mailbox
------------------------------------

You can list your existing forwardings using the ``uberspace mail user forward list`` command, e.g. if you have setup fowardings for ``forwardme``:

.. code-block:: bash

 [isabell@philae ~]$ uberspace mail user forward list forwardme
 mail@allcolorsarebeautiful.example
 [isabell@philae ~]$

Delete forwards for a mailbox
-----------------------------

You can delete forwardings using the ``uberspace mail user forward del`` command. To delete forwarding for ``forwardme``, run the following command:

.. code-block:: bash

 [isabell@philae ~]$ uberspace mail user forward del forwardme
 Mail to forwardme will no longer be forwarded.
 [isabell@philae ~]$

spam filtering
==============

With enabled :doc:`spam filtering <mail-spam>` we do not forward mails with a spam score greater than 5. These mails get sorted into ``~/users/$MAILBOX/.Spam``.
