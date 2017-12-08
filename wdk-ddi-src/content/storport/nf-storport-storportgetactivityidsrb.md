---
UID: NF.storport.StorPortGetActivityIdSrb
title: StorPortGetActivityIdSrb function
author: windows-driver-content
description: Retrieves the Event Tracing for Windows (ETW) activity ID associated with a request block.
old-location: storage\storportgetactivityidsrb.htm
old-project: storage
ms.assetid: 63E956F5-C87C-45AA-BE16-2AD07F3BA050
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: StorPortGetActivityIdSrb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetActivityIdSrb
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: Any
req.product: Windows 10 or later.
---

# StorPortGetActivityIdSrb function



## -description
Retrieves the Event Tracing for Windows (ETW) activity ID associated with a request block.


## -syntax

````
ULONG StorPortGetActivityIdSrb(
  _In_  PVOID               HwDeviceExtension,
  _In_  PSCSI_REQUEST_BLOCK Srb,
  _Out_ LPGUID              ActivityId
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).

### -param Srb [in]

The request block to retrieve the ETW activity ID for.

### -param ActivityId [out]

A pointer to a caller-supplied GUID to receive the ETW activity ID.

## -returns
A status value indicating the result of the notification. This can be one of these values:
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The ETW activity ID was returned in <i>ActivityId</i>.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The pointer in <i>ActivityId</i> or <i>Srb</i> is NULL.
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>An ETW activity ID is not associated with the request in <i>Srb</i>.

 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Storport.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any
</td>
</tr>
</table>