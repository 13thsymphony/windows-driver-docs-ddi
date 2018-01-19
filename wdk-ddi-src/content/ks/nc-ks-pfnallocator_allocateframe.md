---
UID : NC:ks.PFNALLOCATOR_ALLOCATEFRAME
title : PFNALLOCATOR_ALLOCATEFRAME
author : windows-driver-content
description : The KStrAllocateFrame routine describes a vendor-supplied frame allocation function.
old-location : stream\kstrallocateframe.htm
old-project : stream
ms.assetid : 1b6eec23-82b4-4e8f-89d0-e76d6449906e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : NpdBrokerUninitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KStrAllocateFrame
req.alt-loc : ks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : KEYWORDSELECTOR
---


# PFNALLOCATOR_ALLOCATEFRAME callback function
The <i>KStrAllocateFrame</i> routine describes a vendor-supplied frame allocation function.

## Syntax

```
PFNALLOCATOR_ALLOCATEFRAME PfnallocatorAllocateframe;

NTSTATUS PfnallocatorAllocateframe(
  PFILE_OBJECT FileObject,
  PVOID *Frame
)
{...}
```

## Parameters

`FileObject`

Pointer to a <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure for which to allocate frames.

`*Frame`




## Return Value

Returns STATUS_SUCCESS if the request is handled.  Otherwise returns an appropriate error code.

## Remarks

This type is used in the <b>AllocateFrame</b> member of the <a href="..\ks\ns-ks-ksstreamallocator_functiontable.md">KSSTREAMALLOCATOR_FUNCTIONTABLE</a> structure.

You can pass an instance of this structure as part of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a> property request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\ns-ks-ksstreamallocator_functiontable.md">KSSTREAMALLOCATOR_FUNCTIONTABLE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565633">KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KStrAllocateFrame routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>