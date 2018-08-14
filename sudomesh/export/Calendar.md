---
title: Calendar
permalink: /Calendar/
---

Documentation for the new sudo room calendar.

-   View the calendar at <https://sudoroom.org/calendar>.
-   See (and search) event listings at <https://sudoroom.org/events/>
-   Submit a request for event hosting at <https://sudoroom.org/event-request/>
-   Import sudo room's calendar using an **ical** feed:
    -   Find ical here: <https://sudoroom.org/?ical=1>
    -   For Google Calendar, on the left-hand side, select the drop-down menu next to “Other calenders” and select “Add by URL”:
        -   Use this url: **<webcal://sudoroom.org/?ical=1>**

Features
--------

-   One-time events (requires user account w/ 'author' privileges): <https://sudoroom.org/wp-admin/edit.php?post_type=event>
    -   Standard event listing
-   Recurring events (requires user account w/ 'author' privileges): <https://sudoroom.org/wp-admin/edit.php?post_type=event-recurring>
    -   Generates many one-time events, which are deleted and re-created upon update of the recurring event.
-   Location management (requires user account w/ 'author' privileges): <https://sudoroom.org/wp-admin/edit.php?post_type=location>
    -   Locations can be fixed to a pre-defined list, or user-generated, with auto-complete recommendations for common locations.
    -   No good feature to merge location entries yet, seeking work-around for this.
-   Booking management (requires user account w/ 'author' privileges): <https://sudoroom.org/wp-admin/edit.php?post_type=event&page=events-manager-bookings>
    -   Each event can enable booking, which allows the author of that event to create tickets and receive reservations from users and non-users alike. All you need is an email address to book!
