$Id$

DESCRIPTION
--------------------------
The Organic Group module lets you invite other users to a group. Sadly, those invites are not saved in the database.

This module saves OG invitations persistently in a database and lets you use them for messages like
"You have 3 pending group invites"

USAGE
-----
After installation of the Organic Groups and OG Invite module use og_invite_load_pending() to get all invitations for the current user.

EXAMPLE
-------
`<?php
// og/all page view needs to be extended for multiple arguments
if($og_invites = og_invite_load_pending()) {
  $link = l(format_plural(count($og_invites), '1 new group invite', '@count new group invites'), 'og/all/' . implode(',', array_keys($og_invites)));
}

print $link;
?>`

CREDITS
----------------------------
Authored and maintained by Jakob Stoeck <kontakt AT stoeck DOT it>