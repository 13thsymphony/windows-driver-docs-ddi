---
UID: NF:ndis.NdisReadRegisterUshort
title: NdisReadRegisterUshort macro
author: windows-driver-content
description: NdisReadRegisterUshort is called by the miniport driver to read a USHORT from a memory-mapped device register.
old-location: netvista\ndisreadregisterushort.htm
old-project: netvista
ms.assetid: 0048fb18-8728-4b41-b4e2-5762966d5ed0
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisReadRegisterUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisReadRegisterUshort
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisReadRegisterUshort macro



## -description
<b>NdisReadRegisterUshort</b> is called by the miniport driver to read a USHORT from a memory-mapped device
  register.



## -syntax

````
VOID NdisReadRegisterUshort(
  [in]  PUSHORT Register,
  [out] PUSHORT Data
);
````


## -parameters

### -param Register [in]

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.


### -param Data [out]

Pointer to the caller-supplied variable in which this function returns the USHORT read from 
     <i>Register</i> .


## -remarks
If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/e37a6ac8-6a51-4ff3-b09a-d90625025e61">NdisReadRegisterUshort (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisReadRegisterUshort (NDIS
   5.1)</b>) in Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadregisteruchar.md">NdisReadRegisterUchar</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisreadregisterulong.md">NdisReadRegisterUlong</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiswriteregisterushort.md">NdisWriteRegisterUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReadRegisterUshort macro%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

