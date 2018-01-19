---
UID : NF:poscx.PosCxReleaseDevice
title : PosCxReleaseDevice function
author : windows-driver-content
description : PosCxReleaseDevice is called to release a device that was previously claimed with PosCxClaimDevice. Once the device is released, the next pending claim requester is promoted.
old-location : pos\poscxreleasedevice.htm
old-project : pos
ms.assetid : 9615915C-B729-4702-BF41-D5068B43A729
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PosCxReleaseDevice
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : poscx.h
req.include-header : Poscx.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PosCxReleaseDevice
req.alt-loc : poscx.h
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
req.typenames : POS_CX_EVENT_PRIORITY
req.product : Windows 10 or later.
---


# PosCxReleaseDevice function
PosCxReleaseDevice is called to release a device that was previously claimed with
      <a href="..\poscx\nf-poscx-poscxclaimdevice.md">PosCxClaimDevice</a>.
      Once the device is released, the next pending claim requester is promoted.

## Syntax

````
NTSTATUS PosCxReleaseDevice(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject
);
````

## Parameters

`device`

A handle to a framework device object that represents the device.

`fileObject`

A handle to a framework file object that identifies the caller.


## Return Value

Possible return values are:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | poscx.h (include Poscx.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\poscx\nf-poscx-poscxclaimdevice.md">PosCxClaimDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [pos\pos]:%20PosCxReleaseDevice function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>