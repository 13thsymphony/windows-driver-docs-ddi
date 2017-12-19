---
UID: NS.HBAPIWMI._MSFC_HBAPORTSTATISTICS
title: _MSFC_HBAPortStatistics
author: windows-driver-content
description: The MSFC_HBAPortStatistics structure contains statistics information about a port.
old-location: storage\msfc_hbaportstatistics.htm
old-project: storage
ms.assetid: 0274b3c7-c17e-45bf-867f-2b0f741b2ecb
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _MSFC_HBAPortStatistics, PMSFC_HBAPortStatistics, MSFC_HBAPortStatistics, *PMSFC_HBAPortStatistics
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSFC_HBAPortStatistics
req.alt-loc: hbapiwmi.h
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

# _MSFC_HBAPortStatistics structure



## -description
The MSFC_HBAPortStatistics structure contains statistics information about a port.



## -syntax

````
typedef struct _MSFC_HBAPortStatistics {
  LONGLONG SecondsSinceLastReset;
  LONGLONG TxFrames;
  LONGLONG TxWords;
  LONGLONG RxFrames;
  LONGLONG RxWords;
  LONGLONG LIPCount;
  LONGLONG NOSCount;
  LONGLONG ErrorFrames;
  LONGLONG DumpedFrames;
  LONGLONG LinkFailureCount;
  LONGLONG LossOfSyncCount;
  LONGLONG LossOfSignalCount;
  LONGLONG PrimitiveSeqProtocolErrCount;
  LONGLONG InvalidTxWordCount;
  LONGLONG InvalidCRCCount;
} MSFC_HBAPortStatistics, *PMSFC_HBAPortStatistics;
````


## -struct-fields

### -field SecondsSinceLastReset

Contains the number of seconds since the statistics were last reset.


### -field TxFrames

Contains the number of total transmitted fibre channel frames across all protocols and classes.


### -field TxWords

Contains the number of total transmitted fibre channel words across all protocols and classes.


### -field RxFrames

Contains the number of received fibre channel frames across all protocols and classes.


### -field RxWords

Contains the number of received fibre channel words across all protocols and classes.


### -field LIPCount

Contains the number of loop initialization primitive sequence (LIP) events that have occurred on a arbitrated loop.


### -field NOSCount

Contains the number of nonoperational state primitive sequence (NOS) events that have occurred on the switched fabric.


### -field ErrorFrames

Contains the number of frames that have been received in error.


### -field DumpedFrames

Contains the number of frames that were lost due to a lack of host buffers available.


### -field LinkFailureCount

Contains the link failure count. 


### -field LossOfSyncCount

Contains the loss of synchronization count. 


### -field LossOfSignalCount

Contains the loss of signal count. 


### -field PrimitiveSeqProtocolErrCount

Contains the primitive sequence protocol error count. 


### -field InvalidTxWordCount

Contains a count of the number of invalid transmissions. 


### -field InvalidCRCCount

Contains a count of the number frames with invalid cyclic redundancy checksums. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.msfc_hbaportstatistics_wmi_class">MSFC_HBAPortStatistics WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_HBAPortStatistics structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

