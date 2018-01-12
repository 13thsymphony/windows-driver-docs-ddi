---
UID: NS:iscsiop._GetPresharedKeyForId_OUT
title: _GetPresharedKeyForId_OUT
author: windows-driver-content
description: The GetPresharedKeyForId_OUT structure holds the output data for the GetPresharedKeyForId method.
old-location: storage\getpresharedkeyforid_out.htm
old-project: storage
ms.assetid: 21d6378e-b93b-4e97-842a-a3157e081f31
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _GetPresharedKeyForId_OUT, *PGetPresharedKeyForId_OUT, GetPresharedKeyForId_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetPresharedKeyForId_OUT
req.alt-loc: iscsiop.h
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
req.typenames: *PGetPresharedKeyForId_OUT, GetPresharedKeyForId_OUT
---

# _GetPresharedKeyForId_OUT structure



## -description
The GetPresharedKeyForId_OUT structure holds the output data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554970">GetPresharedKeyForId</a> method.



## -syntax

````
typedef struct _GetPresharedKeyForId_OUT {
  ULONG     Status;
  ULONGLONG SecurityFlags;
} GetPresharedKeyForId_OUT, *PGetPresharedKeyForId_OUT;
````


## -struct-fields

### -field Status

On output from <b>GetPresharedKeyForId</b>, the status of the <b>GetPresharedKeyForId</b> operation. For a list of status qualifiers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>.  


### -field SecurityFlags

A bitwise OR of flags that indicate the security requirements of a target.  For a list of possible values for this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>.


## -remarks
You must initiate this method if the initiator supports IKE.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iscsiop.h (include Iscsiop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554970">GetPresharedKeyForId</a>
</dt>
<dt>
<a href="..\iscsiop\ns-iscsiop-_getpresharedkeyforid_in.md">GetPresharedKeyForId_IN</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561568">ISCSI_STATUS_QUALIFIERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563135">MSiSCSI_SecurityConfigOperations WMI Class</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565399">SECURITY_FLAG_QUALIFIERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GetPresharedKeyForId_OUT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

