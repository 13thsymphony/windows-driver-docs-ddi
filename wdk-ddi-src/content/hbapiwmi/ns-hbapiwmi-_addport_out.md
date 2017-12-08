---
UID: NS.HBAPIWMI._ADDPORT_OUT
title: _AddPort_OUT
author: windows-driver-content
description: The AddPort_OUT structure is used by a WMI provider to report the output parameter data of the AddPort WMI method to the WMI client.
old-location: storage\addport_out.htm
old-project: storage
ms.assetid: 1946245d-d661-41c9-8f5a-37534bf71890
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _AddPort_OUT, *PAddPort_OUT, AddPort_OUT
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
req.alt-api: AddPort_OUT
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

# _AddPort_OUT structure



## -description
The AddPort_OUT structure is used by a WMI provider to report the output parameter data of the <a href="storage.addport">AddPort</a> WMI method to the WMI client.


## -syntax

````
typedef struct _AddPort_OUT {
  ULONG HBAStatus;
} AddPort_OUT, *PAddPort_OUT;
````


## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.

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
<a href="storage.addport">AddPort</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddPort_OUT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
