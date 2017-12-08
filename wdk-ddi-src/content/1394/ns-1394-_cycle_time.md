---
UID: NS.1394._CYCLE_TIME
title: _CYCLE_TIME
author: windows-driver-content
description: The CYCLE_TIME structure contains the IEEE 1394 isochronous cycle time.
old-location: ieee\cycle_time.htm
old-project: IEEE
ms.assetid: dcb19338-3848-4f90-876c-357f92fb2637
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: _CYCLE_TIME, *PCYCLE_TIME, CYCLE_TIME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CYCLE_TIME
req.alt-loc: 1394.h
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

# _CYCLE_TIME structure



## -description
The CYCLE_TIME structure contains the IEEE 1394 isochronous cycle time.


## -syntax

````
typedef struct _CYCLE_TIME {
  ULONG CL_CycleOffset  :12;
  ULONG CL_CycleCount  :13;
  ULONG CL_SecondCount  :7;
} CYCLE_TIME, *PCYCLE_TIME;
````


## -struct-fields

### -field CL_CycleOffset

Specifies the number of clock ticks (based on a 24.576 MHz clock) since the current isochronous cycle began.

### -field CL_CycleCount

Specifies the number of isochronous cycles in the current second.

### -field CL_SecondCount

Specifies the number of seconds. This count wraps to zero every 128 seconds.

## -remarks
The layout of this structure matches that of the CYCLE_TIME register in the <i>IEEE 1394-1995 specification</i>.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>1394.h (include 1394.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537656">REQUEST_ISOCH_QUERY_CYCLE_TIME</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537649">REQUEST_ISOCH_ALLOCATE_RESOURCES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537655">REQUEST_ISOCH_LISTEN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537660">REQUEST_ISOCH_TALK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537401">ISOCH_DESCRIPTOR</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20CYCLE_TIME structure%20 RELEASE:%20(11/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
