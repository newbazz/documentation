=============
Adding Events
=============

.. include:: ../../_robot.rst

Plone web sites have a built-in system for managing and showing calendar events.

Use the *Add new...* menu for a folder to add an event:



.. code:: robotframework
   :class: hidden

   *** Test Cases ***

   Show add new event menu
       Go to  ${PLONE_URL}

       Wait until element is visible
       ...  css=span.icon-plone-contentmenu-factories
       Click element  css=span.icon-plone-contentmenu-factories

       Wait until element is visible
       ...  css=#plone-contentmenu-factories li.plone-toolbar-submenu-header

       Mouse over  event
       Update element style  portal-footer  display  none

       Capture and crop page screenshot
       ...  ${CURDIR}/../../_robot/adding-events_add-menu.png
       ...  css=div.plone-toolbar-container
       ...  css=#plone-contentmenu-factories ul

.. figure:: ../../_robot/adding-events_add-menu.png
   :align: center
   :alt: add-new-menu.png


Select **Event** from the drop-down menu, and you'll see the rather large *Add Event* panel:



.. code:: robotframework
   :class: hidden

   *** Test Cases ***

   Show new event add form
       Page should contain element  event
       Click link  event

       Wait until element is visible
       ...  css=#mceu_16-body
       Capture and crop page screenshot
       ...  ${CURDIR}/../../_robot/adding-events_add-form.png
       ...  css=#content

.. figure:: ../../_robot/adding-events_add-form.png
   :align: center
   :alt: Adding events form

From the top, we have the following fields:

-  *Title* - **REQUIRED**
-  *Summary*
-  *Event starts* - **REQUIRED**
-  *Event ends* - **REQUIRED**
-  *Whole Day*
-  *Open End*
-  *Recurrence*
-  *Event Location*
-  *Attendees*
-  *Contact Name*
-  *Contact Email*
-  *Contact Phone*
-  *Event URL*
-  *Event body text* (visual editor panel)
-  Change note

.. note::

   Only three fields, title and start and end date and time, are required.

Although this is a large input panel, if you are in a hurry, type in the title and the start and end times and save.
Of course, if you have the other information, you should type it in.

One part of the panel needs a bit more explanation: the event start and end times.
Both these can be set using a handy pop-up calendar. This will show when you click on the date.

Setting an event to be "Whole day" will remove the start and end times.

But there are many more options: you can set an event to be "Open-ended" if you don't know when the end date is, or if it is an ongoing activity that you would still like to show as an event.

For repeating events, use the "recurrence" link. You can set when, and how often, your event will repeat: daily, weekly, every third Tuesday of the month until 2017, etcetera. You can specify that an event should repeat a certain number of times, or until a certain date.



.. note::

   **IMPORTANT:** Your event will not show on the main web site calendar until it has been **published**.
