---
UID : NE:ntddrilapitypes.RILMSGMWITYPE
title : RILMSGMWITYPE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgmwitype.htm
old-project : netvista
ms.assetid : e5faa899-194a-412c-9308-a84227a31a6a
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilmsgmwitype, RIL_MSGMWITYPE_VOICEMAIL, RILMSGMWITYPE enumeration [Network Drivers Starting with Windows Vista], RIL_MSGMWITYPE_VIDEOMAIL, RIL_MSGMWITYPE_PAGER, ntddrilapitypes/RIL_MSGMWITYPE_VIDEOMAIL, ntddrilapitypes/RIL_MSGMWITYPE_PAGER, RIL_MSGMWITYPE_FAX, ntddrilapitypes/RIL_MSGMWITYPE_MULTIMEDIA, RIL_MSGMWITYPE_TEXT, RILMSGMWITYPE, ntddrilapitypes/RIL_MSGMWITYPE_FAX, RIL_MSGMWITYPE_MULTIMEDIA, ntddrilapitypes/RIL_MSGMWITYPE_TEXT, RIL_MSGMWITYPE_MAX, ntddrilapitypes/RIL_MSGMWITYPE_MAX, ntddrilapitypes/RIL_MSGMWITYPE_VOICEMAIL, ntddrilapitypes/RILMSGMWITYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddrilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : RILMSGMWITYPE
---

# RILMSGMWITYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGMWITYPE { 
  RIL_MSGMWITYPE_VOICEMAIL,
  RIL_MSGMWITYPE_VIDEOMAIL,
  RIL_MSGMWITYPE_FAX,
  RIL_MSGMWITYPE_PAGER,
  RIL_MSGMWITYPE_MULTIMEDIA,
  RIL_MSGMWITYPE_TEXT,
  RIL_MSGMWITYPE_MAX
} RILMSGMWITYPE;
````

## Constants

<table>

<tr>
<td>RIL_MSGMWITYPE_FAX</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGMWITYPE_MAX</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGMWITYPE_MULTIMEDIA</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGMWITYPE_NONE</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGMWITYPE_PAGER</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGMWITYPE_TEXT</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGMWITYPE_VIDEOMAIL</td>
<td></td>
</tr>

<tr>
<td>RIL_MSGMWITYPE_VOICEMAIL</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |