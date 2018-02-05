---
UID : NF:ndis.NdisReadRegisterUchar
title : NdisReadRegisterUchar macro
author : windows-driver-content
description : NdisReadRegisterUchar is called by the miniport driver to read a UCHAR from a memory-mapped device register.
old-location : netvista\ndisreadregisteruchar.htm
old-project : netvista
ms.assetid : 1723672b-aff7-49ca-a027-14a6eb3c2196
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisReadRegisterUchar, miniport_register_ref_04023727-eaf7-45fb-b70d-5a67eda4a54d.xml, ndis/NdisReadRegisterUchar, netvista.ndisreadregisteruchar, NdisReadRegisterUchar macro [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ndis.h
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisReadRegisterUchar function
<b>NdisReadRegisterUchar</b> is called by the miniport driver to read a UCHAR from a memory-mapped device
  register.

## Syntax

````
VOID NdisReadRegisterUchar(
  [in]  PUCHAR Register,
  [out] PUCHAR Data
);
````

## Parameters

`Register`

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.

`Data`

Pointer to the caller-supplied variable in which this function returns the UCHAR read from 
     <i>Register</i> .


## Return Value

None

## Remarks

If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUchar (NDIS   5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndisreadregisterulong.md">NdisReadRegisterUlong</a>

<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>

<a href="..\ndis\nf-ndis-ndiswriteregisteruchar.md">NdisWriteRegisterUchar</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisreadregisterushort.md">NdisReadRegisterUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReadRegisterUchar macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>