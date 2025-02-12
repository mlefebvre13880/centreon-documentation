---
id: centreon-core
title: Centreon Core
---

## Introduction

Vous trouverez dans ce chapitre tout ce qui concerne **Centreon Core**.

> Il est important de mettre à jour en utilisant la documentation
> adéquate de mise à jour et de lire attentivement les notes de mise à
> jour afin d'être au courant des changements qui pourraient impacter
> votre usage ou votre plateforme ou des développements spécifiques que
> vous auriez fait.

Pour faire des demandes d'évolutions ou reporter des bugs sur les extensions
commerciales, vous pouvez vous rendre sur notre
[Github](https://github.com/centreon/centreon/issues/new/choose).

## Centreon Web

### 20.10.17

Release date: `April 15, 2022`

#### Bug fixes

- [Core] Proxy settings were saved with empty parameters
- [MBI] MBI graphs reports were not using graph templates
- [Resources Status] Fixed monitoring command not displayed in Resources Status Details panel

### 20.10.16

Release date: `April 1, 2022`

#### Enhancements

- [Authentication] Autologin Validation reinforcement
- [UX] Add TheWatch URL to Centreon footer

#### Bug fixes

- [Authentication] Improve LDAP authentication and authorization
- [Core] Fixed SQL request syntax error for cron with MySQL 8
- [Install] Fixed SQL errors in upgrade process from Centreon version < 2.8.5
- [Resources Status] Fixed the display of old downtimes in the Details tab

#### Security Fixes

- [Administration] SQL injection on Knowledge Base configuration form
- [Administration] SQL injections on ACL group listing
- [Administration] SQL injections on LDAP listing
- [Configuration] Command path traversal resulting in RCE on command edition form
- [Configuration] SQL injection on export configuration
- [Configuration] SQL injections on SNMP traps edition form
- [Configuration] SQL injection in Resources form
- [Core] Disabling allow_url_fopen in PHP
- [Core] RCE in legacy PHP's class autoload
- [Dashboard] XSS in reporting dashboard
- [Monitoring] SQL injection on performance curve edition form
- [Resources Status] XSS reflected from plugin's metric output

### 20.10.15

Release date: `December 23, 2021`

#### Bug fixes

- [API] Fixed the value of acknowledgement's stickiness set by the API. A value of 1 was set instead of 2. Based on PR [#10028](https://github.com/centreon/centreon/pull/10028).
- [Authentication] Fixed LDAP OU quote connection breaking
- [CLAPI] Fixed an issue preventing ACLs from applying on services created with CLAPI
- [Configuration] Fixed an issue that caused the Anomaly Detection services to lose their graphs when they were renamed
- [Configuration] Fixed an issue that prevented users from removing the SNMP community (and other fields) from the host form
- [Configuration] Fixed unwanted writes into unexisting file when exporting Traps config at the same time as a trap arrives. Based on PR [#9973](https://github.com/centreon/centreon/pull/9973). Fixes issue [#4236](https://github.com/centreon/centreon/issues/4236)
- [Install] Fixed installation with MySQL 5.7 on step 7 of installation wizard

### 20.10.14

Release date: `November 29, 2021`

#### Bug fixes

- [Authentication] Fixed PHP error when debug is enabled with OIDC authentication
- [CLAPI] Fixed LDAP configuration ID for export and import
- [Configuration] Fixed Centreon Broker configuration that could be empty or deleted
- [Core] Remove PHP warning in logs
- [Resources Status] Fixed access to action URLs
- [Resources Status] Fixed access to actions buttons
- [UX] Non admin user do not have the same submenu subsections

### 20.10.13

Release date: `November 15, 2021`

#### Enhancements

- [CEIP] Product Adoption component integration
- [Core] Add Feature Flipping for Resources Status vs Legacy Pages
- [Core] Compatibility PHP 7.4

#### Bug fixes

- [Authentication] Fixed user information retrieval method for OpenId
- [CLAPI] Fixed recurrent downtimes exported with CLAPI that could not be imported with CLAPI
- [Configuration] Avoid blocking configuration generation when users don't have notifications enabled
- [Configuration] Fixed reset untouched values using massive changes on hosts
- [Configuration] Fixed empty string parameter for LUA output in Broker configuration
- [Custom Views] Fixed sharing of views with LDAP groups
- [Discovery] Fixed an issue causing error messages when filling credentials in a Host Discovery job
- [Downtime] Fixed display of planned downtimes when one downtime is started
- [Downtime] Fixed the adding of a downtime on a resource from the French GUI
- [Knowledge Base] Get correct link from template. Based on [PR #10066](https://github.com/centreon/centreon/pull/10066)
- [UX] Fixed menus by no longer displaying orphaned items

#### Security fixes

- CSRF - delete any command
- CSRF - delete any poller
- CSRF - delete any host
- CSRF - delete any SNMP trap
- CSRF - delete any service
- CSRF - delete any contactGroup
- CSRF vulnerability allowing to delete any user	
- CSRF vulnerability allowing to delete many kinds of objects

### 20.10.12

`October 5, 2021`

#### Security fixes

- Fixed session on account deletion

### 20.10.11

`14 septembre 2021`

#### Correctifs

- [ACL] Fixed missing ACL actions on CLAPI import
- [Configuration] Fixed ineffective massive change on 'Reach API configuration' option on remote server
- [Downtimes] Prevent the user from creating downtimes with start date, end date and duration after 2037
- [Platform Topology] Fixed an error that occurred when an FQDN was used as parent address

#### Correctifs de sécurité

- [Install] Rights applied to "centreon.conf.php" and "conf.pm"
- [OpenId] Secret tokens obfuscation
- [Resource status] Fixed error based SQLi on resources GET's endpoint

### 20.10.10

`30 juillet 2021`

#### Améliorations

- [Authentication] Improve centreonAuth.SSO.class for OpenId connection

#### Correctifs

- [Administration] LDAP search fails
- [Configuration] Changing a Remote Server's IP address converts it into a simple Poller
- [Configuration] Editing service template removes relations with servicegroups
- [Configuration] Only first servicegroup linked to a service template is exported
- [Core] Unserialize in CentreonUtils is blocked by QualityGate
- [Core] Update copyright date
- [Graph] Can't get a graph with autologin key
- [LDAP] Fixed LDAP auto-sync is always skipped
- [LDAP] LDAP's My account issue
- [Platform Topology] CLAPI's add Instance doesn't add a poller into the platform_topology table
- [Platform Topology] JSON Schema isn't validated in the POST endpoint
- [Platform Topology] Removed unused variable in registerServerTopology.sh
- [Resources Status] No route found for "GET /centreon/api/beta/monitoring/resources/undefineds/133"
- [i18n] Fix typo in error message

### 20.10.9

`30 juin 2021`

#### Correctifs

- [APIv2] Use poller's page ACL rights on Topology API endpoints
- [Configuration] InfluxDB configuration columns are deleted in Broker form
- [Downtime] Can not remove/delete periods when configuring recurrent downtime
- [Platform Topology] Update Exception handling

#### Correctifs de sécurité

- [Configuration] Input sent to unserialize() are not sanitized
- [Configuration] SQL Injection on commands
- [Configuration] SQL Injection on host dependency
- [Configuration] SQL Injection on hostgroup dependency
- [Configuration] SQL Injection on metaservice
- [Configuration] SQL Injection on metaservice dependency
- [Configuration] SQL Injection on service categories
- [Configuration] SQL Injection on service dependency
- [Configuration] SQL Injection on servicegroup
- [Configuration] SQL Injection on servicegroup dependency
- [Configuration] SQL Injection on timeperiod
- [Configuration] XSS Stored on checks command
- [Core] Manage security acknowledgement

### 20.10.8

`7 Juin 2021`

#### Correctifs

- [APIv1] Cannot send external commands anymore
- [APIv2] Can not authenticate using API when database name and database username are different from default
- [APIv2] DELETE downtime on host not functionnal
- [APIv2] Unable to use v2 api (internal server error)
- [Administration] Broker statistics for pollers are not shown
- [Anomaly] host_id is null is stream connector flow
- [Configuration] Change default values for Centreon Engine
- [Configuration] Unable to add a Poller with the Wizard
- [Core] Avoid 404 redirection
- [Install] Cannot update when you have no metaservices
- [LDAP] Adding new user from LDAP results in Request Entity Too Large error
- [Reporting] Dashboard can't display reporting for service (query too long)
- [Resources Status] "Filter by Host" filter is not emptied between searches
- [Resources Status] Action ACL not working
- [Resources Status] Apply ACL in command line block
- [Resources Status] Manage not filled curves

#### Correctifs de sécurité

- [Administration] Import of JS in image files
- [Administration] Insecure media file upload
- [Administration] SQL Injection on ACL actions
- [Administration] SQL Injection on ACL resources
- [Administration] SQL Injection on reload ACL
- [Configuration] SQL Injection on MediaWiki
- [Configuration] SQL Injection on SNMP trap manufacturer
- [Configuration] SQL Injection on poller form
- [Configuration] Unserialize() are not sanitized in Centreon Broker wizard
- [Configuration] Unserialize() are not sanitized in poller wizard
- [Configuration] XSS reflected on Graph performance curves
- [Configuration] XSS reflected on SNMP trap
- [Configuration] XSS reflected on internal API broker configuration
- [Graph] SQL Injection on Graph component templates
- [Graph] SQL Injection on Graph generate image
- [Install] Packaging, remove . gitignore files
- [Reporting] SQL Injection on reporting export

#### Performance

- [ACL] ACL are computed every time for BV
- [Generation] Bulk insert in index_data during config generation
- [Purge] Purge of index_data is taking too long because of suboptimal SQL query

### 20.10.7

`7 mai 2021`

#### Améliorations

- [Custom Views] Add regex filtering to widget compare field

#### Correctifs

- [Configuration] Can not delete Remote Server from UI
- [Configuration] Central's Engine configuration is set to use aggressive host checking
- [Configuration] Hosts/services templates become simple hosts/services
- [Configuration] Unable to create Meta service with high amount of metrics
- [Configuration] Wrong number of services/pages to display
- [Graph] Graphics are not displayable in the interface
- [Monitoring] Cancelled BA downtime from Downtime menu
- [Monitoring] Export event logs with filter on output is broken
- [Platform Topology] API: remote / poller to central with proxy
- [Platform Topology] Remove all topology when Remote => Central Conversion
- [Platform Topology] Script: Unable to register a remote on a Central
- [Platform Topology] Unable to replace 127.0.0.1 by real IP in poller form when already saved in platform_topology
- [Purge] Script can't drop several partitions
- [Resources Status] Be able to sort by Parent name in listing
- [Resources Status] Manage notes on resources for Notes URL
- [Resources Status] Missing french translations
- [Resources Status] Service link to multiple hosts or service by hostgroup won't be listed
- [UI] Centreon blank page on all menu with firefox < 78

#### Correctifs de sécurité

- [Administration] User can install or delete modules with no ACL rights
- [Configuration] Cross-site Scripting (XSS) Stored/Persistent in Dependency/Notification form
- [Configuration] SQL injection in user additional information
- [Configuration] Stored XSS in host Alias for host form
- [Core] Predictable anti-CSRF token
- [Graph] SQL Injection on graph periods
- [Graph] SQL Injection on graph split
- [Lib] Update centreon vulnerable packages
- [Resources Status / Service Details] Passwords are displayed in command line
- [Resources Status / Service Details] Passwords field for EXTRAOPTIONS is not hidden in command line

#### Performance 

- [Core] Replace "WITH RECURSIVE" MySQL calls with PHP-based recursion loops

### 20.10.6

`20 avril 2021`

#### Correctifs

- [ACL] Use ACL Action to generate traps
- [About] Update about page with current team
- [Administration] Cannot list Pollers in Platform Status pages
- [Configuration] Error while adding a Remote Server and attaching a poller to it via wizard
- [Configuration] Poller attached to remote is not fully removed from database when deleted using the from
- [Core/API/v1] Can't filter on criticality
- [Core] Configuration output can lead to an empty broker configuration
- [Core] Update centreon copyright dates
- [Extensions Manager] No popup when removing extension
- [Graph] Adapt graph scale for b/s unit
- [Graphs] Colors of labels don't match colors of curves (old library)
- [Install] During installation, web installer can not be executed fully
- [Platform Topology] Distant Poller attached behind a Remote Server does not receive conf
- [Platform Topology] Missing current node IP address in register script
- [Platform Topology] Register script concatenates default values to values from the template
- [Platform Topology] Script target address not parsed correctly.
- [Platform Topology] Enhance register script displaying
- [Reporting] Dashboard is slow to display with large service groups
- [Resources Status] Bad urls for mediawiki
- [Resources Status] Macros in "URL" and "Action URL"
- [Resources Status] Missing french translations
- [UX] Remove "deprecated" from menu for deprecated monitoring pages

#### Correctifs de sécurité

- [Core] XSS in index.php and index
- [Library] Update jQuery to version sup or equal 3.5.1

#### Performance

- [API/Topology] Refacto PlatformTopology 20.10

### 20.10.5

`1 avril 2021`

#### Correctifs

- [Lib] Update moment-timezone to manage new timezones
- [Resources Status] Error when getting the command line for Meta Service detail

#### Correctifs de sécurité

- [APIv2] API realtime rights give API configuration rights

### 20.10.4

`25 février 2021`

#### Améliorations

- [Configuration] Add the 'instance_heartbeat_interval' parameter in Engine configuration
- [Configuration] Improve access to the list of pollers
- [Core] Performance improvements for partitioning
- [Core] Update PHP 7.3 compatibility
- [Core] Use Gorgone to dispatch downtimes locally
- [Status Details] Display of comments in the host details page
- [Top counters] Displayed values for services don't consider host acknowledgements

#### Correctifs

- [CLAPI] No control on dependencies relations
- [Configuration/] "Conf Changed" yes is green instead of red in pollers listing
- [Configuration] Creation forms generate status code 400 errors
- [Configuration] Non-admin users can't create host/service
- [Resources Status] Display order of events in timeline
- [Resources Status] Panel does not display radius
- [Resources Status] Unexpected behavior when setting a DT with an empty comment field

#### Correctifs de sécurité

- [Administration] Cross-site Scripting (XSS) Stored/Persistent in "ACL > Resources Access" - CVE-2020-22425
- [Administration] XSS stored in the LDAP form
- [Apache] Remove deprecated TLS ciphers
- [Authentication] Session is active longer than expected
- [Authentication] User enumeration in login page
- [Configuration] Cross-site Scripting (XSS) Reflected in "Configuration > Hosts"
- [Core] Vulnerable handlebars.js library
- [Reporting] Cross-site Scripting (XSS) Reflected in "Dashboard > Hosts"

### 20.10.3

`8 février 2021`

#### Améliorations

- [API] Add endpoint for Topology/enableRemote
- [API] Add Delete method for Topology/enableRemote
- [Core] [Refactor the script to register new server in bash instead of PHP

#### Correctifs

- [Administration] ACL Menus Access - Lines alignment
- [Administration] ACL Menus Access - Unable to select subgroup access options
- [CLAPI] APPLYCFG on a Poller behind a Remote Server doesn't trigger sync task for the RS itself
- [CLAPI] Cancel RTACKNOWLEDGEMENT doesn't work for services
- [CLAPI] Create user with language
- [CLAPI] Import fails on password type macros
- [CLAPI] Show RTACKNOWLEDGEMENT for a service only shows first one to have been defined
- [Update] Central IP is override by 127.0.0.1 in platform_topology table

#### Correctifs de sécurité

- [ACL/Access Groups] Cross-site Scripting (XSS) Stored/Persistent for search
- [ACL/Actions Access] Cross-site Scripting (XSS) Stored/Persistent for search
- [ACL/Resources Access] Cross-site Scripting (XSS) Stored/Persistent for search
- [API] Missing access control mechanism in rest API v1
- [Configuration > Servicegroups] Leak of technical information
- [Configuration/H/HTPL/S/STPL] Password in plain text
- [Core] Centreon token is vulnerable against replay attack
- [Core] Token usage is not mandatory
- [Media] PHP warning about missing tmp dir used during media upload

### 20.10.2

`12 janvier 2021`

> Comportements connus :
>
> -   Les liens "url notes" et "url actions" maintenant visibles dans la page "Resources Status"
>     ne traduisent pas les macros, par exemple $HOSTNAME$.

#### Améliorations

- [API] Add normalizers for data found in concordanceArray
- [API] Get topology of servers of a Centreon Platform
- [Configuration] Add a special variable for trap OID
- [Configuration] Add pool size parameter in configuration for Centreon Broker
- [Resources Status] Add alias & fqdn in host detail panels
- [Resources Status] Add URL link button from host and service extended information configuration

#### Correctifs

- [Authentication] New LDAP configurations are broken
- [CLAPI] Export does not export default contactgroup linked to a LDAP configuration
- [Configuration] PHP Warning while creating a Centreon Engine configuration
- [Configuration] Unable to save log level in Centreon Engine form
- [Knowledge Base] Access to mediawiki is very slow
- [Resources Status] Display issue when resource has a configured icon
- [Resources Status] Incorrect default downtime duration
- [Resources Status] Useless impacted_resources_count property

#### Correctifs de sécurité

- [Apache] Support for the HTTP TRACE
- [Apache] Uncorrect HTTPS declaration of SSLCipherSuite in Centreon example file
- [Authentication] Reach Centreon Front-end parameter ineffective
- [Configuration] Cross-site Scripting (XSS) Stored/Persistent in Connectors & commands form
- [Configuration] Cross-site Scripting (XSS) Stored/Persistent in Contact Groups form
- [Configuration] XSS in updateContactParam.php & commonJS.php
- [Media] Unrestricted file upload

### 20.10.1

`25 novembre 2020`

#### Améliorations

- [API] Improve registration script
- [Performance] Disable UI notification mechanism if not needed by user

#### Correctifs

- [API] Rework POST generated API request for PlatformTopology
- [API] Service groups search not working
- [Administration] "show deprecated pages" option does not work anymore
- [Administration] 'options' table for centreon database is sometimes empty
- [Configuration] Radio buttons for "InfluxDB - Storage - InfluxDB" output
  not working properly for Centreon Broker form
- [Core] Perl lib db query bad looping parameters
- [Core] Too much rows in extended_service_informations tables
- [Event View] Cannot search with regex using "+" character
- [Event logs] Inoperative filters when exporting
- [Graphs] Performance graph legend does not update dynamically
- [Reporting] Dashboard won't build when having service by hostgroup
- [Resources Status] Cannot search multiple times in hostgroup filter
- [Resources Status] Infinite scroll + refresh button duplicates events in
  timeline
- [Resources Status] Services listing blinking in details panel
- [Resources Status] Timeline tab content blinks while browsing resources

#### Correctifs de sécurité

- [Apache] Lack of click diversion protection (Clickjacking)
- [Core] Update moment.js library

### 20.10.0

`21 octobre 2020`

> Comportements connus:
>
> -   Si un Central est configuré pour communiquer avec un Remote Server
>     à l'aide de SSH , le rechargement de la configuration déclenchera
>     l'erreur suivante dans le log de Gorgone:
>
>     ```text
>     ERROR - [sshclient] Unsupported action 'ADDIMPORTTASKWITHPARENT'
>     ```
>
>     Cela est dû au fait que le processus d'exportation/importation
>     de données entre ces deux serveurs n'appelle pas l'API du Remote
>     Server (le flux HTTP n'est alors plus nécessaire).
>
>     L'appel se fait maintenant via Gorgone, comme pour la copie des
>     fichiers, et nécessite que la communication utilise ZMQ.

#### Améliorations

- [API] Possibility to Register servers (Remote Server, Poller, Centreon Map)
- [Configuration/Wizard] Add possibility to select registered poller
- [Authentication] Replace Keycloak to generic OAuth2 / OpenId Connect
- [Event Logs] Display anomaly detection as regular service
- [Monitoring/Resources Status] Add shortcuts for hosts and services details
- [Monitoring/Resources Status] Add timeline for hosts and services details
- [Monitoring/Resources Status] Be able to filter on status output
- [Monitoring/Resources Status] Add possibility to save/manage filters
- [Monitoring/Resources Status] Add possibility to submit result for resources
- [Monitoring/Resources Status] Redirect all realtime links to Resources
  Status page
- [Remote Server] Replace HTTP flow by gorgone between Central and Remote
  Servers

## Centreon Engine

### 20.10.7

`20 octobre 2021`

#### Bug fixes

- Badly designed mutex could cause deadlocks in centreon-clib
- [Anomaly_Detection] Units were not provided in the perfdata for lower_thresholds and upper_thresholds of Anomaly Detection services
- Fixed an issue that could cause deadlocks in the logs production
- Sending values of date_start, date_end and duration of downtimes higher than 2^31 (`Tue Jan 19 04:14:08 CET 2038`) could block broker's inserts into the database. They are now limited to `2037-12-31 23:59:59`.
- No recovery notification was sent if service went from CRITICAL to WARNING to OK state and user deactivated WARNING notification

#### From Community

- Notifications were sent for services of a soft down host despite "Soft Service Dependencies" option being set to "yes" (fixes issue [#286](https://github.com/centreon/centreon-engine/issues/286))


### 20.10.6

`15 juillet 2021`

#### Correctifs

- Les notifications de récupération ne sont pas envoyées si centengine a été interrompu durant l'incident
- Centengine envoie les statuts de services en double lorsqu'un contrôle immédiat est planifié
- Problèmes de compilation sur Raspberry Pi

### 20.10.5

`4 juin 2021`

> Cette version nécessite Centreon Clib 20.10.2 ou supérieur.
> Cette version nécessite Centreon-Connector 20.10.1 ou supérieur.

#### Correctifs

- Engine consomme 100% de CPU quand `check_period` est `none`
- Le build d'engine/broker a été migré de Bintray vers ConanCenter

### 20.10.4

`29 avril 2021`

#### Correctifs

- Évitez d'envoyer des horodatages erratiques
- La macro SERVICEGROUPNAME n'apparaît pas dans les notifications
- Le champ "Hard State Duration" de l'hôte affiche "N/A" lorsqu'il n'est pas associé à des services
- Limiter la date de début, la date de fin et la durée des temps d'arrêt
- Mauvais accès à la mémoire sur les macros hostgroupname / servicegroupname

### 20.10.3

`28 avril 2021`

> Cette version nécessite Centreon Broker 20.10.4 ou supérieur.

#### Correctifs

- Les notifications de type recovery n'étaient pas envoyées à la sortie d'un arrêt prévu
- Les notifications de type recovery n'étaient pas envoyées à l'entrée en période de notification
- Les statuts d'hôtes et de services étaient transmis en double à Broker
- La macro $TIMET$ contenait l'heure formatée au lieu d'un timestamp
- Le flapping n'était pas détecté correctement
- La macro $SERVICENOTESURL$ était encodée par Engine dans les notifications
- La période de notification de l'utilisateur n'était pas correctement appliquée
- Engine pouvait s'arrêter sans logger aucune erreur

### 20.10.2

`20 janvier 2021`

> Cette version nécessite Centreon Broker 20.10.3 ou supérieur.

#### Correctifs

*Notification macros*

The macros in which notification information can be found have been fixed
(ie $NOTIFICATION*$, $HOSTNOTIFICATION*$, $SERVICENOTIFICATION*$)

#### Améliorations

*Instance updates*

There is a minimal delay specified in seconds between two instance updates.
By default, its value is 30s. It can be set with the variable
instance_heartbeat_interval in the centengine.cfg file.

### 20.10.1

`16 décembre 2020`

#### Correctifs

*Stalking option*

The stalking option works again, it has been fixed. Make sure you are not
enabling volatile option at the same time to really get an output
stalking.

*Macros filters*

Macros can be filtered. This was possible before and there was a
regression breaking this functionality. So now, we can activate the
macros filtering and then we can specify which macros to send to broker.

*Notifications*

Host/service status field 'Last Notification' was filled when
state was HARD even if no notification is configured nor sent.

### 20.10.0

`21 octobre 2020`

> Comportements connus:
>
>   - Si Engine sur un Poller ou un Remote Server n'est pas mis à jour en
>     20.10, les fichiers de configuration copiés depuis un Central à jour
>     par Gorgone utilisant une communication ZMQ ne pourront pas être
>     lus par le processus Engine, avec l'erreur suivante dans les logs:
>
>     ```text
>     Error: Parsing of global configuration failed: Can't open file '/etc/centreon-engine/centengine.cfg'
>     ```
>
>     Cela est dû à des droits plus stricts sur ces fichiers.
>
>     Comme toujours, nous **recommandons fortement** de mettre à jour
>     tous les composants en adéquation avec la version du Central.
>
>     Cependant, le temps de la mise à jour, il est possible d'ajouter
>     manuellement l'utilisateur *centreon-engine* au groupe
>     *centreon-gorgone* avec la commande suivante :
>
>     ```shell
>     usermod -a -G centreon-gorgone centreon-engine
>     ```

#### Correctifs

- Contient tous les correctifs jusqu'à la version 20.04.7

## Centreon Broker

### 20.10.12

Release date: `March 10, 2022`

#### Bug fixes

- Refactored the BAM Business activities downtimes inheritance mechanism so that they are properly inherited and not duplicated anymore.

> After having updated centreon-broker to this version, you may still have unwanted remaining downtimes on your Business Activities. It can happen if a downtime that was inherited from a KPI has been duplicated and if the original downtime ended before the bugfix was installed. In that case, you will have to apply the following procedure.

```bash
systemctl stop centengine
sed -i -zE 's/(servicecomment|servicedowntime) \{\nhost_name=_Module_BAM_1\n[^}]*\}\n//g' /var/log/centreon-engine/retention.dat
systemctl start centengine
```

All the downtimes applied on Business Activities have now been removed.

You must then restart the `centengine` service on all the other pollers to restore the legitimate inherited downtimes.

### 20.10.11

Release date: `January 20, 2022`

#### Bug fixes

- Fixed a regression due to the central broker's cache generation optimization, which was too thorough and prevented BAM from computing KPIs based on boolean rules

### 20.10.10

Release date: `January 13, 2022`

#### Bug fixes

- The central broker's cache generation loaded too much data and took too much time when BAM was activated
- When a single metric is deleted, the corresponding RRD file is now removed
- Fixed an issue causing BAM Business Activities (best status) to remain in an OK state when the OK KPIs were removed

### 20.10.9

`27 octobre 2021`

#### Bug fixes

- Fixed a deadlock issue that blocked engine when all debug options were enabled


### 20.10.8

`20 octobre 2021`

#### Improvements

- A TCP keepalive check has been added to the acceptor side of broker connections to avoid keeping dead connections

#### Bug fixes

- Fixed an issue that occasionally caused the LUA cache to disappear when reloading cbd
- In case of retention on one side of a tcp connection, the connection could get interrupted because of an issue in the flush() function
- Database connection error flag was not reset in conflict manager once an error occurred (even after successful connection) and could block the insertion into the database
- The index_id column of table metrics was cast in int32 instead of int64
- Resolved conflicts that could appear between hostgroups when connections_count > 1
- Deleting graph from the WUI did not actually delete RRD files


### 20.10.7

`30 Août 2021`

#### Correctifs

- Fixed a deadlock in broker with a reversed TCP output when cbd receives SIGTERM
- Fixed "MySQL server has gone away" error causing failure in BAM events computation, and data loss in BAM availability statistics

### 20.10.6

`15 juillet 2021`

#### Correctifs

- Un *deadlock* pouvait se produire lorsque broker était arrêté immédiatement après son démarrage
- Un *core dump* pouvait apparaître lorsque centengine était stoppé
- Parfois centengine ne parvenait pas à se reconnecter au broker central
- Quand beaucoup de collecteurs essayent de se connecter au même moment au broker central, il arrive que les derniers ne puissent pas se connecter
- Les plages de temps n'étaient pas parsées correctement lorsqu'elles se terminaient par `\r` ou `\n`
- Problèmes de compilation sur Raspberry Pi
- Les requêtes TLS n'étaient pas correctement traitées par GNUTLS sur RedHat 8

#### Améliorations

- Les logs de *debug* `BBDO serialized events` sont désormais des logs de niveau *trace*

### 20.10.5

`4 juin 2021`

#### Sécurité

- Blocage des injections SQL depuis des *custom variables*
- Suppression de SSL et de suites de chiffrement dépréciées

#### Correctifs

- Le build d'engine/broker a été migré de Bintray vers ConanCenter
- La compatibilité BBDO était cassée suite à la mise à jour mineure 20.10.4, ce qui bloquait le rafraichissement des données de la supervision
- Les metaservices utilisés comme KPI n'impactaient pas les activités métier (Centreon BAM)
- L'impact *CRITICAL* était appliqué plutôt que l'impact *UNKNOWN* lorsqu'une BA était utilisée comme KPI d'une autre BA (Centreon BAM)
- Le redémarrage de Broker était ralenti par des requêtes sous-optimales relatives aux arrêts prévus et aux commentaires
- Limiter les valeurs des dates de début, de fin et de durée des arrêts prévus pour qu'elles ne dépassent pas la valeu
r maximale permise en base de données

### 20.10.4

`28 avril 2021`

*Broker*

- Add TLS handshake in broker debug logs
- Allow point as a valid character for ouput's name
- Broker hangs when stopped alone (without watchdog)
- Cast index_data.id to unsigned int 64
- Connection interruption not detected by Central (one peer retention mode)
- Harden SIGTERM handling when shutting down
- Insert NULL instead of Nan or Inf for metrics data
- Provide host_id and service_id in logs when metrics fail to be inserted in database
- Rebuild of RRD not working
- Study ARM compilation
- TLS common name check impossible if it is too long

*Engine*

- Engine stops working without error

*Security*

- Strengthen TLS / SSL exchanges

### 20.10.3

`20 janvier 2020`

#### Correctifs

*Conflict manager and comments*

It is possible to lock the database during comments insertion. This new
version fixes that.

*BAM reporting dimensions computation*

If there are retention files, dimensions computation could fail because of
conflicts between new block computation and old ones (the ones in the
retention). There was also an issue of concurrent access to tables during
dimensions computation.

*BAM availabilities rebuild*

When availabilities are rebuilt, durations can be doubled. This new version
fixes this issue.

#### Améliorations

*Logs*

Logs are sent to the database in bulk as we already do for customvariables.

*Lua*

There is a new API available for the Lua connector. To use it, scripts
must declare a global variable `broker_api_version=2`. From the user's
point of view, Stream Connectors should work almost the same. In isolate
cases, we could see scripts that do not work with this new API, then you
can always work with Broker API version 1, by setting the variable to 1
or by removing this variable declaration in the script. Why should we
use the v2 version? Because it is faster, really faster.

*TCP connections*

If the connection between two peers is flapping, it may be difficult for one
to reconnect to the other and this could lead to many CLOSE_WAIT on the
acceptor side. This new version fixes this issue.

### 20.10.2

`16 décembre 2020`

> Comportements connus:
>
>   - Si le chiffrement TLS est configuré pour utiliser une paire
>     clé/certificat personnelle pour les entrées/sorties IPv4/6,
>     **les deux extrémités doivent être mises à jour** pour assurer
>     la communication.
>
>   - Si vous utilisez Centreon MAP avec un chiffrement TLS, assurez
>     vous de **mettre à jour le serveur MAP** à la version >= 20.10.2.

#### Correctifs

*TLS*

Credentials were not more loaded by the TLS connector anymore. This is fixed
with this new version.

*Custom variables*

They were updated several times in the database. It is fixed now.

*Build*

GnuTLS requirement now matches compilation version.

*BAM*

Reporting events were not stored into database because of truncated
Business Activities names causing *duplicate entry* errors.

### 20.10.1

`25 novembre 2020`

#### Correctifs

*Build*

Build on Centos8 fixed.

*Retention files*

The splitter class is now thread safe and does not need external locks
anymore. It is also far less strict and allows some reading and some
writing at the same time.

*TCP*

Writing on a tcp stream could slow down in case of many retention files. The
issue was essentially in the flush internal function.

#### Améliorations

*TCP connections*

TCP streams are really faster, especially when Broker has retention
files and there are a lot of traffic.

*SQL and storage streams*

Those streams have several improvements:

-   Events exchanges are much faster, especially when Broker has
    retention files.
-   Several queries have been changed to insert data in bulk, it is
    the case for custom variables and metrics.
-   There are cases where those streams could crash that have been
    also fixed.

*Statistics*

The thread pool has now its own statistics. For now, we have two
informations that are the number of threads it contains and its latency
in milliseconds that is the duration we have to wait to see a task
executed. We post a task to the thread pool at time T1, it is executed
by the thread pool at time T2, the latency is T2 - T1.

*Command line argument*

It is now possible to set the cbd pool size directly on the command line
with the –pool\_size X argument or -s X.

### 20.10.0

`21 octobre 2020`

> Comportements connus:
>
>   - Si Broker sur un Poller ou un Remote Server n'est pas mis à jour en
>     20.10 (ou utilisant une version antérieur à 20.04.9), la
>     communication entre ces Pollers ou Remote Servers et un Central
>     à jour peut ne pas fonctionner.
>
>     Comme toujours, nous **recommandons fortement** de mettre à jour
>     tous les composants en adéquation avec la version du Central.
>
>     Cependant, le temps de la mise à jour, la communication peut être
>     maintenue en s'assurant que les configurations des Brokers respectent
>     les conditions suivantes :
>
>     - le *chiffrement TLS* et la *compression* sont paramétrés à *Auto*
>       ou *No* sur l'entrée du Central,
>     - le *chiffrement TLS* et la *compression* sont paramétrés à *Auto*
>       ou *No* sur la sortie du Poller ou Remote Server.
>
>     Si le mode de connexion inversé (*one peer retention*) est utilisé,
>     la mise à jour de Broker est obligatoire.

#### Correctifs

- Contient tous les correctifs jusqu'à la version 20.04.9

## Centreon CLib

### 20.10.5

`27 octobre 2021`

#### Bug fixes

- Fixed a deadlock issue that blocked engine when all debug options were enabled


### 20.10.4

`20 octobre 2021`

#### Bug fixes

- Fixed an issue in centreon-clib that caused deadlocks when a process was killed
- Badly designed mutex could cause deadlocks in centreon-clib
- Fixed an issue that could cause deadlocks in the logs production


### 20.10.3

`15 juillet 2021`

#### Correctifs

- Libraries are loaded lazily now. This allows not having to check all link issues during loading.

### 20.10.2

`4 juin 2021`

#### Améliorations

- Compilation in C++14 with conan-center: bintray has stopped. We had to switch to conan-center. And then our conan dependencies had to be upgraded and then we had to switch to C++14. So here is the corresponding compilation.

### 20.10.1

`28 avril 2021`

#### Correctifs

- Start/Stop process\_manager mechanism is rewritten and much simpler. The consequences are that there are less deadlocks in the processes management.
- The simple cases that are addition, subtraction and some other cases, have had their computations simplified, that is to say less computations, so faster.

### 20.10.0

`October 21, 2020`

#### Correctifs

- A possible deadlock was removed when a process is added and at the same time a process is removed because in timeout.

## Centreon Connector Perl

### 20.10.3

`20 octobre 2021`

#### Bug fixes

- Badly designed mutex could cause deadlocks in centreon-clib
- Fixed an issue that could cause deadlocks in the logs production


### 20.10.2

`15 juillet 2021`

- Provide compatibility with centreon-clib 20.10.3

### 20.10.1

`4 juin 2021`

- Le build d'engine/broker a été migré de Bintray vers ConanCenter.

### 20.10.0

- Compatibilité avec les autres composants 20.10.

## Centreon Connector SSH

### 20.10.3

`20 octobre 2021`

#### Bug fixes

- Badly designed mutex could cause deadlocks in centreon-clib
- Fixed an issue that could cause deadlocks in the logs production


### 20.10.2

`15 juillet 2021`

- Provide compatibility with centreon-clib 20.10.3

### 20.10.1

`4 juin 2021`

- Le build d'engine/broker a été migré de Bintray vers ConanCenter.

### 20.10.0

- Compatibilité avec les autres composants 20.10.

## Centreon Gorgone

### 20.10.6

Release date: `December 15, 2021`

#### Bugfixes

- Make Gorgone’s private key readable by centreon-gorgone only
- Fixed export of configuration files on a poller with Debian 11
- Fixed error in log for autodiscovery module
- Merge YAML libraries to use only one
- Fixed uninitialized value using pull mode

### 20.10.5

`7 septembre 2021`

#### Améliorations

- Add endpoint to ask gorgoned to resync pollers configuration
- Add Centreon platform audit module
- Allow to define the list of the commands that can be run through the Action module

#### Correctifs

- Fixed only returns no_log when asking associated logs of a token through API

### 20.10.4

`10 juin 2021`

#### Correctifs

- [Anomaly] Le host ID était null dans les filtres de détection.

#### Améliorations

- Ajout d'une option de journalisation pour éviter une taille trop grande de la base SQLite
- Ajout de la dépendance pour perl-Libssh-Session-0.8

### 20.10.3

`4 mars 2021`

#### Améliorations

- [core] Envoi par blocs des commandes externes à Engine

### 20.10.2

`29 janvier 2021`

#### Correctifs

- [zmqclient] Harden communication to avoid "Protocol not good" errors
- [zmqclient] Increment ZMQ_LINGER period for some modules
- [zmqclient] Lot of ESTABLISHED connections on server side when network
  is flapping
- [sshclient] Command actions badly encoded lead to badly encoded messages
  in web UI (downtimes, acknowledgements)
- [sshclient] Uncaught messages lead to problems with statistics collection
  and Autodiscovery module.

#### Améliorations

- [anomalydetection] Reduce time interval between prediction downloads

### 20.10.1

`17 décembre 2020`

#### Correctifs

- [proxy] gorgone-proxy processes stucked when stopping gorgoned
- [core] Rare case of database handler wrongly instantiated due to race
  condition issue
- [core] Hardened management of message encoding/decoding
- [autodiscovery] Handle Centreon API modules version endpoint empty
  response
- [autodiscovery] Uncatched error when reaching Host Discovery global timeout
- [autodiscovery] Discovered services state flapped between enabled and
  disabled
- [autodiscovery] Service discovery email sending not working properly
  when having services with space in their name
- [autodiscovery] Service discovery email sending not working with groups
  of contacts

#### Améliorations

- [proxy] Force TCP reconnection after 3 ping timeout
- [zmqclient] ID is not necessary anymore in end targets configuration
  (ie Pollers)

### 20.10.0

`21 octobre 2020`

#### Correctifs

- Contient tous les correctifs jusqu'à la version 20.04.6

#### Améliorations

- [module] Add new core/pipeline module
- [module] Add new centreon/judge module
- [core] Add listener system
- [autodiscovery] Refacto centreon/autodiscovery module to use listener system
- [autodiscovery] Add service discovery in centreon/autodiscovery module
