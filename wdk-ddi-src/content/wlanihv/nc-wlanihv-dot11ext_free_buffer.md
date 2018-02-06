---
UID: NC:wlanihv.DOT11EXT_FREE_BUFFER
title: DOT11EXT_FREE_BUFFER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extfreebuffer.htm
old-project: netvista
ms.assetid: a6e49914-29c0-47d2-936b-17c48958cb36
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extfreebuffer, Dot11ExtFreeBuffer callback function [Network Drivers Starting with Windows Vista], Dot11ExtFreeBuffer, DOT11EXT_FREE_BUFFER, DOT11EXT_FREE_BUFFER, wlanihv/Dot11ExtFreeBuffer, Native_802.11_IHV_Ext_af721540-28a8-43c2-a649-ce0f6fb9adce.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wlanihv.h
req.include-header: Wlanihv.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wlanihv.h
apiname:
-	Dot11ExtFreeBuffer
product: Windows
targetos: Windows
req.typenames: "*PDRIVER_INFO_8W, DRIVER_INFO_8W, *LPDRIVER_INFO_8W"
req.product: Windows 10 or later.
---


# DOT11EXT_FREE_BUFFER callback function
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtFreeBuffer</b> function to free memory allocated through a call to 
  <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>.

## Syntax

```
DOT11EXT_FREE_BUFFER Dot11extFreeBuffer;

void Dot11extFreeBuffer(
  LPVOID pvMemory
)
{...}
```

## Parameters

`pvMemory`

A pointer to the buffer to be freed. If the value of 
     <i>pvMemory</i> is <b>NULL</b>, the 
     <b>Dot11ExtFreeBuffer</b> function returns immediately.


## Return Value

None

## Remarks

The IHV Extension DLL must not call the 
    <b>Dot11ExtFreeBuffer</b> function for any variable-length buffer allocated
    within an IHV handler function and passed to the operating system through a parameter to the function. In
    this situation, the operating system is responsible for freeing the buffer after the return of the IHV
    Handler function.

For more information about the IHV Handler functions, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
    Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Target Platform** | Desktop |
| **Header** | wlanihv.h (include Wlanihv.h) |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_FREE_BUFFER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>