---
UID : NC:hdaudio.PHDAUDIO_BDL_ISR
title : PHDAUDIO_BDL_ISR
author : windows-driver-content
description : The HDAudioBdlIsr routine is the ISR that the HD Audio bus driver calls each time an IOC interrupt occurs on the stream. It is a function pointer of type PHDAUDIO_BDL_ISR, which is defined as
old-location : audio\phdaudio_bdl_isr.htm
old-project : audio
ms.assetid : 9DC36C2E-6609-46C8-870E-44845020A4B2
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _SM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : hdaudio.h
req.include-header : Hdaudio.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HDAudioBdlIsr
req.alt-loc : hdaudio.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DIRQL
req.typenames : SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
---


# PHDAUDIO_BDL_ISR callback function
The HDAudioBdlIsr routine is the ISR that the HD Audio bus driver calls each time an IOC interrupt occurs on the stream. It is a function pointer of type PHDAUDIO_BDL_ISR, which is defined as:

## Syntax

```
PHDAUDIO_BDL_ISR PhdaudioBdlIsr;

void PhdaudioBdlIsr(
  VOID *Context,
  ULONG InterruptBitMask
)
{...}
```

## Parameters

`*Context`



`InterruptBitMask`

The interruptBitMask parameter contains the bits from the HD Audio controller device's stream status register that indicate the reason for the interrupt. The following table shows the meaning of the individual bits in interruptBitMask.

<table>
<tr>
<th>Bit Numbers</th>
<th>Meaning</th>
</tr>
<tr>
<td>
31:5

</td>
<td>

        Unused.
       

</td>
</tr>
<tr>
<td>
4

</td>
<td>

        Descriptor Error (DESE). If an error occurs during the fetch of a buffer descriptor, then the HD Audio controller sets the DESE bit to 1.

</td>
</tr>
<tr>
<td>
3

</td>
<td>

        FIFO Error (FIFOE). If a FIFO error occurs (an overrun on an output stream or an underrun on an input stream), then the HD Audio controller sets the FIFOE bit to 1.

</td>
</tr>
<tr>
<td>
2

</td>
<td>

        Buffer Completion Interrupt Status (BCIS). If the IOC bit is set to 1 in the command byte of the buffer descriptor, then the HD Audio controller sets the BCIS bit to 1 after the last sample of a buffer is processed.

</td>
</tr>
<tr>
<td>
1:0

</td>
<td>

        Unused.
       

</td>
</tr>
</table>
 

The HD Audio bus driver sets the unused bits to zero. Instead of assuming that an IOC interrupt has occurred, the ISR must always check the interruptBitMask parameter to determine whether a stream error has occurred. For more information about the interrupt status bits shown in the preceding table, see the description of the stream status registers in the Intel High Definition Audio Specification.



The FIFO size is the maximum number of bytes that the DMA engine can hold in its internal buffer at any one time .


Depending on the hardware implementation, a DMA engine's FIFO size can either be static or vary dynamically with changes in the stream format. For more information about the FIFO size, see the Intel High Definition Audio Specification.


## Return Value

None

## Remarks

The caller must allocate the buffer memory and BDL from the nonpaged pool.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hdaudio.h (include Hdaudio.h) |
| **Library** |  |
| **IRQL** | DIRQL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-psetup_dma_engine_with_bdl.md">PSETUP_DMA_ENGINE_WITH_BDL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PHDAUDIO_BDL_ISR callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>