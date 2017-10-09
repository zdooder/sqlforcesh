## sqlforcesh

sqlforcesh is a simple command-line shell in python that uses the very excellent 
[SQLForce library from Capstorm](https://www.capstorm.com/sqlforce-project)
to provide a basic interface to Salesforce instances.  

The interface is probably reasonably familiar to people who have used MySQL or
Postgres databases before.

## Example

```
sqlforce> connect
sqlforce> select id from account where name='IBM';
┌────────────────────┐
│ id                 │
├────────────────────┤
│ 0018000000RA0HjAAL │
│ 0018000000vT6ExAAK │
└────────────────────┘
2 records
sqlforce> select count() from contact where account.BillingCountry='USA'
1238 records
sqlforce> describe Payment__c
┌────────────────────────┬───────────┐
│ Field Name             │ Type      │
├────────────────────────┼───────────┤
│ CreatedById            │ reference │
│ CreatedDate            │ datetime  │
│ Duration__c            │ double    │
│ Expiration_Date__c     │ date      │
│ Grace_Period__c        │ double    │
│ Id                     │ id        │
│ IsDeleted              │ boolean   │
│ LastActivityDate       │ date      │
│ LastModifiedById       │ reference │
│ LastModifiedDate       │ datetime  │
│ License_Master__c      │ reference │
│ Lock_Out_Date__c       │ date      │
│ Name                   │ string    │
│ Renewal_Opportunity__c │ reference │
│ Renewal_Price__c       │ currency  │
│ Start_Date__c          │ date      │
│ Status__c              │ string    │
│ SystemModstamp         │ datetime  │
└────────────────────────┴───────────┘
sqlforce>
```

## Motiviation

SQLForce used to include such a shell in its distribution, but recent versions no longer include it.
Since I have come to rely on using the shell for various "quick and dirty" queries and updates, I've 
created this as a replacement.

This code is not particularly elegant or clever, but if it works that's what I consider important.

## Installation

Currently this needs the SQLForce package and terminaltables python module.

There is a sample config in `sqlforcesh.ini-default` and `sqlforceshrc-default`.  The script looks for
them in your home directory.  I built (and use) this on Linux, so Windows and Mac users are welcome to 
adjust as needed.

