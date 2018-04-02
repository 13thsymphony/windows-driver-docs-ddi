---
UID: NF:wdfrequest.WdfRequestGetEffectiveIoType
title: WdfRequestGetEffectiveIoType function
author: windows-driver-content
description: The WdfRequestGetEffectiveIoType method returns the buffer access method that UMDF is using for the data buffers of the specified I/O request.
old-location: wdf\wdfrequestgeteffectiveiotype.htm
old-project: wdf
ms.assetid: ED63E47F-B91F-49DC-9CE9-8CFE8F670B16
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfRequestGetEffectiveIoType, WdfRequestGetEffectiveIoType method, wdf.wdfrequestgeteffectiveiotype, wdfrequest/WdfRequestGetEffectiveIoType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfRequestGetEffectiveIoType
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestGetEffectiveIoType function
<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfRequestGetEffectiveIoType</b> method returns the buffer access method that UMDF is using for the data buffers of the specified I/O request.

## Syntax

```
WDF_DEVICE_IO_TYPE WdfRequestGetEffectiveIoType(
  WDFREQUEST Request
);
```

## Parameters

`Request`

A handle to a framework request object.


## Return Value

<b>WdfRequestGetEffectiveIoType</b> returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551255">WDF_DEVICE_IO_TYPE</a>-typed value that identifies the buffer access method that UMDF is using for the I/O request's data buffers.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/BDB78BCD-1964-431B-BE99-CABA6DF44D7A">Managing Buffer Access Methods in UMDF Drivers</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/5a0fa3b4-d020-4664-afa4-352573d4f079">EvtIoWrite</a> callback function can determine the buffer access method for the specified write request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyDrvEvtIoWrite(
  _In_  WDFQUEUE Queue,
  _In_  WDFREQUEST Request,
  _In_  size_t Length
)
{ 

...

    WDF_DEVICE_IO_TYPE iotype = WdfDeviceIoUndefined;
    
    iotype = WdfRequestGetEffectiveIoType(Request);

...

}
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1  |
| **Target Platform** | Universal |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | WUDFx02000.lib |
| **DLL** | WUDFx02000.dll; TBD |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551255">WDF_DEVICE_IO_TYPE</a>