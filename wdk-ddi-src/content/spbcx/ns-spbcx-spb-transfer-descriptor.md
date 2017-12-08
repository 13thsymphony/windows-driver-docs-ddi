---
UID: NS.spbcx.SPB_TRANSFER_DESCRIPTOR
title: SPB_TRANSFER_DESCRIPTOR
author: windows-driver-content
description: The SPB_TRANSFER_DESCRIPTOR structure describes a single transfer in an I/O transfer sequence.
old-location: spb\spb_transfer_descriptor.htm
old-project: SPB
ms.assetid: 3D370646-3879-4415-8D80-04D0B23839B0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SPB_TRANSFER_DESCRIPTOR,
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
req.alt-api: SPB_TRANSFER_DESCRIPTOR
req.alt-loc: Spbcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# SPB_TRANSFER_DESCRIPTOR structure



## -description
<p>The <b>SPB_TRANSFER_DESCRIPTOR</b> structure describes a single transfer in an <a href="https://msdn.microsoft.com/7415DB28-5E93-4F47-B169-7C652969D4C7">I/O transfer sequence</a>.</p>


## -syntax

````
typedef struct _SPB_TRANSFER_DESCRIPTOR {
  USHORT                 Size;
  SPB_TRANSFER_DIRECTION Direction;
  size_t                 TransferLength;
  ULONG                  DelayInUs;
} SPB_TRANSFER_DESCRIPTOR, *PSPB_TRANSFER_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>The size, in bytes, of the entire structure.  Used for versioning.</p>
</dd>

### -field Direction

<dd>
<p>The direction of the transfer.  This member is set to one of the following <a href="https://msdn.microsoft.com/library/windows/hardware/hh406220">SPB_TRANSFER_DIRECTION</a> enumeration values:</p>
<ul>
<li><b>SpbTransferDirectionFromDevice</b></li>
<li><b>SpbTransferDirectionToDevice</b></li>
</ul>
</dd>

### -field TransferLength

<dd>
<p>The number of bytes of data to be transferred.</p>
</dd>

### -field DelayInUs

<dd>
<p>An optional delay, in microseconds, before this transfer begins. For more information, see the following Remarks section.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a> method. Before passing an <b>SPB_TRANSFER_DESCRIPTOR</b> structure to this method, initialize the structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406219">SPB_TRANSFER_DESCRIPTOR_INIT</a> function.</p>

<p>The <b>DelayInUs</b> member specifies a delay before the start of the transfer. In certain cases, a peripheral driver might need to insert a delay between two consecutive transfers in a sequence. For example, if a write to a target device specifies the type of information that is being requested, this device might need time to process the request before the information can be read. In addition, a peripheral driver might need to specify a delay before the first transfer in a sequence. In this case, the controller must apply the address or assert the device-select  line to the target device for the specified delay interval before the start of the first transfer.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Spbcx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450924">SpbRequestGetTransferParameters</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406219">SPB_TRANSFER_DESCRIPTOR_INIT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406220">SPB_TRANSFER_DIRECTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_DESCRIPTOR structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
