---
UID: NS:hbapiwmi._GetFcpTargetMapping_IN
title: _GetFcpTargetMapping_IN
author: windows-driver-content
description: The GetFcpTargetMapping_IN structure is used to report the output parameter data of the GetFcpTargetMapping WMI method to the WMI client.
old-location: storage\getfcptargetmapping_in.htm
old-project: storage
ms.assetid: a07a97ea-17f0-4e24-89c5-1b24600ac497
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _GetFcpTargetMapping_IN, *PGetFcpTargetMapping_IN, GetFcpTargetMapping_IN
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
req.alt-api: GetFcpTargetMapping_IN
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
req.typenames: *PGetFcpTargetMapping_IN, GetFcpTargetMapping_IN
---

# _GetFcpTargetMapping_IN structure



## -description
The GetFcpTargetMapping_IN structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> WMI method to the WMI client.



## -syntax

````
typedef struct _GetFcpTargetMapping_IN {
  UCHAR HbaPortWWN[8];
  ULONG InEntryCount;
} GetFcpTargetMapping_IN, *PGetFcpTargetMapping_IN;
````


## -struct-fields

### -field HbaPortWWN

Contains a worldwide name for the port whose table of mappings is to be retrieved. 


### -field InEntryCount

Indicates the total number of persistent bindings associated with the HBA.


## -remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a> WMI method queries a WMI provider for mappings between the information that uniquely identifies a set of logical units for the operating system and the fibre channel protocol (FCP) identifiers for the logical units.

The WMI tool suite generates a declaration of the GetFcpTargetMapping_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554948">GetFcpTargetMapping</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetFcpTargetMapping_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

