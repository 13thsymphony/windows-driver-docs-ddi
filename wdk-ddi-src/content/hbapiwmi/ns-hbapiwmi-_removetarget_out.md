---
UID: NS.HBAPIWMI._REMOVETARGET_OUT
title: _RemoveTarget_OUT
author: windows-driver-content
description: The RemoveTarget_OUT structure is used by an HBA miniport driver to report the output parameter data of the RemoveTarget WMI method to the WMI client.
old-location: storage\removetarget_out.htm
old-project: storage
ms.assetid: 176dbb0c-227e-48b2-956c-9e2b42f4c68b
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _RemoveTarget_OUT, *PRemoveTarget_OUT, RemoveTarget_OUT
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
req.alt-api: RemoveTarget_OUT
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

# _RemoveTarget_OUT structure



## -description
The RemoveTarget_OUT structure is used by an HBA miniport driver to report the output parameter data of the <a href="storage.removetarget">RemoveTarget</a> WMI method to the WMI client.


## -syntax

````
typedef struct _RemoveTarget_OUT {
  ULONG HBAStatus;
} RemoveTarget_OUT, *PRemoveTarget_OUT;
````


## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>.

## -remarks
The WMI tool suite generates a declaration of the RemoveTarget_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_eventcontrol_wmi_class">MSFC_EventControl WMI Class</a>.

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
<a href="storage.removetarget">RemoveTarget</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemoveTarget_OUT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
