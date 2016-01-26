# Mantainability and reuse

## Determine appropriate solutions to support globalization

### Deploying Salesforce Globally

Ressource: Deploying Salesforce Globally

####  Translation Basics

Language vs. Locate vs. Currency settings

* Language
	* Controls labels and translations presented to the user
	* Example: 
		* {!$Label.Lastname} -> Firstname, Vorname
* Locate
	* Controls date formats, time and name displayed
	* Example: 
		* 12/7/2015 vs. 7/12/2015
		* 1:15 on vs. 13:15
		* JC Whitfield vs Whitfield JC
* Currency setting
	* controls currencies and number sparators
	* Example: 
		* 2.95 vs. 9,99

#### Translations Workbench
* active languages can be translated by designate translators vis translation settings
* Trnslators allow non system administrators to change translations
* Manage package labels can be overwritten

#### Formulas
* Avoid text strings in formulas
* Expressions returning True or False are ok
* Avoid Formula function where expression or lieral expression are part of the makeup of the function — **DO TO: WHAT?**
* Avoid LEFT, LEN, RIGHT because of different text lengths in different languages

#### Picklists
* Utilize picklists instead of returning literal values for formulas
* Are language specifc
* Use picklists for field that execs want to be able to see in their local language

#### Not Translated
* Home Page Components
* Dashboard Components
* Folder Names
* Public Calendars

#### Lessons Learned
* Double check translations
* Have some internal translators on-call
* Establish a process to change a translation
* Utilize local language fields —> Create a field “Local Company Name”
* If mutliple languages are used only in portals, check each language on a regular basis



### Currencies

####  Overview Multi-Currency
* setting up available currencies
* mantaining conversion rates
* Enter and view amount fields in different languages

BUT: NO REPORTING OR TRACKING of currency gain or losses based on fluctuation

#### Currency Types
* Personal Currency
	* Default currency set for new records
	* Currency used for quotas, forecasts and reports
* Record Currency
	* Every record has a RC that determines the amount of the record
* Corporate Currency
	* All exchanges rates are based on CC

##### Hwo tho use multi currency
* On a record the record currency and the amount converted to the personal currency is shown
* Currency can determined per report
* Converted amount can be displayed as well

#### Questions to ask
* Which currencies are needed?
* What will be your corporate currency?
* How often will conversion rate be updated and will perform updates?
* 

### Learnings
* Number format is controlled by the currency settings
* Translators can change translation. They are determined by the translation settings (Workbench)
* Overwrite translations of managed packages is possible
* Try to use picklists instead of literals
* Use picklists to allow execs to see content in their language
* Create local fields like “Local Company Name”
* Mutli-Currency management does not allow to report or track gai or losses based on fluctuations (e.g. dated currency on specific record…)