---
UID: NS.HBAPIWMI._GETBINDINGSUPPORT_OUT
title: _GetBindingSupport_OUT
author: windows-driver-content
description: The GetBindingSupport_OUT structure is used by a WMI provider to report the output parameter data of the GetBindingSupport WMI method to the WMI client.
old-location: storage\getbindingsupport_out.htm
old-project: storage
ms.assetid: cd67b301-a94a-41dd-9c06-e6c674ea9173
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _GetBindingSupport_OUT, GetBindingSupport_OUT, *PGetBindingSupport_OUT, PGetBindingSupport_OUT
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
req.alt-api: GetBindingSupport_OUT
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

# _GetBindingSupport_OUT structure



## -description
The GetBindingSupport_OUT structure is used by a WMI provider to report the output parameter data of the <a href="storage.getbindingsupport">GetBindingSupport</a> WMI method to the WMI client. 



## -syntax

````
typedef struct _GetBindingSupport_OUT {
  ULONG HBAStatus;
  ULONG BindType;
} GetBindingSupport_OUT, *PGetBindingSupport_OUT;
````


## -struct-fields

### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="storage.hba_status">HBA_STATUS</a>. 


### -field BindType

Contains a bitmap that indicates the ability of an HBA and its miniport driver to provide a specific set of features related to persistent binding. For a list of values that this parameter can have, see the description of the <a href="storage.hba_bind_type">HBA_BIND_TYPE</a> WMI class qualifier. 


## -remarks
The WMI tool suite generates a declaration of the GetBindingSupport_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbafcpinfo_wmi_class">MSFC_HBAFCPInfo WMI Class</a>.


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
<a href="storage.getbindingsupport">GetBindingSupport</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetBindingSupport_OUT structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
