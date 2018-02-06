---
UID: NC:wlanihv.DOT11EXTIHV_INIT_ADAPTER
title: DOT11EXTIHV_INIT_ADAPTER
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvinitadapter.htm
old-project: netvista
ms.assetid: 96dc1718-ee35-440a-94e8-eba4a41c9559
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvinitadapter, Dot11ExtIhvInitAdapter callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvInitAdapter, DOT11EXTIHV_INIT_ADAPTER, DOT11EXTIHV_INIT_ADAPTER, wlanihv/Dot11ExtIhvInitAdapter, Native_802.11_IHV_Ext_c2fbb863-6b05-4444-90f1-37f375db9b9e.xml
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
-	Dot11ExtIhvInitAdapter
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---


# DOT11EXTIHV_INIT_ADAPTER callback function
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvInitAdapter</i> function to have the IHV Extensions DLL allocate and initialize an adapter
  context.

## Syntax

```
DOT11EXTIHV_INIT_ADAPTER Dot11extihvInitAdapter;

DWORD Dot11extihvInitAdapter(
  PDOT11_ADAPTER pDot11Adapter,
  HANDLE hDot11SvcHandle,
  PHANDLE phIhvExtAdapter
)
{...}
```

## Parameters

`pDot11Adapter`

A pointer to a 
     <a href="..\wlclient\ns-wlclient-_dot11_adapter.md">DOT11_ADAPTER</a> structure, which identifies the
     adapter to be initialized.

`hDot11SvcHandle`

A handle assigned by the operating system for the adapter. The IHV Extensions DLL must use this
     handle value when calling any IHV Extensibility function that declares an 
     <i>hDot11SvcHandle</i> parameter, such as 
     <a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
     Dot11ExtPreAssociateCompletion</a>.

`phIhvExtAdapter`

A pointer to a handle variable. The IHV Extensions DLL must assign a unique handle value for the
     adapter and set *
     <i>phIhvExtAdapter</i> to the handle value. The operating system uses this handle value when it calls any
     IHV Handler function that declares an 
     <i>hIhvExtAdapter</i> parameter, such as 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a>. 
     

Typically, the IHV Extensions DLL allocates a state array for the adapter context and returns the
     address of the array as the handle value.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

The operating system calls the 
    <i>Dot11ExtIhvInitAdapter</i> function whenever a WLAN adapter becomes available and enabled for use, such
    as when a PCMCIA adapter is inserted.

For more information about WLAN adapter initialization, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff557044">802.11 WLAN Adapter Arrival</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Target Platform** | Desktop |
| **Header** | wlanihv.h (include Wlanihv.h) |

## See Also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
   Dot11ExtPreAssociateCompletion</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-extensibility-functions">Native 802.11 IHV
   Extensibility Functions</a>

<a href="..\wlclient\ns-wlclient-_dot11_adapter.md">DOT11_ADAPTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_INIT_ADAPTER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>