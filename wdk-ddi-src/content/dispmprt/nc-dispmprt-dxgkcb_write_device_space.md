---
UID : NC:dispmprt.DXGKCB_WRITE_DEVICE_SPACE
title : DXGKCB_WRITE_DEVICE_SPACE
author : windows-driver-content
description : The DxgkCbWriteDeviceSpace function writes to a device configuration space or the expansion ROM of a display adapter.
old-location : display\dxgkcbwritedevicespace.htm
old-project : display
ms.assetid : 797d6b0c-91a4-4923-ad40-937cfde50067
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.dxgkcbwritedevicespace, DxgkCbWriteDeviceSpace callback function [Display Devices], DxgkCbWriteDeviceSpace, DXGKCB_WRITE_DEVICE_SPACE, DXGKCB_WRITE_DEVICE_SPACE, dispmprt/DxgkCbWriteDeviceSpace, DpFunctions_947b42ba-4121-4f21-b361-29a63278feb0.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : dispmprt.h
req.include-header : Dispmprt.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---


# DXGKCB_WRITE_DEVICE_SPACE callback function
The <b>DxgkCbWriteDeviceSpace</b> function writes to a device configuration space or the expansion ROM of a display adapter.

## Syntax

```
DXGKCB_WRITE_DEVICE_SPACE DxgkcbWriteDeviceSpace;

NTSTATUS DxgkcbWriteDeviceSpace(
  HANDLE DeviceHandle,
  ULONG DataType,
  PVOID Buffer,
  ULONG Offset,
  ULONG Length,
  PULONG BytesWritten
)
{...}
```

## Parameters

`DeviceHandle`

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>.

`DataType`

The type of write transaction to be performed. This parameter must be one of the following values, which are defined in <i>Dispmprt.h</i>:

`Buffer`

A pointer to a buffer that supplies the data to be written to the configuration space.

`Offset`

The offset, in bytes, into the configuration space, at which the write transaction begins.

`Length`

The number of bytes to be written.

`BytesWritten`

A pointer to a ULONG-typed variable that receives the number of bytes actually written.


## Return Value

<b>DxgkCbWriteDeviceSpace</b> returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>  STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
  The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>  STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
  The <i>DeviceHandle</i>, <i>DataType</i>, or <i>Buffer</i> parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>  STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
  The function was unable to write the data.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dispmprt.h (include Dispmprt.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkcb_read_device_space.md">DxgkCbReadDeviceSpace</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_WRITE_DEVICE_SPACE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>