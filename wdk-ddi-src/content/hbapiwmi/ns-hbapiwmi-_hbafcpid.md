---
UID: NS.HBAPIWMI._HBAFCPID
title: _HBAFCPID
author: windows-driver-content
description: The HBAFCPID structure contains information that uniquely identifies a logical unit on a fibre channel network.
old-location: storage\hbafcpid.htm
old-project: storage
ms.assetid: a4fa3093-a328-4d90-bc51-0e7a6db1ed58
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _HBAFCPID, HBAFCPID, *PHBAFCPID
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
req.alt-api: HBAFCPID
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

# _HBAFCPID structure



## -description
The HBAFCPID structure contains information that uniquely identifies a logical unit on a fibre channel network.



## -syntax

````
typedef struct _HBAFCPID {
  ULONG     Fcid;
  UCHAR     NodeWWN[8];
  UCHAR     PortWWN[8];
  ULONGLONG FcpLun;
} HBAFCPID, *PHBAFCPID;
````


## -struct-fields

### -field Fcid

Contains the identifier that indicates which port is to be queried for information about the logical unit. For a discussion of the values that this member have, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field NodeWWN

Contains the 64 bit world-wide name (WWN) of the node (machine) to which the logical unit is connected. If an HBA has multiple ports and is associated with more than one node, this member will contain a name chosen from among the names of the associated nodes. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field PortWWN

Contains the 64 bit world-wide name of the port to be queried for information about the logical unit. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.


### -field FcpLun

Contains a 64-bit fibre channel protocol (FCP) number for the logical unit. 


## -remarks
The WMI tool suite generates a declaration for this structure in <i>hbapiwm.h</i> after compiling the <a href="storage.hbafcpid_wmi_class">HBAFCPID WMI Class</a>.

For more information about the fibre channel protocol (FCP), see the T11 committee's <i>dpANS Fibre Channel Protocol for SCSI</i> and <i>Fibre Channel HBA API</i> specifications.


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
<a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a>
</dt>
<dt>
<a href="storage.hbafcpbindingentry">HBAFCPBindingEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBAFCPID structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

