---
UID : NC:storport.HW_TRACING_ENABLED
title : HW_TRACING_ENABLED
author : windows-driver-content
description : The HwStorTracingEnabled callback routine enables the Storport to notify a miniport that event tracing is enabled.
old-location : storage\hwstortracingenabled.htm
old-project : storage
ms.assetid : 2B56A2D3-1FA6-4212-A83C-3C20D826353B
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 8 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HwStorTracingEnabled
req.alt-loc : Storport.h
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
req.typenames : "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product : Windows 10 or later.
---


# HW_TRACING_ENABLED callback function
The <b>HwStorTracingEnabled</b> callback routine enables the Storport to notify a miniport that event tracing is enabled.

## Syntax

```
HW_TRACING_ENABLED HwTracingEnabled;

void HwTracingEnabled(
  PVOID HwDeviceExtension,
  BOOLEAN Enabled
)
{...}
```

## Parameters

`HwDeviceExtension`



`Enabled`

True to enable tracing in the miniport. Otherwise, false.


## Return Value

None.

## Remarks

The name <i>HwStorTracingEnabled</i> is placeholder text for the actual routine name. The actual prototype of this routine is defined in <i>Storport.h</i> as follows:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_TRACING_ENABLED routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>