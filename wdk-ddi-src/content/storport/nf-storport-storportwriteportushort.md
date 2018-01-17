---
UID: NF:storport.StorPortWritePortUshort
title: StorPortWritePortUshort function
author: windows-driver-content
description: The StorPortWritePortUshort routine writes a value to a specified register address.
old-location: storage\storportwriteportushort.htm
old-project: storage
ms.assetid: 7655b6a1-2ed4-4e57-b8b5-e7b8ff2dd1e5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortWritePortUshort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortWritePortUshort
req.alt-loc: Storport.lib,Storport.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortWritePortUshort function



## -description
The <b>StorPortWritePortUshort</b> routine writes a value to a specified register address. 



## -syntax

````
STORPORT_API VOID StorPortWritePortUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Port,
  _In_ USHORT  Value
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension.


### -param Port [in]

Contains the address of the port to be written to. 


### -param Value [in]

Contains the value to be written. 


## -returns
None 


## -remarks
For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564841">ScsiPortWritePortUshort</a>. For a buffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportbufferushort.md">StorPortWritePortBufferUshort</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564841">ScsiPortWritePortUshort</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportwriteportbufferushort.md">StorPortWritePortBufferUshort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

