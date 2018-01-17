---
UID: NF:ndis.NdisRawWritePortUlong
title: NdisRawWritePortUlong macro
author: windows-driver-content
description: NdisRawWritePortUlong writes a ULONG value to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportulong.htm
old-project: netvista
ms.assetid: 24abe892-7d49-4bc4-8862-e375f9862a5f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisRawWritePortUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisRawWritePortUlong
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
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisRawWritePortUlong macro



## -description
<b>NdisRawWritePortUlong</b> writes a ULONG value to an I/O port on the NIC.



## -syntax

````
VOID NdisRawWritePortUlong(
  [in] ULONG_PTR Port,
  [in] ULONG     Data
);
````


## -parameters

### -param Port [in]

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.


### -param Data [in]

Specifies the ULONG to be written.


## -remarks
<b>NdisRawWritePortUlong</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.


## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawreadportulong.md">NdisRawReadPortUlong</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportbufferulong.md">NdisRawWritePortBufferUlong</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportuchar.md">NdisRawWritePortUchar</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisrawwriteportushort.md">NdisRawWritePortUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawWritePortUlong macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

