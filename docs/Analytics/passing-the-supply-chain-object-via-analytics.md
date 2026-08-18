---
title: "Passing the Supply Chain Object via Analytics"
excerpt: "The purpose of the document is to explain how to pass Supply chain Object in tag via kv55"
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
---

**Tag**

The value can be passed in kv55, if kv55 is not already in the tag provided by Pixalate, please add it in as follows

kv55=[SupplyChainObject]

**Example JS Tag with kv55**

``

**Example** **1x1 Tag with kv55**

`https://adrta.com/i?clid=[CLIENTID]&paid;=[PARTNER_ID]&avid;=[ADVERTISER_ID]&publisherId;=[PUBLISHER_ID]&**kv55=[SupplyChainObject]** &kv24;=[SUPPLY_TYPE]`

**Format**

\- [SupplyChainObject] should be replaced by a serialized value

The serialization value is composed of two items;

● the SupplyChainObject properties

● SupplyChainNode array

These two items are separated by a bang (“!”) character.

SupplyChainObject}!{SupplyChainNode array}

**\- Properties**

There are two properties

● Version

● Complete

These two values must be included and separated by ‘,’

ver,complete

**\- Order Of Node Properties**

If there are more than one node then each node is also separated by bang (‘!’) character.

asi,sid,hp,rid,name,domain,ext

**Example of Multiple Hops with all the properties supplied**

**"schain" : {**

**"ver": "1.0",**

**"complete" : 1,**

**"nodes" : [**

**{**

**"asi":"exchange1.com",**

**"sid":"1234",**

**"hp":1,**

**"rid":"bid-request-1",**

**"name":"publisher",**

**"domain":"publisher.com"**

**},**

**{**

**"asi":"exchange2.com",**

**"sid":"abcd",**

**"hp":1,**

**"rid":"bid-request-2",**

**"name":"intermediary",**

**"domain":"intermediary.com"**

**}**

**]**

**}**

**1.0,1!exchange1.com,1234,1,bid-request-1,publisher,publisher.com!exchange2.com,abcd,1**

**,bid-request2,intermediary,intermediary.com**

The last node should be the client’s ID/info and is expected to be added before passing in kv55, if not already in the serialized value.
