---
UID: NF:poscx.PosCxCleanPendingRequests
title: PosCxCleanPendingRequests function
author: windows-driver-content
description: PosCxCleanPendingRequests is called to cancel all pending requests for a given caller, identified by the open instance.
old-location: pos\poscxcleanpendingrequests.htm
old-project: pos
ms.assetid: FD6036D5-C316-43E6-8C37-067F5705BCB6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PosCxCleanPendingRequests
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PosCxCleanPendingRequests
req.alt-loc: poscx.h
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
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# PosCxCleanPendingRequests function



## -description
      PosCxCleanPendingRequests is called to cancel all pending requests for a given  

      caller, identified by the open instance.



## -syntax

````
VOID PosCxCleanPendingRequests(
  _In_     WDFDEVICE     device,
  _In_opt_ WDFFILEOBJECT callerFileObj,
  _In_     NTSTATUS      completionStatus
);
````


## -parameters

### -param device [in]

A handle to a framework device object that represents the device.


### -param callerFileObj [in, optional]

      A handle to a framework file object for which all pending requests should be 

          cancelled, or NULL to cancel all pending requests.


### -param completionStatus [in]

An appropriate NTSTATUS error code that indicates success or failure.


## -returns
This function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Product

</th>
<td width="70%">
Windows 10 or later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Poscx.h (include Poscx.h)</dt>
</dl>
</td>
</tr>
</table>