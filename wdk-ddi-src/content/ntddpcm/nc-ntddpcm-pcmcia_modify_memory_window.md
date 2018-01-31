---
UID : NC:ntddpcm.PCMCIA_MODIFY_MEMORY_WINDOW
title : PCMCIA_MODIFY_MEMORY_WINDOW
author : windows-driver-content
description : The PCMCIA_MODIFY_MEMORY_WINDOW interface routine sets the attributes of a memory window for a PCMCIA memory card. The memory window is mapped by the PCMCIA bus driver.
old-location : pcmcia\pcmcia_modify_memory_window.htm
old-project : PCMCIA
ms.assetid : 01469cd7-a023-42b0-9306-fc390bf990e6
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : PCMCIA.pcmcia_modify_memory_window, ModifyMemoryWindow callback function [Buses], ModifyMemoryWindow, PCMCIA_MODIFY_MEMORY_WINDOW, PCMCIA_MODIFY_MEMORY_WINDOW, ntddpcm/ModifyMemoryWindow, memcdref_fdb376f2-4f80-4a35-ab23-f007bdc05cad.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ntddpcm.h
req.include-header : Ntddpcm.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.lib : 
req.dll : 
req.irql : "<=DISPATCH_LEVEL (See Remarks section.)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PAR_SET_INFORMATION, *PPAR_SET_INFORMATION
---


# PCMCIA_MODIFY_MEMORY_WINDOW function
The <b>PCMCIA_MODIFY_MEMORY_WINDOW</b> interface routine sets the attributes of a memory window for a PCMCIA memory card. The memory window is mapped by the PCMCIA bus driver.

## Syntax

```
PCMCIA_MODIFY_MEMORY_WINDOW PcmciaModifyMemoryWindow;

BOOLEAN PcmciaModifyMemoryWindow(
  PVOID Context,
  ULONGLONG HostBase,
  ULONGLONG CardBase,
  BOOLEAN Enable,
  ULONG WindowSize,
  UCHAR AccessSpeed,
  UCHAR BusWidth,
  BOOLEAN IsAttributeMemory
)
{...}
```

## Parameters

`Context`

Pointer to the context for the interface routine.

`HostBase`

Specifies the physical memory window to map. <i>HostBase</i> is the base address for the memory card in the system's physical address space.

`CardBase`

Specifies the byte offset in the PC Card's or CardBus card's memory where the memory mapping begins.

`Enable`

Specifies permission to access the memory window. If <i>Enable</i> is <b>TRUE</b>, memory access is permitted, otherwise memory access is not permitted.

`WindowSize`

Specifies the size, in bytes, of the memory window that is mapped. The value of <i>WindowSize</i> cannot exceed the memory window granted to the driver in its assigned resources. If the value of Enable is <b>TRUE</b> and the value of WindowSize is zero, the size of the memory window granted to the driver in its assigned resources is used. If <i>Enable</i> is <b>FALSE</b>, <i>WindowSize</i> is not used.

`AccessSpeed`

Specifies the access speed of the PC Card or CardBus card. The value of <i>AccessSpeed</i> is encoded as specified by the <i>PC Card Standard, Release 6.1</i>. If Enable is <b>FALSE</b>, <i>AccessSpeed</i> is not used.

`BusWidth`

Specifies the width of bus access to the PCMCIA memory card. <i>BusWidth</i> must be one of the following values:



If <i>Enable</i> is <b>FALSE</b>, <i>BusWidth</i> is not used.


#### PCMCIA_MEMORY_8BIT_ACCESS

`IsAttributeMemory`




## Return Value

The <b>PCMCIA_MODIFY_MEMORY_WINDOW</b> interface routine returns <b>TRUE</b> if the memory window is successfully enabled or disabled, as specified by the <i>Enable</i> parameter.

## Remarks

A caller must set the <i>Context</i> parameter to the context that is specified by the PCMCIA bus driver. The PCMCIA bus driver returns the context for the interface routines in the <b>Context</b> member of the same PCMCIA_INTERFACE_STANDARD structure that contains the pointers to the interface routines. If the <i>Context</i> parameter is not valid, system behavior is not defined, and the system might halt.

Callers of this routine must be running at IRQL &lt;= DISPATCH_LEVEL. To maintain overall system performance, it is recommended that drivers call this routine at IRQL &lt; DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddpcm.h (include Ntddpcm.h) |
| **Library** |  |
| **IRQL** | "<=DISPATCH_LEVEL (See Remarks section.)" |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537609">PCMCIA_IS_WRITE_PROTECTED</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537611">PCMCIA_SET_VPP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCMCIA\buses]:%20PCMCIA_MODIFY_MEMORY_WINDOW callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>