---
id: access-control-lists
title: Access Control Lists
---

Access Control Lists (ACL) are used to limit users' access to the web interface
Centreon via miscellaneous rules. The ACL are also used to create multiple user
profiles making possible to focalise on a precise set of resources.

> The management of access checks is a function specific to Centreon, the export
> of the configuration to the monitoring engine is not necessary to enable them.

Access groups are groups containing the Centreon users. For each access group,
it is possible to define three types of access:

- Access filters to resources serve to limit access to Centreon objects
(hosts, services, etc.),
- Access filters to menus serve to limit access to Centreon menus,
- Access filters on actions serve to limit access to actions that the user can
undertake on a monitoring engine or on the resources themselves (program a
downtime, stop a monitoring engine, etc.).

> A user can belong to several access groups thus making it possible to add
> together all the access authorizations.

The ACLs respect very strict rules:

- Centreon administrators are not subject to ACLs (property of the contact),
- A user (non-administrator) who does not belong to any access group has no
right on the monitoring platform (screen empty after logging in),
- The ACLs are recalculated every minute; this why it is sometimes necessary
to wait a few seconds before seeing the change applied to the profile.

> The addition of additional modules to Centreon sometimes makes it possible to
> add additional filters to the access groups. E.g.: Centreon modules BI, BAM and
> MAP can be subjected to filters.

## Access groups

To add an access group:

1. Go into the menu: `Administration > ACL`
2. Click on **Add**

### General information

- The **Group Name** and **Alias** fields define the name and the alias of the
group
- The **Linked Contacts** list can be used to link contacts to the access
group
- The **Linked Contact Groups** list can be used to link groups of contacts to
the access group
- The **Status** field can be used to enable or disable the access group

> The contact group can be groups coming from the LDAP directory connected to the
> Centreon interface.
>
> Groups created in Centreon interface should not have the same name as LDAP
> groups to avoid problems.

### Authorizations information

The lists presented in this tab can be used to link the various types of access
already created to the access group.

## Resources Access

The access filters for the resources serve to limit the viewing of objects
(hosts, host groups, services and service groups) to a user profile.

To add resources access filter:

1. Go into the menu: `Administration > ACL`
2. In the left menu, click on **Resources Access**
3. Click on **Add**

> Once the filters on the resources are set, you can to view the result via the
> menu: **Check User View**, next to the add option.

### General information

- The **Access list name** and **Description** fields define the name and the
description of the filter
- The **Linked groups** list can be used to link access groups to this
resource filter
- The **Status** and **Comments** fields serve to enable / disable the filter
and to comment on it

### Hosts Resources

The **Hosts Resources** tab enables us to add:

- Hosts
- Host groups

If the **Include all hosts** or **Include all hostgroups** box is checked, all
newly created objects will be added to the filter automatically.

> It is possible to explicitly exclude hosts from the filter (useful in cases
> where only 1 or 2 hosts must not be part of the filter) if *Include all hosts*\*
> or **Include all hostgroups** options are checked.

### Services Resources

The **Services Resources** tab can be used to add service groups to the filter.

### Meta Services

The Meta-Services tab can be used to add meta-services to the filter.

### Filters

- The **Poller Filter** list can be used to select the hosts according to
monitoring poller (if none is selected all the pollers are taken into
account)
- The **Host Category Filter** list can be used to filter the hosts by
category
- The **Service Category Filter** list can be used to filter the services by
category

> The filters by poller or by category of object are inclusion filters (UNION).
> Only the objects belonging to these filters in addition to groups of objects
> (hosts and services) will be visible.

## Menus Access

The access filters to the menu serve to limiter the access to various menus of
the Centreon interface. The menus are ranked as follows:

- Level 1 menus (Home, Monitoring, Views, etc.)
- Level 2 menus (Monitoring > Hosts, Monitoring > Services, etc.)
- Level 3 context menus (Monitoring > Services > By Hosts / Details)
- Level 4 context menus (Monitoring > Services > By Hosts / Details >
Problems)

> By default, access is **Read Only**. If you want to allow your users to modify
> the configuration, you will need to select the **Read / Write** option for each
> submenu.

> To access an ‘n-1’ menu level, the user must have access to the ‘n’ menu level,
> otherwise he will not be able to view the menu via the interface. If this is not
> the case, the user will have to directly access the page via a direct link
> (autologin, etc.).

> Accessing the command editing menu, as well as accessing the SNMP trap editing
> menu can be very dangerous. Indeed, the privileged user can create commands,
> which may lead to the creation of security breaches (RCE). Only give this access
> to people you can trust.

To add an access filter to the menus:

1. Go into the menu: `Administration > ACL`
2. In the left menu, click on **Menus Access**
3. Click on **Add**

- The **ACL Definition** and **Alias** fields define the name and the alias of
the access filter
- The **Status** field is used to enable or disable the filter
- The **Linked Groups** list can be used to associate an access group to the
filter
- The **Accessible Pages** can be used to associate menus to the filter (The
parent menu should be checked to be able to access the child menu)
- The **Comments** field gives indications on the filter

> On the access definition to the **Configuration > Hosts** and **Configuration > Service** menus, 
> it is possible to give read only or read / write access to
> various objects.

> At each addition of a new Centreon module possessing a web interface accessible
> via a new menu, it should be added in the access groups so that the users can
> access.

## Actions Access

Filters on actions enable us to limit access to actions that can be effective on
resources (hosts and services) and on monitoring engines (stopping
notifications, restarting the scheduler, etc.).

To add an access filter to the actions:

1. Go into the menu: `Administration > ACL`
2. In the left menu, click on **Actions Access**
3. Click on **Add**

- The **Action Name** and **Description** fields contain the name of the
filter and its description
- The **Linked Groups** list serves to associate an access group to the filter

The table below describes the general access functionalities:

| Field                                  | Associated actions                                                               |
| -------------------------------------- | -------------------------------------------------------------------------------- |
| Display Top Counter                    | The monitoring overview will be displayed at the top of all pages                |
| Display Top Counter pollers statistics | The monitoring poller status overview will be displayed at the top of all pages. |
| Display Poller Listing                 | The poller filter will be available to users in the monitoring consoles          |

The table below describes the access to the configuration generation:

| Field                            | Associated actions                                                                                                                   |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Generate Configuration Files     | Allows users to generate, test and export configuration to pollers and to restart the monitoring scheduler                           |
| Generate SNMP Trap configuration | Allows users to generate and export configuration of the SNMP traps for the Centreontrapd process on pollers and to restart this one |

The table below describes all the actions that can be authorized on the
scheduler:

| Field                                   | Associated actions                                            |
| --------------------------------------- | ------------------------------------------------------------- |
| Shutdown Monitoring Engine              | Allows users to stop the monitoring systems                   |
| Restart Monitoring Engine               | Allows users to restart the monitoring systems                |
| Enable/Disable notifications            | Allows users to enable or disable notifications               |
| Enable/Disable service checks           | Allows users to enable or disable service checks              |
| Enable/Disable passive service checks   | Allows users to enable or disable passive service checks      |
| Enable/Disable passive host checks      | Allows users to enable or disable passive host checks         |
| Enable/Disable Event Handlers           | Allows users to enable or disable event handlers              |
| Enable/Disable Flap Detection           | Allows users to enable or disable flap detection              |
| Enable/Disable Obsessive service checks | Allows users to enable or disable obsessive service checks    |
| Enable/Disable Obsessive host checks    | Allows users to enable or disable obsessive host checks       |
| Enable/Disable Performance Data         | Allows users to enable or disable performance data processing |

The table below describes all the actions that can be authorized on services:

| Field                                                         | Associated actions                                                                     |
| ------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Enable/Disable Checks for a service                           | Allows users to enable or disable checks of a service                                  |
| Enable/Disable Notifications for a service                    | Allows users to enable or disable notifications of a service                           |
| Acknowledge a service                                         | Allows users to acknowledge a service                                                  |
| Re-schedule the next check for a service                      | Allows users to re-schedule next check of a service                                    |
| Re-schedule the next check for a service (Forced)             | Allows users to re-schedule next check of a service by placing its priority to the top |
| Schedule downtime for a service                               | Allows users to schedule downtime on a service                                         |
| Add/Delete a comment for a service                            | Allows users to add or delete a comment of a service                                   |
| Enable/Disable Event Handler for a service                    | Allows users to enable or disable the event handler processing of a service            |
| Allows users to enable or disable flap detection of a service | Allows users to enable or disable flap detection of a service                          |
| Enable/Disable passive checks of a service                    | Allows users to enable or disable passive checks of a service                          |
| Submit result for a service                                   | Allows users to submit result to a service                                             |
| Display executed command by monitoring engine                 | Allow the display of the executed command for a service                                |

The table below describes the all the actions that can be authorized on hosts:

| Field                                           | Associated actions                                                                  |
| ----------------------------------------------- | ----------------------------------------------------------------------------------- |
| Enable/Disable Checks for a host                | Allows users to enable or disable checks of a host                                  |
| Enable/Disable Notifications for a host         | Allows users to enable or disable notifications of a host                           |
| Acknowledge a host                              | Allows users to acknowledge a host                                                  |
| Disaknowledge a host                            | Allows users to disacknowledge a host                                               |
| Schedule the check for a host                   | Allows users to re-schedule next check of a host                                    |
| Schedule the check for a host (Forced)          | Allows users to re-schedule next check of a host by placing its priority to the top |
| Schedule downtime for a host                    | Allows users to schedule downtime on a host                                         |
| Add/Delete a comment for a host                 | Allows users to add or delete a comment of a host                                   |
| Enable/Disable Event Handler for a host         | Allows users to enable or disable the event handler processing of a host            |
| Enable/Disable Flap Detection for a host        | Allows users to enable or disable flap detection of a host                          |
| Enable/Disable Checks services of a host        | Allows users to enable or disable all service checks of a host                      |
| Enable/Disable Notifications services of a host | Allows users to enable or disable service notifications of a host                   |
| Submit result for a host                        | Allows users to submit result to a host                                             |

- The **Status** field is used to enable or disable the filter

## Reload ACL

It is possible of reload the ACLs manually:

1. Go into the menu: `Administration > ACL`
2. In the left menu, click on **Reload ACL**
3. Select the user(s) you want to reload the ACL
4. In the **More actions** menu, click on **Reload ACL**
