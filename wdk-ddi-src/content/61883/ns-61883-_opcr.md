---
UID: NS.61883._OPCR
title: _OPCR
author: windows-driver-content
description: The OPCR structure contains initialization values for an output plug.
old-location: ieee\opcr.htm
old-project: IEEE
ms.assetid: fbd6fa74-eb39-4240-947e-1edec1365a83
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: _OPCR, *POPCR, OPCR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OPCR
req.alt-loc: 61883.h
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

# _OPCR structure



## -description
The OPCR structure contains initialization values for an output plug. 


## -syntax

````
typedef struct _OPCR {
  ULONG Payload  :10;
  ULONG OverheadID  :4;
  ULONG DataRate  :2;
  ULONG Channel  :6;
  ULONG Reserved  :2;
  ULONG PPCCounter  :6;
  ULONG BCCCounter  :1;
  ULONG OnLine  :1;
} OPCR, *POPCR;
````


## -struct-fields

### -field Payload

Specifies the connection speed. 

### -field OverheadID

Specifies, for an unconnected output plug, the upper bounds for the bandwidth that the output plug needs for the transmission of an isochronous packet. 

### -field DataRate

Indicates the bit rate that the output plug uses to transmit an isochronous packet. 

### -field Channel

Indicates the channel number that the output plug shall use to transmit the isochronous data flow, for a suspended output plug. For an active output plug it indicates the actual channel number that the output plug uses to transmit the isochronous data flow. For an unconnected output plug it has no meaning.

### -field Reserved

Reserved. 

### -field PPCCounter

Indicates the number of point-to-point connections to the output plug. 

### -field BCCCounter

Indicates, when one, that there is a broadcast-out connection to the output plug. When zero it indicates that there is no connection. 

### -field OnLine

Indicates, when one, that the corresponding output plug is on-line. When zero it indicates that the output plug is off-line.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>61883.h (include 61883.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537010">AV_PCR</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20OPCR structure%20 RELEASE:%20(11/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
