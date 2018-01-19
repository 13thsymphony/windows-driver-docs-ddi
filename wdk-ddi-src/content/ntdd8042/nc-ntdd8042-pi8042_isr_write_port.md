---
UID : NC:ntdd8042.PI8042_ISR_WRITE_PORT
title : PI8042_ISR_WRITE_PORT
author : windows-driver-content
description : The PI8042_ISR_WRITE_PORT-typed callback routine writes data to an i8042 port. I8042prt provides this callback.
old-location : hid\pi8042_isr_write_port.htm
old-project : hid
ms.assetid : deded3fb-f0b3-4af5-b8b4-03658293b0fc
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _MSFC_VirtualFibrePortAttributes, *PMSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ntdd8042.h
req.include-header : Ntdd8042.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : I8042IsrWritePort
req.alt-loc : ntdd8042.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section.
req.typenames : "*PMSFC_VirtualFibrePortAttributes, MSFC_VirtualFibrePortAttributes"
---


# PI8042_ISR_WRITE_PORT callback function
The PI8042_ISR_WRITE_PORT-typed callback routine writes data to an i8042 port. I8042prt provides this callback.

## Syntax

```
PI8042_ISR_WRITE_PORT Pi8042IsrWritePort;

void Pi8042IsrWritePort(
  PVOID Context,
  UCHAR Value
)
{...}
```

## Parameters

`Context`

Pointer to the function device object that represents a keyboard or mouse device.

`Value`

Specifies the data to write to an i8042 port.


## Return Value

None

## Remarks

The PI8042_ISR_WRITE_PORT callback should only be called by a <a href="..\ntdd8042\nc-ntdd8042-pi8042_keyboard_isr.md">PI8042_KEYBOARD_ISR</a> callback or a <a href="..\ntdd8042\nc-ntdd8042-pi8042_mouse_isr.md">PI8042_MOUSE_ISR</a> callback. I8042prt calls a vendor-supplied ISR callback for a device in the corresponding I8042prt device ISR.

I8042prt specifies the keyboard write port callback in the <b>IsrWritePort</b> member of the <a href="..\ntdd8042\ns-ntdd8042-_internal_i8042_hook_keyboard.md">INTERNAL_I8042_HOOK_KEYBOARD</a> structure that I8042prt uses with an <a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_keyboard.md">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.

I8042prt specifies the mouse write port callback in the <b>IsrWritePort</b> member of the <a href="..\ntdd8042\ns-ntdd8042-_internal_i8042_hook_mouse.md">INTERNAL_I8042_HOOK_MOUSE</a> structure that I8042prt uses with an <a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_keyboard.md">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a> request.

The PI8042_ISR_WRITE_PORT callback runs in kernel mode at the same IRQL as the I8042prt ISR for the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntdd8042.h (include Ntdd8042.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_keyboard.md">IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</a>
</dt>
<dt>
<a href="..\ntdd8042\ns-ntdd8042-_internal_i8042_hook_mouse.md">INTERNAL_I8042_HOOK_MOUSE</a>
</dt>
<dt><b>IOCTL_INTERNAL_I8042_HOOK_KEYBOARD</b></dt>
<dt>
<a href="..\ntdd8042\ni-ntdd8042-ioctl_internal_i8042_hook_mouse.md">IOCTL_INTERNAL_I8042_HOOK_MOUSE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20PI8042_ISR_WRITE_PORT callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>