# Release Notes

## IceTest-NG 2.17.1
* [FIX] Correctly set locale when a competition's country changes.
* [FIX] Judge cards not printing for riders without assigned age class.
* [FIX] Data export to WorldRanking.

## IceTest-NG 2.17
* [UPDATE] Add age class to judge cards.
* [UPDATE] Improve post-event export to IPZV.
* [FIX] Number of finalists in split-results when using 6 spots in AFIN.
* [UPDATE] Handling of red cards in Secretary mode.
* [UPDATE] Improve derived results for teams.
* [UPDATE] Submit results to IceCompass when not in Secretary mode.
* [UPDATE] Let judges re-send marks in Secretary mode.
* [UPDATE] Better support for PP1/P1/P2/P3 when using a video wall.
* [UPDATE] Improve data center's correction window for Secretary mode.
* [FIX] Correct starting order of 2nd/3rd/4th heat in P1/P3 for very slow times.
* [UPDATE] IPZV start list sorting procedure updated.
* [UPDATE] Secretary mode documentation updated.
* [UPDATE] Docs updated.
* [FIX] Repair button to delete participants.

## IceTest-NG 2.16
* [FIX] Fix automatic activation of ticker feed for split tests (CU-2eat5yg).
* [FIX] Always flag horse for data update when creating a new participant.
* [NEW] Allow P2 heat 2 start lists to be locked to heat 1.
* [NEW] Add manual ticker push button to start list page.
* [NEW] Display PersonID when looking up persons.
* [NEW] Add support for music playlists in single rider classes.
* [NEW] Support self check-in via app.
* [NEW] Introduce the IceTestNG newsletter.

## IceTest-NG 2.15
* [FIX] Update multi-starter markers after removing an entry (CU-1wegmwv).
* [UPDATE] Improve CSV handling while importing classic files.
* [NEW] Support for Danish ranking site IceCompass Id.

## IceTest-NG 2.11
* [NEW] Support mark-based, heated tests like PP3.
* [FIX] Judge cards for D3 (and some other FIN phase tests) don't print.

## IceTest-NG 2.10.7
* [FIX] Judge cards for FZ1 (and other FIN phase tests) don't print.
* [FIX] Starting lists of tests with no entries throw an error.
* [NEW] Admins can swap test definitions for existing tests.

## IceTest-NG 2.10.4
* [FIX] Incorrect scores in finals of tests with droppable sections (161).
* [UPDATE] Improve CouchDB handling in YHE tests.

## IceTest-NG 2.10.3
* [NEW] Provide a startlist template for riders' music wishes.
* [UPDATE] Don't put breaks on the track when SECR mode auto-advance is active.

## IceTest-NG 2.10.0
* [NEW] Send marks & comments to riders from the results page (when using SECR mode).
* [FIX] Use correct number of decimals when rounding in SECR mode.
* [FIX] Fix rounding in tests with more than 2 decimals (149).
* [UPDATE] Improve UI of the marks entry page when using SECR mode.
* [UPDATE] Make in-app messaging (Stomp) more reliable.

## IceTest-NG 2.9.9
* [NEW] Send marks & comments to riders from the results page (when using SECR mode).
* [UPDATE] Trigger mark processing from the marks entry page (when using SECR mode).

## IceTest-NG 2.9.8
* [UPDATE] Improve syncing sponsor logos.
* [UPDATE] Add street address to participant XLS export.
* [FIX] Always get the correct Not-Yet-Started list in SECR mode.

## IceTest-NG 2.9.7
* [UPDATE] Improve printing functions.
* [UPDATE] Allow self-checkin for everybody if desired.

## IceTest-NG 2.9.7
* [UPDATE] Improve printing functions.
* [UPDATE] Allow self-checkin for everybody if desired.

## IceTest-NG 2.9.6
* [FIX] Fix judges' days in WR report generation.

## IceTest-NG 2.9.5
* [UPDATE] Support custom test names via API.
* [UPDATE] Support product creation via API.
* [FIX] Ticker: Mark vs. time in results of race tests (148).
* [UPDATE] Update WR report generation (150).

## IceTest-NG 2.9.4
* [FIX] Fix STA filter in report card generation.
* [FIX] Startlists in P1 not sorted for heats 2,3,4 (139).
* [UPDATE] Improve self-check-in status info on startlsts.
* [UPDATE] Finals: Send push notifications to the ticker app only for complete results.

## IceTest-NG 2.9.3
* [FIX] Tie break pop up dialog not working (136).
* [FIX] Speaker screen not always updating (134).

## IceTest-NG 2.9.0
* [NEW] Add support for six riders in AFIN as described in FEIF RR 2021.
* [UPDATE] Tweak menu design.
* [UPDATE] Add more layouts for startlists, results.
* [FIX] Judge cards for FIN phases.

## IceTest-NG 2.8.8
* [UPDATE] Delete user if connected person is removed (131) 
* [FIX] SecMode: Publication of FIN phases (120)

## IceTest-NG 2.8.6
* [FIX] Vet Form 2 won't print (127) 
* [FIX] Add breaks, demo rider in startlists (124)
* [FIX] Removing a sponsor fails (121)

## IceTest-NG 2.8.5
* [UPDATE] Young Horse Evaluation: Improved report format

## IceTest-NG 2.8.4
* [FIX] Creating a new competition might fail
* [FIX] Columns in table views (participants, persons, horses etc.) not selectable

## IceTest-NG 2.8

## IceTest-NG 2.7

* [NEW] Add Self-Check-In for riders
* [NEW] Add Swedish translations
* [FIX] Updating your own password fails (issue 558)
* [FIX] Mark analysis graph 0.5 off (issue 562)
* [FIX] Corrections view skips 1st judge in independent secretary mode (issue 561)
* [FIX] Corrections view displays some riders more than once (issue 564)
* [FIX] Secretary report not working for rider names (issue 565)
* [FIX] Let national admins remove a future competition from the ticker
* [UPDATE] Improve report for riders with judges' comments
* [UPDATE] Allow removal of breaks for locked start lists (issue 559)

## IceTest-NG 2.6

* [NEW] Confirmation dialog when removing tests (issue 551)
* [NEW] Add new participant status values: SELFCHECKIN and PENDING (issue 540)
* [NEW] Expose starting numbers in results side of marks entry (issue 536)
* [NEW] Add feifid to the list of columns in the combinations overview (issue 532)
* [NEW] Expose combination comments on speaker screen (issue 531)
* [NEW] Move print button on marks entry page (issue 522)
* [NEW] Show test name in bold (large) font in marks entry headline (issue 521)
* [NEW] Decorate riders with more than one horse in a final (issue 519)
* [NEW] Show participant status on startlist (issue 518)
* [NEW] Quick nav between marks entry, start list and results for current test (issue 516)
* [NEW] Add column specific search for data tables (issue 505)
* [NEW] Allow resizing of popovers (issue 502)
* [NEW] Add FEIF ID when searching horses to make a new starting combination (issue 499)
* [NEW] Import complex time schedule from Excel (issue 496)
* [FIX] Cannot assign default judges for the whole competition (issue 549)
* [FIX] Don't include riders who have marks in the secretary marks start list (issue 545)
* [FIX] New persons not flowing back to new combination (issue 525)
* [FIX] Results with more than one page missing page header (issue 524)
* [FIX] Judges missing on printed results where combinations have withdrawn (issue 523)
* [FIX] Sorting errors in group start lists (issue 517)
* [FIX] Printing invoices generates blank second page (issue 510)
* [FIX] Check datatable filter persistence (issue 509)
* [FIX] Preserve location in datatable while editing (issue 506)
* [FIX] New balance not updating (issue 495)
* [FIX] Phase state in P1 with only two heats (issue 492)
* [FIX] Error sorting start list for heated tests (issue 483)
* [UPDATE] Filter variables, products, and competitions for normal users (issue 515)
* [UPDATE] loading FEIF judges (issue 537)

Version 2.6 was released on February 4, 2020.


## IceTest-NG 2.5

* [NEW] Derived results: Add support for "best n" marks in blocks for STAs (issue 455)
* [NEW] Derived results: Add optional <required_club> to XML definition to limit the participation in the calculation based on membership in a specific club (issue 383)
* [NEW] Add judge summary by country report (issue 478)
* [NEW] Add documentation on setting up calculation of derived results.
* [NEW] Option to add demo rider to judge cards (issue 268)
* [FIX] Saving ticker publication settings work as expected (issue 474)
* [FIX] Publish split result scores using the same conditions as complete results (time, points, or percentage) and with the correct decimal places (issues 462, 347)
* [FIX] FIN splits not sending to the ticker (issue 456)
* [FIX] Withdrawn combinations remain on ticker site (issue 228)
* [FIX] Withdrawals from LOCKED tests (issues 55, 235)
* [FIX] Rider withdrawn from BFIN might show up in AFIN (issue 442)
* [FIX] Orphan withdrawn entries on ticker (issue 443)
* [FIX] Withdrawing from an AFIN after the BFIN is COMPLETE pulls riders in from the preliminary (issue 445)
* [FIX] Next rider after a NOSHOW disappears from screen (issue 479)
* [FIX] Extreme late entries: Withdraws after the list is LOCKED (or ACTIVE) now prompts to DQ the rider (issue 52)
* [FIX] Print judge cards as expected in CFINs for split tests
* [UPDATE] Set default secretary position in single-judge shows (issue 472)
* [UPDATE] Derived results: The required number of marks per block can now be enforced by using  <marks_strict> in XML
* [UPDATE] Change the ‘rider’ label on reports and the Ticker for YHE tests (issue 408)
* [UPDATE] YHE tests now support derived results (issue 475)
* [UPDATE] Allow 2 character entry classes (think YR)
* [UPDATE] Admins can remove a competition from the Ticker from the competition ticker options tab provided there are no marks yet (issue 376)
* [UPDATE] Turn on columns for not-yet-started list on the speaker screen (issue 224)
* [UPDATE] Add Chief and Deputy Chief judge days to the WR export file (issue 195)

Version 2.5 was released on September 23, 2019.


## IceTest-NG 2.4

* [NEW] Add analysis feature for marks collected in secretary mode
* [NEW] Add support to hold final results back from the ticker until they are locked (issue 241)
* [NEW] Expose the per-test armband color list override in the edit test page
* [NEW] Export judges' days for non-international judges when creating WR report files
* [NEW] YHE: Sort start lists by horse age
* [NEW] Add fit-to-compete status
* [NEW] Add list of granted users to the index page (issue 269)
* [NEW] Add doping control selection feature (issue 122)
* [NEW] Add ability to CRUD snapshots of start lists (issue 36)
* [UPDATE] Add columns stable, email to Sporti import function
* [UPDATE] Add switch for secretary mode to competition setup page (issue 398)
* [FIX] Start lists may not be suggested correctly after the first time they are published (issue 216)
* [FIX] YHE: Error when no judge assigned (issue 467)
* [FIX] Reordering judges works as expected

Version 2.4 was released on September 1, 2019.


## IceTest-NG 2.3

* [NEW] Add comments to the secretary function
* [NEW] Trigger country-specific settings upon event creation (issue 406)
* [NEW] New column in Combinations overview with testlist (issue 413)
* [NEW] Enable timer for Gædingakeppni tests (issue 446)
* [FIX] Tiebreak causes ACTIVE state on ticker site (issue 440)
* [FIX] Pre-fill “0” for all future sections when a rider is entered as a NOSHOW (issue 444)
* [FIX] PP1 “missing“ judge (issue 438)
* [FIX] Correctly set multistarter status in heated entries (issue 441)
* [FIX] Updating testcode fails (issue 380)
* [FIX] Batch print of judge cards doesn't not set default judges (issue 433)
* [FIX] Long colour names not shown in start lists (issue 449)
* [UPDATE] Limit derived results templates to official and local ones

Version 2.3 was released on July 2, 2019.


## IceTest-NG 2.2

* [NEW] Support column ‚phonemobile‘ in Sporti import (issue 422)
* [NEW] Startlists: Add the group size to the toolbar
* [NEW] Print a grid-style judge card for tests with only once section
* [FIX] Cannot enter marks if test name has a single quote / apostrophe (issue 428)
* [FIX] Fix corner case in calculation of available spots in GK BFIN
* [FIX] Correctly detect when in a non-fullpage modal (issue 425)
* [FIX] Secretary Mode: Entering 0 (issue 424)
* [FIX] xFIN phase state after PREL (issue 426)
* [FIX] AFIN missing participants after completed BFIN (issue 427)
* [FIX] Multi-form printing (start lists and judge cards) confused by schedule order (issue 432)
* [FIX] Can't set groupsize for heated tests on startlist.cfm (issue 436)
* [FIX] Push startlists for heated tests to ticker site
* [UPDATE] Allow judges to be assigned to test phases when the start list is LOCKED
* [UPDATE] Startlists: use horizontal collapse in the footer to declutter the page by hiding the toolbar
* [UPDATE] Filter out funny chars in testcodes (issue 429)
* [UPDATE] Improve docs on Secretary Mode
* [UPDATE] Update XLS export component
* [UPDATE] Improve current ranking view in speaker screen, marks entry screen

Version 2.2 was released on May 23, 2019.


## IceTest-NG 2.1

* [NEW] Apply catalog updates to tests (issue 421)
* [NEW] Allow the rider to be changed in Gaedingakeppni finals
* [NEW] Support for new Gaedingakeppni tests GDY-A and GDY-B
* [FIX] Tests with apostrophe in the testname cannot show startlist (issue 420)
* [FIX] Automatic age assignment does not assign Junior riders (issue 414)
* [FIX] Import of X-level tests for DE/CH/NL competitions
* [UPDATE] Improve judge cards for group tests with more than 5 sections
* [UPDATE] Support for external CSS in video wall output (issue 399)
* [UPDATE] Introducing Quick Controls for video wall features (thanks to Andreas Hejndorf)
* [UPDATE] Import Sporti files without starting numbers (STA) (issue 417)
* [UPDATE] Handle dis-/enabling of CFin and/or BFin for active test (issue 418)

Version 2.1 was released on April 19, 2019.


## IceTest-NG 2.0

* [NEW] Start lists can now actively be locked by the user
* [NEW] Add a new judge level called "local" (issue 411)
* [NEW] Notify users when getting EventAdmin permission for competitions in Denmark (issue 403)
* [NEW] Allow signup systems used in CH/DE/NL to transfer competition data to NG
* [NEW] Print certificates for Young Horse Evaluations (IPZV)
* [NEW] Publish documentation on importing Sporti files (issue 405)
* [UPDATE] Improve Young Horse Evaluations
* [UPDATE] Tölt in Harmony tests are now known as Figure Tests FG1/FG2/FG3
* [FIX] Printing vet-check forms with diagrams
* [FIX] Ranking calculation for Young Horse Evaluations
* [FIX] Removing tests not working (issue 409)
* [FIX] Catalog refresh fails for P2 (issue 412)

Version 2.0 was released on March 31, 2019.


## IceTest-NG 0.19

* [NEW] Import participant data from CSV files (generated by Sporti, IceTest Classic) (issue 384)
* [NEW] Introducing Young Horse Evaluations
* [NEW] Attribute marks to a different judge (issue 252)
* [NEW] Test catalog XML now supports SECR phase (see issue 389)
* [FIX] SetDefaultJudges can block secretary marks feature (issue 389)
* [UPDATE] Improve start list printing when preliminaries and finals have different sections
* [UPDATE] Improve secretary features when preliminaries and finals have different sections

Version 0.19 was released on January 7, 2019.

## IceTest-NG 0.18

* [NEW] Make carrying judges over optional (issue 387)
* [FIX] Turning off test phases (competitions -> edit test list) assumes the current competition (issue 385)
* [FIX] Editing times in the schedule (issue 358)
* [FIX] Ticker has no start lists for pace disciplines (issue 382)
* [UPDATE] Improve local storage use for mark input by secretaries
* [FIX] Handle club membership data correctly when not using a web service to look up memberships

Version 0.18 was released on September 28, 2018.

## IceTest-NG 0.17

* [FIX] Removing or moving judges can prevent proper calculation of marks (issue 379)
* [FIX] Stop deleting completed phases from the schedule (issue 378)
* [FIX] Improve rank assignment for very slow times in time-based tests (issue 377)
* [FIX] Cannot unschedule phase if all have been scheduled (issue 371)
* [FIX] Save marks correctly in case of a lost shoe (issue 366)
* [FIX] Always advance winner of CFIN to BFIN (issue 365)
* [FIX] Fix the selection of a specific competition from the breadcrumb
* [FIX] Drag/drop behaves as expected in start lists that have breaks (issue 363)
* [UPDATE] Make the index page look a little nicer
* [UPDATE] Visually group the test catalogs on the left side of the panel when editing the tests in a given competition
* [UPDATE] Improve mark input for judges
* [NEW] remove a phase from the schedule if it is turned off in the competition test list (issue 372)
* [NEW] Do not remove judges from a test phase if marks exist (issue 370)
* [NEW] Make speaker phase state change messages into links to the appropriate speaker page (issue 375)
* [NEW] Display a Reconnect button on the secretary page when the websocket disconnects
* [NEW] Improve new menu controls on small devices (issue 364)
* [NEW] Speed up generation of overview PDF
* [NEW] Allow derived results to be dropped (issue 348)
* [NEW] Add reports on products sold for a competition


Version 0.17 was released on September 5, 2018.

## IceTest-NG 0.16

* [NEW] Support mark input for judges' secretaries.
* [NEW] Add support for multiple video wall outputs (e.g. video wall and backstage monitor)
* [UPDATE] Gaedingakeppni: 7 AFIN, but 8 BFIN participants
* [FIX] Withdrawal from AFIN after BFIN took place (issue 357)

Version 0.16 was released on July 7, 2018.



***
*$Author$*  
*$Rev$*  
*$Date$*  
