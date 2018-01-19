---
UID : NF:usbcamdi.USBCAMD_ControlVendorCommand
title : USBCAMD_ControlVendorCommand function
author : windows-driver-content
description : The USBCAMD_ControlVendorCommand function sends vendor-specific commands to the control pipe.
old-location : stream\usbcamd_controlvendorcommand.htm
old-project : stream
ms.assetid : 3bd11885-2c33-4d4d-b9e8-8eff79eb9c61
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : USBCAMD_ControlVendorCommand
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : usbcamdi.h
req.include-header : Usbcamdi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBCAMD_ControlVendorCommand
req.alt-loc : usbcamd2.lib,usbcamd2.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Usbcamd2.lib
req.dll : 
req.irql : >= PASSIVE_LEVEL (See Remarks section)
req.typenames : USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product : Windows 10 or later.
---


# USBCAMD_ControlVendorCommand function
The <b>USBCAMD_ControlVendorCommand</b> function sends vendor-specific commands to the control pipe.

## Syntax

````
NTSTATUS USBCAMD_ControlVendorCommand(
  _In_        PVOID                      DeviceContext,
  _In_        UCHAR                      Request,
  _In_        USHORT                     Value,
  _In_        USHORT                     Index,
  _Inout_opt_ PVOID                      Buffer,
  _Inout_     PULONG                     BufferLength,
  _In_        BOOLEAN                    GetData,
  _In_opt_    PCOMMAND_COMPLETE_FUNCTION CommandComplete,
  _In_opt_    PVOID                      CommandContext
);
````

## Parameters

`DeviceContext`

Pointer to device-specific context.

`Request`

Specifies the value of the <b>Request</b> field for the vendor command.

`Value`

Specifies the value of the <b>Value</b> field for the vendor command.

`Index`

Specifies the value of the <b>Index</b> field for the vendor command.

`Buffer`

Pointer to a data buffer if the command has data. If the command does not have any data, this value is <b>NULL</b>.

`BufferLength`

Pointer to the buffer length value. Buffer length is expressed in bytes. If the value of <i>Buffer</i> is <b>NULL</b>, <i>BufferLength</i> may also be <b>NULL</b>.

`GetData`

<i>GetData</i> indicates data was sent from the device to the host.

`CommandComplete`

Pointer to a camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>, which is called when the bulk read or write is completed. This value can be <b>NULL</b>.

`CommandContext`

Pointer to a block of memory, that is passed as an argument to the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>.


## Return Value

<b>USBCAMD_ControlVendorCommand </b>returns the NTSTATUS code from vendor command. Other possible error codes include:
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The vendor command is deferred.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There are insufficient resources to allocate the vendor command.

## Remarks

This function may be called at IRQL &gt;= PASSIVE_LEVEL. If the function is called at IRQL &gt; PASSIVE_LEVEL, the command is deferred. After completion, the camera minidriver defined <a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a> is called and passed the value in the <i>CommandContext</i> argument<i>.</i>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **Library** |  |
| **IRQL** | >= PASSIVE_LEVEL (See Remarks section) |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcommand_complete_function.md">CommandCompleteFunction</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_ControlVendorCommand function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>