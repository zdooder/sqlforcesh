## sqlforcesh

sqlforcesh is a simple command-line shell in python that uses the very excellent SQLForce library from Capstorm to provide a query interface to Salesforce instances.

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

SQLForce used to include such a shell, but recent versions seem to have abandoned it.  I have come to rely on
using the shell for various "quick and dirty" queries, so I've created this as a replacement.

## Installation

Currently this needs the SQLForce package and terminaltables python module.

