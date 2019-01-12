========================================
Konfiguration eines frischen Hauptbuches
========================================

.. NOTE::

    Baustelle: Diese Seite ist noch nicht fertiggestellt...

Wir gehen in dieser Anleitung davon aus, dass das Hauptbuch schon eingerichtet worden ist (siehe :ref:`ein-hauptbuch-anlegen`).

Kontenrahmen einrichten
=======================

Gehen Sie im seitlichen Menü auf *Buchhaltung*, und wählen *Konfiguration*, und dann unter *Hauptbuch* wählen Sie *Kontenrahmen verwalten*.

.. _figure-account_edit:

.. figure:: images/account_edit.png
   :scale: 50%

   Kontenstruktur

Sie können die Kontenstruktur in einer Text Datei exportieren, in dem Sie auf den Schalter *Exportieren* klicken. Die Datei können Sie lokal speichern, und in einem Text Editor Ihrer Wahl bearbeiten.

Sie können neue Konten einfügen, und Konten, die noch nicht bebucht sind, bearbeiten oder entfernen.

Die Datei kann dann mit dem Schalter *Importieren* wieder ins System geladen werden.

Eine Beispiel-Datei sieht so aus:

::

   RootNodeInternal:
       BAL SHT:{active=True, type=Asset, debitcredit=debit, validcc=All, shortdesc=Balance Sheet}
           ASSETS:{shortdesc=Total Assets}
               CASH:{shortdesc=Cash & Bank, longdesc=Bank, locallongdesc=Cash & Bank}
                   6000S:{shortdesc=Petty Cash Accounts (Total)}
                       6000:{validcc=Local, shortdesc=Petty Cash}
                   6200S:{shortdesc=Bank Accounts(Total Operational)}
                       6200:{validcc=Local, shortdesc=Bank Accounts Operational, bankaccount=true}
                   6400S:{shortdesc=Bank Accounts (Total Deposit)}
                       6400:{validcc=Local, shortdesc=Bank Accounts Deposit}
               6500S:{shortdesc=Investments, longdesc=INVESTMENTS, locallongdesc=Investments}
                   6500:{validcc=Local, longdesc="Investments, General"}
               DRS:{shortdesc="Debtors:Due within one year"}
                   6800S:{shortdesc=Accounts Receivable, longdesc=Accounts Receivable within one year, locallongdesc=Accounts Receivable}
                       6800:{validcc=Local}
                   6900S:{shortdesc=Accounts Receivable Funds, longdesc=Accounts Receivable from other Funds within one year, locallongdesc=Accounts Receivable Funds}
                       6900:{validcc=Local}
                   6700S:{shortdesc=Prepaid Expenses}
                       6700:{validcc=Local, shortdesc=Prepaid Expense}
                   6600S:{shortdesc=Provision for Dbtful Debts, longdesc=Provision for Dbtful Debts (Total), locallongdesc=Provision for Dbtful Debts}
                       6600:{type=Liability, debitcredit=credit, validcc=Local, shortdesc=Provision for Doubtful Debts}
               DRS LNG:{shortdesc="Debtors:Due in more than 1 year", longdesc="Debtors:Due in more than one year", locallongdesc="Debtors:Due in more than 1 year"}
                   7000S:{shortdesc=Long Term Loans Receivable}
                       7000:{validcc=Local, locallongdesc=Long Term Loans Receivable}
                       7010:{validcc=Local, shortdesc=Deposits (landlords etc)}
                   7100S:{shortdesc=Long Term Loans Receivable Funds, longdesc=Long Term Loans Receivable from other Funds, locallongdesc=Long Term Loans Receivable Funds}
                       7100:{validcc=Local}
               STOCK:{shortdesc=Stock}
                   7200S:{shortdesc=Stock Inventory}
                       7200:{validcc=Local}
               FA:{shortdesc=Fixed Assets}
                   7300S:{shortdesc=Equipment}
                       7300:{validcc=Local, shortdesc="Equipment, General", longdesc=Equipment, locallongdesc="Equipment, General"}
                       7311:{validcc=Local, shortdesc=Business Equipment}
                       7312:{validcc=Local, shortdesc=Vehicles}
                       7313:{validcc=Local, shortdesc=Computer Equipment}
                       7314:{validcc=Local, shortdesc=Audio Visual Equipment}
                   7400S:{shortdesc=Land & Buildings}
                       7400:{validcc=Local}
                   7500S:{type=Liability, shortdesc="Accum. Depreciation: Equipment"}
                       7500:{debitcredit=credit, validcc=Local, shortdesc=Accumulated Depreciation Equip}
                   7600S:{shortdesc="Accum. Depr.:  Land & Buildings", longdesc="Accum. Depreciation:  Land & Buildings", locallongdesc="Accum. Depr.:  Land & Buildings"}
                       7600:{type=Liability, debitcredit=credit, validcc=Local, shortdesc=Land and Buildings}
           LIABS:{type=Liability, debitcredit=credit, shortdesc=Total Liabilities}
               8200S:{shortdesc=Suspense Accounts, longdesc=Suspense Accounts (Total), locallongdesc=Suspense Accounts}
                   8200:{validcc=Local, shortdesc=Suspense Account}
               ILT:{shortdesc=Inter Ledger Transfer Total}
               CRS:{shortdesc="Creditors:Due within one year"}
                   CRS CTRL:{shortdesc=Creditor's Control}
                   8500S:{validcc=Local, shortdesc=International Clearing House}
                       8500:
                       8500X:{shortdesc=Non-ICH Clearing}
                   9100S:{shortdesc=Accounts Payable, longdesc=Accounts Payable within one year, locallongdesc=Accounts Payable}
                       9100:{validcc=Local}
                   9200S:{shortdesc=Accounts Payable Funds, longdesc=Accounts Payable to other Funds within one year, locallongdesc=Accounts Payable Funds}
                       9200:{validcc=Local}
                   8100S:{shortdesc=Stewardship Clearing}
                       8100:{validcc=Local}
               CRS LNG:{shortdesc="Creditors:Due in more than 1 year", longdesc="Creditors:Due in more than one year", locallongdesc="Creditors:Due in more than 1 year"}
                   9300S:{shortdesc=Long Term Loans Payable}
                       9300:{validcc=Local, locallongdesc=Long Term Loans Payable}
                   9400S:{shortdesc=Long Term Loans Payable Funds, longdesc=Long Term Loans Payable to other Funds, locallongdesc=Long Term Loans Payable Funds}
                       9400:{validcc=Local}
                   9500S:{shortdesc=Provisions}
                       9500:{validcc=Local, locallongdesc=Provisions}
               9000S:{shortdesc=Deferred income, longdesc=Deferred Income(Total), locallongdesc=Deferred Income (Total)}
                   9000:{validcc=Local, longdesc=Defrerred Income, locallongdesc=Deferred Income}
               9800S:{shortdesc=Internal Transfer}
                   9800:{validcc=Local}
           RET EARN:{type=Equity, debitcredit=credit, shortdesc=Equity}
               9700S:{shortdesc=Brought Forward 1st January, longdesc=Balance Brought Forward 1st January, locallongdesc=Brought Forward 1st January}
                   9700:
               PL:{type=Income, shortdesc=Surplus or Deficit}
                   INC:{shortdesc=Total Income}
                       GIFT:{shortdesc=Gift Income}
                           0100S:{shortdesc="Support Gifts: local"}
                               0100:{shortdesc="Support Gifts: Local"}
                           0200S:{shortdesc="Fund Gifts: Local"}
                               0200:
                               0210:{shortdesc=Subscriptions and Fees}
                           0300S:{shortdesc=Undesignated Gifts}
                               0300:
                           1100S:{shortdesc="Support Gifts: Foreign"}
                               1100:{shortdesc="Support Gifts, Foreign", longdesc="Support Gifts: Foreign (ie via other funds)", localdesc="Support Gifts: Foreign", locallongdesc="Support Gifts: Foreign"}
                           1200S:{shortdesc="Fund Gifts: Foreign"}
                               1200:
                           0400S:{shortdesc="Project Gifts: Local", longdesc="Project Gifts: Local (Total)", locallongdesc="Project Gifts: Local"}
                               0400:
                           1900S:{shortdesc="Foreign Income: Unidentified"}
                               1900:
                           1400S:{shortdesc="Project Gifts: Foreign", longdesc="Project Gifts: Foreign (Total)", locallongdesc="Project Gifts: Foreign"}
                               1400:
                       LIT SALE:{shortdesc=Literature Sales, longdesc=Total Literature Sales, locallongdesc=Literature Sales}
                           2100S:{shortdesc=Literature Sales external}
                               2100:{locallongdesc=Literature Sales external}
                           2200S:{shortdesc=Literature Sales internal, longdesc=Literature Sales internal (Total), locallongdesc=Literature Sales internal}
                               2200:
                       STC INC:{shortdesc=Short Term Event Income}
                           0900S:{shortdesc=Event Income for Others}
                               0900:
                               0910S:{shortdesc=Event Supplements for Others, longdesc=Event Supplements for Others (Total), locallongdesc=Event Supplements for Others}
                                   0910:
                               0980S:{shortdesc=Event Supplements, longdesc=Event Supplements (Total), locallongdesc=Event Supplements}
                                   0980:
                           1000S:{shortdesc=Local Event Income, longdesc=Local Event Income (Total), locallongdesc=Local Event Income}
                               1000:
                               1010S:{shortdesc=Local Event Supplements, longdesc=Local Event Supplements (Total), locallongdesc=Local Event Supplements}
                                   1010:
                       OTHINC:{shortdesc=Other Income}
                           3100S:{shortdesc=Interest, longdesc=Interest (Total), locallongdesc=Interest}
                               3100:{shortdesc=Interest Earned}
                           3200S:{shortdesc=Central Services, longdesc=Central Services (Total), locallongdesc=Central Services}
                               3200:
                           3300S:{shortdesc=Grants from Other Funds, longdesc=Grants from Other Funds (Total), locallongdesc=Grants from Other Funds}
                               3300:
                           3400S:{shortdesc=Admin Grant Income, longdesc=Admin Grant Income (Total), locallongdesc=Admin Grant Income}
                               3400:
                           3700S:{longdesc=Other Income (Total), locallongdesc=Other Income}
                               3700:
                               3710:{shortdesc=Registration Fees}
                               3720:{shortdesc=Sale of Fixed Assets}
                               3730:{shortdesc=Gifts in Kind}
                               3740:{shortdesc=Other Sales}
                   EXP:{type=Expense, debitcredit=debit, shortdesc=Total Expenditure}
                       4600S:{shortdesc=Cost of Sales}
                           4600:{shortdesc="Cost of Sales, General", longdesc=Cost of Sales, locallongdesc="Cost of Sales, General"}
                       4100S:{shortdesc=Ministry, longdesc=Ministry (Total), locallongdesc=Ministry}
                           4100:{shortdesc="Ministry: General", longdesc=Ministry, locallongdesc="Ministry: General"}
                           4110S:{shortdesc=Literature, longdesc=Literature (Total), locallongdesc=Literature}
                               4110:{shortdesc="Literature: General", longdesc=Literature, locallongdesc="Literature: General"}
                               4111:{shortdesc=Literature For Sale}
                               4112:{shortdesc=Literature for free Distribution}
                               4113:{shortdesc=Freight Inward (lit.)}
                               4114:{shortdesc=Carriage Out (lit.)}
                           4120S:{shortdesc=Relief of Need, longdesc=Relief of Need (Total), locallongdesc=Relief of Need}
                               4120:
                           4130S:{shortdesc=Project Expenses, longdesc=Project Expenses (Total), locallongdesc=Project Expenses}
                           4140S:{shortdesc=AV (for outreach), longdesc=AV (for outreach) (Total), locallongdesc=AV (for outreach)}
                               4140:
                           4180S:{shortdesc=Home Event Expenses, longdesc=Home Event Expenses (Total), locallongdesc=Home Event Expenses}
                               4180:
                       4200S:{shortdesc=Administration, longdesc=Administration (Total), locallongdesc=Administration}
                           4200:{shortdesc="Administration: General", longdesc=Administration, locallongdesc="Administration: General"}
                           4202:{shortdesc=Business Hospitality/Meals}
                           4203:{shortdesc=Subscriptions (Payable), longdesc=Subscriptions, localdesc=Subscriptions Payable, locallongdesc=Subscriptions Payable}
                           4210S:{shortdesc=Office Rent & Utilities, longdesc=Office Rent & Utilities (Total), locallongdesc=Office Rent & Utilities}
                               4210:{shortdesc="Office Rent & Utilities, General", longdesc=Office Rent & Utilities, locallongdesc="Office Rent & Utilities, General"}
                               4211:{shortdesc=Rent}
                               4212:{shortdesc=Gas}
                               4213:{shortdesc=Electricity}
                               4214:{shortdesc=Heating Oil}
                               4215:{shortdesc=Water & Sewage}
                               4216:{shortdesc=Insurance}
                           4220S:{shortdesc=Communication, longdesc=Communication (Total), locallongdesc=Communication}
                               4220:{shortdesc="Communication, General", longdesc=COMMUNICATION, locallongdesc="Communication, General"}
                               4221:{shortdesc=Telephone}
                               4222:{shortdesc=Fax}
                               4223:{shortdesc=E-mail}
                               4224:{shortdesc=Postage}
                               4225:{shortdesc=Prayer Letter postage}
                           4230S:{shortdesc=Office Supplies, longdesc=Office Supplies (Total), locallongdesc=Office Supplies}
                               4230:{shortdesc="Office Supplies, General", longdesc=OFFICE SUPPLIES, locallongdesc="Office Supplies, General"}
                               4231:{shortdesc=Stationery}
                               4232:{shortdesc=Computer Expense}
                               4233:{shortdesc=Printer/copier supplies}
                               4234:{shortdesc=Photocopying}
                           4240S:{shortdesc="Equipment, Maint. & Repairs", longdesc="Equipment, Maintenance & Repairs (Total)", locallongdesc="Equipment, Maint. & Repairs"}
                               4240:{shortdesc="Equip. Maint. & Repairs, General", longdesc=EQUIP/MAINT & REPAIRS, locallongdesc="Equip. Maint. & Repairs, General"}
                               4241:{shortdesc=Service Contracts}
                               4242:{shortdesc=Equipment Leasing}
                           4250S:{shortdesc=Building Repairs & Maint., longdesc=Building Repairs & Maintenance (Total), locallongdesc=Building Repairs & Maint.}
                               4250:{shortdesc=Building Repairs & Maint, longdesc=BUILDING REPAIRS AND MAINTENANCE, locallongdesc=Building Repairs & Maint}
                           4260S:{shortdesc=Professional Fees, longdesc=Professional Fees (Total), locallongdesc=Professional Fees}
                               4260:{shortdesc="Professional Fees, General", longdesc=PROFESSIONAL FEES, locallongdesc="Professional Fees, General"}
                               4261:{shortdesc=Legal Fees}
                               4262:{shortdesc=Consultancy}
                               4263:{shortdesc=Audit Fees}
                           4280S:{shortdesc=Home Event Admin., longdesc=Home Event Administration (Total), locallongdesc=Home Event Admin.}
                               4280:{longdesc=HOME Event ADMIN.}
                       4300S:{shortdesc=Personnel, longdesc=PERSONNEL, locallongdesc=Personnel}
                           4300:{shortdesc="Personnel, General"}
                           4310S:{shortdesc=Salaries/Allow. & Payroll Taxes, longdesc=Salaries/Allowances & Payroll Taxes (Total), locallongdesc=Salaries/Allow. & Payroll Taxes}
                           4330S:{shortdesc=Pension/Insurance, longdesc=Pension/Insurance (Total), locallongdesc=Pension/Insurance}
                               4330:{shortdesc="Pension/Insurance, General", longdesc=PENSION/INSURANCE, locallongdesc="Pension/Insurance, General"}
                               4331:{shortdesc=Pension}
                               4332:{shortdesc=Insurance}
                           4340S:{shortdesc=Housing, longdesc=Housing (Total), locallongdesc=Housing}
                               4340:{longdesc=HOUSING}
                           4350S:{shortdesc=Team Living, longdesc=Team Living (Total), locallongdesc=Team Living}
                               4350:{longdesc=TEAM LIVING}
                           4360S:{shortdesc=Personal Travel, longdesc=Personal Travel (Total), locallongdesc=Personal Travel}
                               4360:{longdesc=PERSONAL TRAVEL}
                           4370S:{shortdesc=Medical Expenses, longdesc=Medical Expenses (Total), locallongdesc=Medical Expenses}
                               4370:{longdesc=MEDICAL EXPENSES}
                           4380S:{shortdesc=Home Event Personnel, longdesc=Home Event Personnel (Total), locallongdesc=Home Event Personnel}
                               4380:{longdesc=HOME Event PERSONNEL}
                           4390S:{shortdesc=Further Education/Training, longdesc=Further Education/Training (Total), locallongdesc=Further Education/Training}
                               4390:{longdesc=FURTHER EDUCATION/TRAINING}
                       4400S:{shortdesc=Business Travel, longdesc=BUSINESS TRAVEL, locallongdesc=Business Travel}
                           4400:{shortdesc="Business Travel, General", longdesc=Business Travel, locallongdesc="Business Travel, General"}
                           4410S:{shortdesc=Public Transport, longdesc=Public Transport (Total), locallongdesc=Public Transport}
                               4410:{longdesc=PUBLIC TRANSPORT}
                           4420S:{shortdesc=Vehicle, longdesc=Vehicle (Total), locallongdesc=Vehicle}
                               4420:{shortdesc="Vehicle, General", longdesc=VEHICLE, locallongdesc="Vehicle, General"}
                               4421:{shortdesc=Vehicle Maintenance}
                               4422:{shortdesc=Vehicle Insurance/Tax, longdesc=Vehicle, locallongdesc=Vehicle Insurance/Tax}
                               4423:{shortdesc=Vehicle Fuel}
                           4430S:{shortdesc=Air, longdesc=Air (Total), locallongdesc=Air}
                               4430:{longdesc=AIR}
                           4480S:{shortdesc=Home Event Travel, longdesc=Home Event Travel (Total), locallongdesc=Home Event Travel}
                               4480:{longdesc=HOME Event TRAVEL}
                       4500S:{shortdesc=Public Relations, longdesc=PUBLIC RELATIONS, locallongdesc=Public Relations}
                           4500:{shortdesc="Public Relations, General", longdesc=Public Relations, locallongdesc="Public Relations, General"}
                           4510S:{shortdesc=Advertising, longdesc=Advertising (Total), locallongdesc=Advertising}
                               4510:{longdesc=ADVERTSIING}
                           4520S:{shortdesc=Newsletters, longdesc=Newsletters (Total), locallongdesc=Newsletters}
                               4520:{longdesc=NEWSLETTERS}
                           4530S:{shortdesc=Brochures, longdesc=Brochures (Total), locallongdesc=Brochures}
                               4530:{longdesc=BROCHURES}
                           4550S:{shortdesc=AV Productions, longdesc=AV Productions (Total), locallongdesc=AV Productions}
                               4550:{shortdesc="AV Productions, General", longdesc=AV PRODUCTIONS, locallongdesc="AV Productions, General"}
                               4551:{shortdesc=Videos}
                               4552:{shortdesc=Slide Presentations}
                               4553:{shortdesc=Casettes}
                       OTHEXP:{shortdesc=Other Expenditure}
                           4800S:{shortdesc=Grants to Other Funds, longdesc=Grants to Other Funds (Total), locallongdesc=Grants to Other Funds}
                               4800:
                           4900S:{shortdesc=Admin Grant Expense, longdesc=Admin Grant Expense (Total), locallongdesc=Admin Grant Expense}
                               4900:
                           5000S:{shortdesc=Financial  and Other, longdesc=Financial  and Other (Total), locallongdesc=Financial  and Other}
                               5000:{shortdesc="Financial and Other, General", longdesc=Financial and Other, locallongdesc="Financial and Other, General"}
                               5003:{shortdesc=Currency Revaluation}
                               5010S:{shortdesc=Equipment Acquired, longdesc=Equipment Acquired (Total), locallongdesc=Equipment Acquired}
                                   5010:{shortdesc="Equipment Acquired, General", longdesc=EQUIPMENT ACQUIRED, locallongdesc="Equipment Acquired, General"}
                                   5011:{shortdesc=Business Equipment, locallongdesc=Business Equi[ment}
                                   5012:{shortdesc=Vehicle}
                                   5013:{shortdesc=Computer Equipment, longdesc=Computer Exuipment, locallongdesc=Computer Equipment}
                                   5014:{shortdesc=Audio Visial Equipment}
                               5020S:{shortdesc=Depreciation, longdesc=Depreciation (Total), locallongdesc=Depreciation}
                                   5020:{longdesc=DEPRECIATION}
                               5030S:{shortdesc=Interest & Bank Charges, longdesc=Interest & Bank Charges (Total), locallongdesc=Interest & Bank Charges}
                                   5030:{longdesc=INTEREST & BANK CHARGES}
                               5040S:{shortdesc=Bad and Doubtful Debts, longdesc=Bad and Doubtful Debts (Total), locallongdesc=Bad and Doubtful Debts}
                                   5040:{shortdesc="Bad and Doubtful Debts, General", longdesc=Bad and Doubtful Debts, locallongdesc="Bad and Doubtful Debts, General"}
                                   5041:{shortdesc=Bad Debts}
                                   5042:{shortdesc=Doubtful Debts}
                               5050S:{shortdesc=Prior Year Adjustments, longdesc=Prior Year Adjustments (Total), locallongdesc=Prior Year Adjustments}
                                   5050:{longdesc=PRIOR YEAR ADJUSTMENTS}
                           5100S:{shortdesc=Conference Expenses}
                               5100:
                           5200S:{shortdesc=Event Fees to Other Funds}
                               5200:
                           5400S:{shortdesc="Foreign Expenses: Unidentified"}
                               5400:
                           5500S:{shortdesc=Recharges to Other Funds, longdesc=Recharges to Other Funds (Total), locallongdesc=Recharges to Other Funds}
                               5500:
                               5501:{shortdesc=Direct Transfers, longdesc=DIRECT TRANSFERS, locallongdesc=Direct Transfers}
                           5600S:{shortdesc=ICH Settlement, longdesc=ICH Settlement (Total), locallongdesc=ICH Settlement}
                               5600:{shortdesc=ICH Settlement Transfers}
                               5601:


Kostenstellen einrichten
========================

Gehen Sie im seitlichen Menü auf *Buchhaltung*, und wählen *Konfiguration*, und dann unter *Hauptbuch* wählen Sie *Kostenstellen verwalten*.

.. _figure-costcentre_edit:

.. figure:: images/costcentre_edit.png
   :scale: 50%

   Kostenstellen

Sie können die Kostenstellen in einer Text Datei exportieren, in dem Sie auf den Schalter *Exportieren* klicken. Die Datei können Sie lokal speichern, und in einem Text Editor Ihrer Wahl bearbeiten.

Sie können neue Kostenstellen einfügen, und Kostenstellen, die noch nicht bebucht sind, bearbeiten oder entfernen.

Die Datei kann dann mit dem Schalter *Importieren* wieder ins System geladen werden.

Eine Beispiel-Datei sieht so aus:

::

    RootNodeInternal:
        [10]:{descr=[Mein Verein e.V.], active=True, type=Local}
            1000S:{descr=Mein Verein e.V.}
                1000:{descr="Mein Verein e.V., General"}
            ILT:{descr=Inter Ledger Transfer Total}
                0400:{descr=International Clearing House, type=Foreign}
                3500:{descr=Switzerland, type=Foreign}
                4300:{descr=Germany, type=Foreign}
                7300:{descr=Kenya, type=Foreign}
                9500:{descr=Global Impact Fund, type=Foreign}

Verwendungszwecke einrichten
============================

Verwendungszwecke sind dazu da, um Spenden direkt einem Konto und einer Kostenstelle zuzuordnen, über ein leicht zu merkendes Kürzel.

Zum Beispiel kann man bestimmen, dass Spenden an den Verwendungszweck SPENDE/PATENSCHAFTEN immer auf die Kostenstelle 101000 Patenschaften und das Konto 0100 Patenschaften gebucht werden.

Hierbei ist SPENDE die Gruppe, und PATENSCHAFTEN das Detail.

Gehen Sie im seitlichen Menü auf *Buchhaltung*, und wählen *Konfiguration*, und dann unter *Spenden* wählen Sie *Verwendungszwecke verwalten*.

.. _figure-motivations_list:

.. figure:: images/motivations_list.png
   :scale: 50%

   Verwendungszwecke verwalten

Verwendungszwecke werden gruppiert, in diesem Beispiel heißt die Gruppe GIFT. Sie können die Gruppe löschen, indem Sie auf das Symbol mit dem Schraubenschlüssel klicken.

Dann erscheint dieser Dialog:

.. _figure-motivation_group_edit:

.. figure:: images/motivation_group_edit.png
   :scale: 50%

   Verwendungszweck-Gruppe bearbeiten

Um diese Gruppe und alle ihre Details zu löschen, klicken Sie den roten *Löschen* Schalter.

Nun können Sie eine neue Gruppe mit Namen SPENDEN anlegen, in dem Sie auf den Schalter mit der Beschriftung *Hinzufügen* klicken.

Um Verwendungszweck-Details einzufügen, klicken Sie auf die Gruppe, und dann klappt die Detailansicht auf. Dort ist ein weiterer *Hinzufügen* Schalter, der nun erlaubt, ein Detail anzulegen.

Der Dialog für das Hinzufügen eines Verwendungszweck-Details sieht so aus:

.. _figure-motivation_detail_add:

.. figure:: images/motivation_detail_add.png
   :scale: 50%

   Verwendungszweck-Detail hinzufügen

Startsaldo buchen
=================

Wenn Sie einen bestehenden Verein mit OpenPetra verwalten wollen, müssen die Konten mit einem Startsaldo bebucht werden.

Dazu gehen Sie im seitlichen Menü auf *Buchhaltung*, und wählen *Hauptbuch*, und dann unter *Buchungen im Hauptbuch pflegen* wählen Sie *Buchungen verwalten*.

.. _figure-gl_batches_list_empty:

.. figure:: images/gl_batches_list_empty.png
   :scale: 50%

   Leere Liste der Stapel von Hauptbuch-Buchungen

Zu Anfang ist die Liste der Stapel von Hauptbuch-Buchungen noch leer.

Sie klicken nun aber auf den Schalter *Hinzufügen*, und legen einen neuen Stapel an:

.. _figure-gl_batch_add:

.. figure:: images/gl_batch_add.png
   :scale: 50%

   Neuen Stapel anlegen

Die Stapelnummer ist vorgegeben, unveränderbar und fortlaufend.

Den Namen und das Datum des Stapels können Sie selber vergeben. Das Datum muss in einem offenen Monat liegen.

Wenn Sie auf den Schalter *Übernehmen* klicken, wird der Stapel angelegt. Nun klicken Sie auf den Namen des Stapels, und Sie gelangen in eine Ansicht, wo die Transaktionen innerhalb des Stapels gezeigt werden.
OpenPetra arbeitet mit doppelter Buchführung, das bedeutet es gibt zu jeder Transaktion mindestens eine Gegenbuchung. Am Ende müssen sich die Debit- und Kredit-Transaktionen gegenüber stehen und ausgleichen.

Das sieht dann so aus:

.. _figure-gl_transaction_list_empty:

.. figure:: images/gl_transaction_list_empty.png
   :scale: 50%

   Neuer Stapel, noch ohne Transaktionen

Klicken Sie nun auf den Schalter *Hinzufügen* innerhalb des Stapels, um eine Transaktion anzulegen.

Hier können Sie nun eine Transaktion anlegen, um den Kontostand auf einem der Bankkonten des Vereins zu buchen. In unserem Beispiel sind es 31088,99 Euro Haben auf dem Konto der Sparkasse. Wir müssen eine Debit-Buchung auf das Bankkonto erstellen, den Bankkonten werden als Debitkonten geführt.

.. _figure-gl_transaction_add_debit:

.. figure:: images/gl_transaction_add_debit.png
   :scale: 50%

   Neue Debit-Transaktion

Nun müssen wir auch eine Gegenbuchung anlegen. Für den Übertrag von Beträgen aus dem vorherigen Jahr gibt es das Konto 9700, mit dem englischen Namen "Brought Forward 1st January", als der "Übertrag am 1. Januar". Dort buchen wir den Kredit-Betrag hin.

Natürlich kann man das Geld noch auf verschiedene andere Konten verteilen, wenn man Überträge erhalten will.

.. _figure-gl_transaction_add_credit:

.. figure:: images/gl_transaction_add_credit.png
   :scale: 50%

   Neue Kredit-Transaktion

Nun können Sie in der Ansicht der Transaktionsliste des neuen Stapels auf den Schalter *Stapel prüfen* klicken, um zu sehen, wie die Salden der betroffenen Konten aussehen würden, wenn Sie nun buchen würden. Das hilft, wenn man sich mit Debit und Kredit nicht so ganz sicher ist...

In unserem Fall sieht es so aus:

.. _figure-gl_test_post:

.. figure:: images/gl_test_post.png
   :scale: 50%

   Prüfe den Stapel und die Salden der betroffenen Konten

Das Ergebnis ist, dass wir 31088,99 Euro auf dem Bankkonto haben, und 31088,99 Euro im Übertragskonto.

Nun können Sie die Buchung tatsächlich durchführen, in dem Sie auf den Schalter *Stapel buchen* klicken.

Damit wird die Buchung durchgeführt und festgeschrieben, und evtl. Fehler können nur durch Umbuchungen korrigiert werden.

