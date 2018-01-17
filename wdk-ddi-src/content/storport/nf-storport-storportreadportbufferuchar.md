---
UID: NF:storport.StorPortReadPortBufferUchar
title: StorPortReadPortBufferUchar function
author: windows-driver-content
description: The StorPortReadPortBufferUchar routine reads a value from a specified port address
old-location: storage\storportreadportbufferuchar.htm
old-project: storage
ms.assetid: 8602efbf-8e90-43d3-992f-4d2ecbcc7043
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: StorPortReadPortBufferUchar
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
req.alt-api: StorPortReadPortBufferUchar
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

# StorPortReadPortBufferUchar function



## -description
The <b>StorPortReadPortBufferUchar</b> routine reads a value from a specified port address 



## -syntax

````
STORPORT_API VOID StorPortReadPortBufferUchar(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR Port,
  _In_ PUCHAR Buffer,
  _In_ ULONG  Count
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the hardware device extension.


### -param Port [in]

Pointer to the address from which to read. 


### -param Buffer [in]

Pointer to the buffer that receives the data that is read.


### -param Count [in]

Number of unsigned characters to be read. 


## -returns
None  


## -remarks
For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564715">ScsiPortReadPortBufferUchar</a> routine. For a nonbuffered version of this routine, see <a href="..\storport\nf-storport-storportreadportuchar.md">StorPortReadPortUchar</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564715">ScsiPortReadPortBufferUchar</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportreadportuchar.md">StorPortReadPortUchar</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadPortBufferUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

