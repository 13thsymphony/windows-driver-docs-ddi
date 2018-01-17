---
UID: NF:storport.StorPortWritePortBufferUlong
title: StorPortWritePortBufferUlong function
author: windows-driver-content
description: The StorPortWritePortBufferUlong routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferulong.htm
old-project: storage
ms.assetid: 24735e9a-d259-48d1-8efe-8ff1642b6a35
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortWritePortBufferUlong
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
req.alt-api: StorPortWritePortBufferUlong
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

# StorPortWritePortBufferUlong function



## -description
The <b>StorPortWritePortBufferUlong</b> routine writes a value to a specified register address. 



## -syntax

````
STORPORT_API VOID StorPortWritePortBufferUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Port,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension.


### -param Port [in]

Contains the address of the port to be written to. 


### -param Buffer [in]

Pointer to the buffer containing the data to be written. 


### -param Count [in]

Contains the number of data items of size <b>sizeof</b>(ULONG) to be written. 


## -returns
None 


## -remarks
For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564824">ScsiPortWritePortBufferUlong</a>. For a nonbuffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportulong.md">StorPortWritePortUlong</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564824">ScsiPortWritePortBufferUlong</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportwriteportulong.md">StorPortWritePortUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortBufferUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

