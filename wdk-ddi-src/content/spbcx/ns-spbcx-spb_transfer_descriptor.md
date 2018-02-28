---
UID: NS:spbcx.SPB_TRANSFER_DESCRIPTOR
title: SPB_TRANSFER_DESCRIPTOR
author: windows-driver-content
description: The SPB_TRANSFER_DESCRIPTOR structure describes a single transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_descriptor.htm
old-project: SPB
ms.assetid: 3D370646-3879-4415-8D80-04D0B23839B0
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSPB_TRANSFER_DESCRIPTOR, PSPB_TRANSFER_DESCRIPTOR, PSPB_TRANSFER_DESCRIPTOR structure pointer [Buses], SPB.spb_transfer_descriptor, SPB_TRANSFER_DESCRIPTOR, SPB_TRANSFER_DESCRIPTOR structure [Buses], spbcx/PSPB_TRANSFER_DESCRIPTOR, spbcx/SPB_TRANSFER_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: spbcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any IRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Spbcx.h
api_name:
-	SPB_TRANSFER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: SPB_TRANSFER_DESCRIPTOR, *PSPB_TRANSFER_DESCRIPTOR
req.product: Windows 10 or later.
---

# SPB_TRANSFER_DESCRIPTOR structure
The <b>SPB_TRANSFER_DESCRIPTOR</b> structure describes a single transfer in an <a href="https://msdn.microsoft.com/7415DB28-5E93-4F47-B169-7C652969D4C7">I/O transfer sequence</a>.

## Syntax
````
typedef struct _SPB_TRANSFER_DESCRIPTOR {
  USHORT                 Size;
  SPB_TRANSFER_DIRECTION Direction;
  size_t                 TransferLength;
  ULONG                  DelayInUs;
} SPB_TRANSFER_DESCRIPTOR, *PSPB_TRANSFER_DESCRIPTOR;
````

## Members


`DelayInUs`

An optional delay, in microseconds, before this transfer begins. For more information, see the following Remarks section.

`Direction`

The direction of the transfer.  This member is set to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/hh406220">SPB_TRANSFER_DIRECTION</a> enumeration values:

<ul>
<li><b>SpbTransferDirectionFromDevice</b></li>
<li><b>SpbTransferDirectionToDevice</b></li>
</ul>

`Size`

The size, in bytes, of the entire structure.  Used for versioning.

`TransferLength`

The number of bytes of data to be transferred.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a> method. Before passing an <b>SPB_TRANSFER_DESCRIPTOR</b> structure to this method, initialize the structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406219">SPB_TRANSFER_DESCRIPTOR_INIT</a> function.

The <b>DelayInUs</b> member specifies a delay before the start of the transfer. In certain cases, a peripheral driver might need to insert a delay between two consecutive transfers in a sequence. For example, if a write to a target device specifies the type of information that is being requested, this device might need time to process the request before the information can be read. In addition, a peripheral driver might need to specify a delay before the first transfer in a sequence. In this case, the controller must apply the address or assert the device-select  line to the target device for the specified delay interval before the start of the first transfer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | spbcx.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406219">SPB_TRANSFER_DESCRIPTOR_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406220">SPB_TRANSFER_DIRECTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_DESCRIPTOR structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>