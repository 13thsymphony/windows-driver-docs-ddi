---
UID: NS:hbapiwmi._GetPersistentBinding2_IN
title: _GetPersistentBinding2_IN
author: windows-driver-content
description: The GetPersistentBinding2_IN structure is used to deliver input parameter data to the GetPersistentBinding2 WMI method.
old-location: storage\getpersistentbinding2_in.htm
old-project: storage
ms.assetid: 646378f8-9037-4c40-bcbc-5ffe380e6279
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _GetPersistentBinding2_IN, GetPersistentBinding2_IN, *PGetPersistentBinding2_IN
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
req.alt-api: GetPersistentBinding2_IN
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
req.typenames: GetPersistentBinding2_IN, *PGetPersistentBinding2_IN
---

# _GetPersistentBinding2_IN structure



## -description
The GetPersistentBinding2_IN structure is used to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554959">GetPersistentBinding2</a> WMI method.



## -syntax

````
typedef struct _GetPersistentBinding2_IN {
  UCHAR PortWWN[8];
  ULONG InEntryCount;
} GetPersistentBinding2_IN, *PGetPersistentBinding2_IN;
````


## -struct-fields

### -field PortWWN

Contains a worldwide name that indicates the port whose persistent bindings are to be retrieved. 


### -field InEntryCount

Indicates the number of binding entries that the WMI provider can report.


## -remarks
The WMI tool suite generates a declaration of the GetPersistentBinding2_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562509">MSFC_HBAFCPInfo WMI Class</a>.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554959">GetPersistentBinding2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetPersistentBinding2_IN structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

