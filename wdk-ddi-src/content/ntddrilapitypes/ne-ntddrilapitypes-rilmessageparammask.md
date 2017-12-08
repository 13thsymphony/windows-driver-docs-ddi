---
UID: NE.ntddrilapitypes.RILMESSAGEPARAMMASK
title: RILMESSAGEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageparammask.htm
old-project: netvista
ms.assetid: 718c9d10-fd89-4d31-815e-da4dea0a3f34
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILMESSAGEPARAMMASK, RILMESSAGEPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILMESSAGEPARAMMASK
req.alt-loc: ntddrilapitypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# RILMESSAGEPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef enum _RILMESSAGEPARAMMASK { 
  RIL_PARAM_M_TYPE,
  RIL_PARAM_M_FLAGS,
  RIL_PARAM_M_ORIGADDRESS,
  RIL_PARAM_M_TGTRECIPADDRESS,
  RIL_PARAM_M_DESTADDRESS,
  RIL_PARAM_M_SCRECEIVETIME,
  RIL_PARAM_M_TGTSCRECEIVETIME,
  RIL_PARAM_M_TGTDISCHARGETIME,
  RIL_PARAM_M_PROTOCOLID,
  RIL_PARAM_M_DATACODING,
  RIL_PARAM_M_TGTDLVSTATUS,
  RIL_PARAM_M_VPFORMAT,
  RIL_PARAM_M_VP,
  RIL_PARAM_M_GEOSCOPE,
  RIL_PARAM_M_MSGCODE,
  RIL_PARAM_M_UPDATENUMBER,
  RIL_PARAM_M_ID,
  RIL_PARAM_M_TOTALPAGES,
  RIL_PARAM_M_PAGENUMBER,
  RIL_PARAM_M_HDRLENGTH,
  RIL_PARAM_M_SERIALNUMBER,
  RIL_PARAM_M_MSGLENGTH,
  RIL_PARAM_M_HDR,
  RIL_PARAM_M_MSG,
  RIL_PARAM_M_WARNINGTYPE,
  RIL_PARAM_M_EUSERALERT,
  RIL_PARAM_M_POPUP,
  RIL_PARAM_M_MSGID,
  RIL_PARAM_M_ORIGSUBADDRESS,
  RIL_PARAM_M_DESTSUBADDRESS,
  RIL_PARAM_M_DIGIT,
  RIL_PARAM_M_PRIVACY,
  RIL_PARAM_M_PRIORITY,
  RIL_PARAM_M_TELESERVICE,
  RIL_PARAM_M_LANG,
  RIL_PARAM_M_VALIDITYPERIODABS,
  RIL_PARAM_M_VALIDITYPERIODREL,
  RIL_PARAM_M_DEFERREDDELTIMEABS,
  RIL_PARAM_M_DEFERREDDELTIMEREL,
  RIL_PARAM_M_ENCODING,
  RIL_PARAM_M_USERRESPONSECODE,
  RIL_PARAM_M_DISPLAYMODE,
  RIL_PARAM_M_CALLBACKNUM,
  RIL_PARAM_M_NUMMSGS,
  RIL_PARAM_M_CAUSECODE,
  RIL_PARAM_M_REPLYSEQNUMBER,
  RIL_PARAM_M_SERVICEID,
  RIL_PARAM_M_USERACK,
  RIL_PARAM_M_DELIVERYACK,
  RIL_PARAM_M_ALERTONMSGDELIVERY,
  RIL_PARAM_M_HDRLENGTHCDMA,
  RIL_PARAM_M_MSGSTATUSTYPE,
  RIL_PARAM_M_BEARERREPLYACK,
  RIL_PARAM_M_ALL_IN_DELIVER,
  RIL_PARAM_M_ALL_IN_STATUS,
  RIL_PARAM_M_ALL_OUT_SUBMIT,
  RIL_PARAM_M_ALL_BC_GENERAL,
  RIL_PARAM_M_ALL_IN_IS637DELIVER,
  RIL_PARAM_M_ALL_OUT_IS637SUBMIT,
  RIL_PARAM_M_ALL_IN_IS637STATUS,
  RIL_PARAM_M_ALL_OUT_IS637STATUS
} RILMESSAGEPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_M_TYPE


### -field RIL_PARAM_M_FLAGS


### -field RIL_PARAM_M_ORIGADDRESS


### -field RIL_PARAM_M_TGTRECIPADDRESS


### -field RIL_PARAM_M_DESTADDRESS


### -field RIL_PARAM_M_SCRECEIVETIME


### -field RIL_PARAM_M_TGTSCRECEIVETIME


### -field RIL_PARAM_M_TGTDISCHARGETIME


### -field RIL_PARAM_M_PROTOCOLID


### -field RIL_PARAM_M_DATACODING


### -field RIL_PARAM_M_TGTDLVSTATUS


### -field RIL_PARAM_M_VPFORMAT


### -field RIL_PARAM_M_VP


### -field RIL_PARAM_M_GEOSCOPE


### -field RIL_PARAM_M_MSGCODE


### -field RIL_PARAM_M_UPDATENUMBER


### -field RIL_PARAM_M_ID


### -field RIL_PARAM_M_TOTALPAGES


### -field RIL_PARAM_M_PAGENUMBER


### -field RIL_PARAM_M_HDRLENGTH


### -field RIL_PARAM_M_SERIALNUMBER


### -field RIL_PARAM_M_MSGLENGTH


### -field RIL_PARAM_M_HDR


### -field RIL_PARAM_M_MSG


### -field RIL_PARAM_M_WARNINGTYPE


### -field RIL_PARAM_M_EUSERALERT


### -field RIL_PARAM_M_POPUP


### -field RIL_PARAM_M_MSGID


### -field RIL_PARAM_M_ORIGSUBADDRESS


### -field RIL_PARAM_M_DESTSUBADDRESS


### -field RIL_PARAM_M_DIGIT


### -field RIL_PARAM_M_PRIVACY


### -field RIL_PARAM_M_PRIORITY


### -field RIL_PARAM_M_TELESERVICE


### -field RIL_PARAM_M_LANG


### -field RIL_PARAM_M_VALIDITYPERIODABS


### -field RIL_PARAM_M_VALIDITYPERIODREL


### -field RIL_PARAM_M_DEFERREDDELTIMEABS


### -field RIL_PARAM_M_DEFERREDDELTIMEREL


### -field RIL_PARAM_M_ENCODING


### -field RIL_PARAM_M_USERRESPONSECODE


### -field RIL_PARAM_M_DISPLAYMODE


### -field RIL_PARAM_M_CALLBACKNUM


### -field RIL_PARAM_M_NUMMSGS


### -field RIL_PARAM_M_CAUSECODE


### -field RIL_PARAM_M_REPLYSEQNUMBER


### -field RIL_PARAM_M_SERVICEID


### -field RIL_PARAM_M_USERACK


### -field RIL_PARAM_M_DELIVERYACK


### -field RIL_PARAM_M_ALERTONMSGDELIVERY


### -field RIL_PARAM_M_HDRLENGTHCDMA


### -field RIL_PARAM_M_MSGSTATUSTYPE


### -field RIL_PARAM_M_BEARERREPLYACK


### -field RIL_PARAM_M_ALL_IN_DELIVER


### -field RIL_PARAM_M_ALL_IN_STATUS


### -field RIL_PARAM_M_ALL_OUT_SUBMIT


### -field RIL_PARAM_M_ALL_BC_GENERAL


### -field RIL_PARAM_M_ALL_IN_IS637DELIVER


### -field RIL_PARAM_M_ALL_OUT_IS637SUBMIT


### -field RIL_PARAM_M_ALL_IN_IS637STATUS


### -field RIL_PARAM_M_ALL_OUT_IS637STATUS


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>