.. _initial-instance-setup:

==============================================
Konfiguration einer frischen OpenPetra Instanz
==============================================

.. NOTE::

    Baustelle: Diese Seite ist noch nicht fertiggestellt...

Wir gehen in dieser Anleitung davon aus, dass ein Dienstleister eine Instanz von OpenPetra für Sie bereitgestellt hat.
Zur Bereitstellung gehört eine **URL**, z.B. https://op012345.openpetra.com, und es wurde eine E-Mail an Sie versendet, mit einem Link, der das erstmalige Setzen des **Passwortes** für den ``SYSADMIN`` Benutzer erlaubt.

In einer selbst-installierten Umgebung von OpenPetra ist das voreingestellte Passwort für den Benutzer ``SYSADMIN`` das Wort: ``CHANGEME``, wobei die Großschreibung der Buchstaben des Passwortes zu beachten ist.

Passwort setzen
===============

Sie haben eine E-Mail erhalten, und klicken auf die dort angegebene Internetadresse.

Nun müssen Sie zweimal ein von Ihnen gewähltes Passwort eingeben.

Anmeldung
=========

Sie melden sich nun im Webbrowser auf Ihrer OpenPetra Instanz als Benutzer ``SYSADMIN`` an.
Sie benutzen das Passwort, das Sie eben gesetzt haben:

.. _figure-login_sysadmin:

.. figure:: images/login_sysadmin.png
   :scale: 50%

   Anmeldung als Benutzer ``SYSADMIN``

Einen nicht-administrativen Benutzer anlegen
============================================

Es ist nicht zu empfehlen, die Tagesaufgaben in OpenPetra mit dem Benutzer ``SYSADMIN`` zu erledigen. Daher hat der Benutzer SYSADMIN auch keine Berechtigungen z.B. im Partner- oder Finanz-Modul.

Stattdessen sollten Sie einen Benutzer anlegen, der auf die Finanz- und Adressdaten zugreifen darf, aber keine Rechte zum Anlegen weiterer Benutzer hat.
Selbstverständlich können Sie auch für andere Mitarbeiter in Ihrem Team weitere Benutzer anlegen.

Dazu gehen Sie im seitlichen Menü auf *System einrichten*, und wählen *Benutzer*.

.. _figure-manage_users:

.. figure:: images/manage_users.png
   :scale: 50%

   Benutzer verwalten

Hier wählen Sie den Schalter *Hinzufügen*, um weitere Benutzer hinzuzufügen.

Es folgt dieser Dialog:

.. _figure-add_user2:

.. figure:: images/add_user.png
   :scale: 50%

   Neuen Benutzer anlegen

Hier geben Sie den Benutzernamen, die E-Mail Adresse, ggf. den Vornamen und den Nachnamen des Benutzers, und die Berechtigungen an.

Per Voreinstellungen sind die Module *Finance - Basic User*, *Finance - Reporting User*, *Partner User Level Access* schon ausgewählt. Für den Buchhalter in Ihrem Team sollte auch *Finance - Intermediate User* und *Finance - Advanced User* gewählt werden.

Dem neuen Benutzer wird eine E-Mail zugeschickt, um den Zugang zu OpenPetra mitzuteilen. In der E-Mail ist auch ein Link zum Setzen des Passwortes für diesen Benutzer.

.. _ein-hauptbuch-anlegen:

Ein Hauptbuch anlegen
=====================

Nun melden Sie sich mit dem gerade erstellten Benutzer an, um das Hauptbuch anzulegen.

Gehen Sie im seitlichen Menü auf *Finanzen einrichten*, und wählen *Hauptbuch*.

Die Liste der Hauptbücher ist erstmal leer:

.. _figure-ledger_list:

.. figure:: images/ledger_list.png
   :scale: 50%

   Liste der Hauptbücher

Sie müssen für jeden Verein ein Hauptbuch anlegen, im Normalfall brauchen Sie also nur ein Hauptbuch.

Wählen Sie nun den Schalter *Hinzufügen*, um ein Hauptbuch anzulegen.

Es folgt dieser Dialog:

.. _figure-add_ledger:

.. figure:: images/add_ledger.png
   :scale: 50%

   Neues Hauptbuch anlegen

Danach sollten Sie sich mit Ihrem Benutzer abmelden, und nochmal neu anmelden, um die Zugriffsrechte auf das neue Hauptbuch zu erhalten (siehe auch `Fehler 291 <https://github.com/openpetra/openpetra/issues/291>`_).

Sie können die aktuellen Daten des neuen Hauptbuches so anzeigen lassen: Gehen Sie im seitlichen Menü auf *Buchhaltung*, und wählen *Hauptbuch*, und dann unter der *Übersicht* wählen Sie *Hauptbuch Statusinformationen*.

Dann erscheint eine Ansicht wie diese:

.. _figure-ledger_info:

.. figure:: images/ledger_info.png
   :scale: 50%

   Details des Hauptbuches

