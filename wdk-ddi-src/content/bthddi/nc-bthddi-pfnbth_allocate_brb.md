---
UID : NC:bthddi.PFNBTH_ALLOCATE_BRB
title : PFNBTH_ALLOCATE_BRB
author : windows-driver-content
description : The BthAllocateBrb function allocates a Bluetooth request block (BRB) of the specified type.
old-location : bltooth\bthallocatebrb.htm
old-project : bltooth
ms.assetid : e1ac9d4c-75e2-4d37-86d7-3c3f1486222e
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : IBidiSpl2, IBidiSpl2::UnbindDevice, UnbindDevice
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Desktop
req.target-min-winverclnt : Versions: Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BthAllocateBrb
req.alt-loc : bthddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
req.typenames : MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---


# PFNBTH_ALLOCATE_BRB callback function
The 
  <i>BthAllocateBrb</i> function allocates a Bluetooth request block (BRB) of the specified type.

## Syntax

```
PFNBTH_ALLOCATE_BRB PfnbthAllocateBrb;

PBRB PfnbthAllocateBrb(
  BRB_TYPE brbType,
  ULONG tag
)
{...}
```

## Parameters

`brbType`

Specifies a value from the 
     <a href="..\bthddi\ne-bthddi-_brb_type.md">BRB_TYPE</a> enumeration to initialize the BRB
     with.

`tag`

Specifies a 4-byte 
     pool tag that uniquely identifies the driver that does the memory
     allocation. For more information about pool tags, see 
     <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>.


## Return Value

<i>BthAllocateBrb</i> returns a pointer to the newly allocated BRB, or <b>NULL</b> if the system is out of
     memory.

## Remarks

Profile drivers obtain a pointer to the 
    <i>BthAllocateBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="https://msdn.microsoft.com/56db29cd-26ab-4262-9b9f-40d46372ffe9">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\bthddi\ne-bthddi-_brb_type.md">BRB_TYPE</a>
</dt>
<dt>pool tag</dt>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PFNBTH_ALLOCATE_BRB callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>