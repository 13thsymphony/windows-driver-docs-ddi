---
UID: NC:wlanihv.DOT11EXTIHV_QUERY_UI_REQUEST
title: DOT11EXTIHV_QUERY_UI_REQUEST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvqueryuirequest.htm
old-project: netvista
ms.assetid: 37c01180-0742-4764-88c3-9ceb807a0086
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvqueryuirequest, Dot11ExtIhvQueryUIRequest callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvQueryUIRequest, DOT11EXTIHV_QUERY_UI_REQUEST, DOT11EXTIHV_QUERY_UI_REQUEST, wlanihv/Dot11ExtIhvQueryUIRequest, Native_802.11_IHV_Ext_b820a678-9e05-4f96-87bd-ed1154317091.xml
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
-	Dot11ExtIhvQueryUIRequest
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---


# DOT11EXTIHV_QUERY_UI_REQUEST callback function
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvQueryUIRequest</i> function whenever the connection status changes. When this function is
  called, the IHV Extensions DLL returns a 
  <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure that
  the operating system can use for a UI request.

## Syntax

```
DOT11EXTIHV_QUERY_UI_REQUEST Dot11extihvQueryUiRequest;

DWORD Dot11extihvQueryUiRequest(
  HANDLE hIhvExtAdapter,
  DOT11EXT_IHV_CONNECTION_PHASE connectionPhase,
  PDOT11EXT_IHV_UI_REQUEST *ppIhvUIRequest
)
{...}
```

## Parameters

`hIhvExtAdapter`

The handle used by the IHV Extensions DLL to reference the wireless LAN (WLAN) adapter. This
     handle value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

`connectionPhase`

The current connection phase. The data type for this member is the 
     <b>DOT11EXT_IHV_CONNECTION_PHASE</b> enumeration:
     




#### connection_phase_any

Specifies any connection phase.


#### connection_phase_initial_connection

Specifies the connection phase before the IHV Extensions DLL initiates a pre-association
       operation. For more information about the pre-association operation, see 
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/pre-association-operation-overview">Pre-Association
       Operations</a>.


#### connection_phase_post_l3_connection

Specifies the connection phase after the IHV Extensions DLL completes a post-association
       operation. For more information about the post-association operation, see 
       <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/post-association-operations">Post-Association
       Operations</a>.

`*ppIhvUIRequest`

The address of a pointer to a 
     <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure.
     The IHV Extensions DLL must allocate a buffer for the DOT11EXT_IHV_UI_REQUEST structure by calling 
     <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

When 
    <i>Dot11ExtIhvQueryUIRequest</i> is called, the IHV Extensions DLL must allocate and return a buffer
    formatted as a 
    <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure.
    In this situation, the DLL must follow these guidelines:
<ul>
<li>
The IHV Extensions DLL must call 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a> to
      allocate the buffer. After the DLL returns from 
      <i>Dot11ExtIhvQueryUIRequest</i>, the operating system is responsible for calling 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a> to free the
      buffer.

</li>
<li>
The IHV Extensions DLL formats the 
      <a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a> structure
      for a UI request appropriate for the change in connection status.

For example, if 
      <i>connectionPhase</i> is set to 
      <b>connection_phase_initial_connection</b>, the IHV Extensions DLL could set the members of the
      DOT11EXT_IHV_UI_REQUEST structure to reference a user interface page that notifies the user of the
      start of the connection operation.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Target Platform** | Desktop |
| **Header** | wlanihv.h (include Wlanihv.h) |

## See Also

<a href="..\wlanihv\ns-wlanihv-_dot11ext_ihv_ui_request.md">DOT11EXT_IHV_UI_REQUEST</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_free_buffer.md">Dot11ExtFreeBuffer</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_allocate_buffer.md">Dot11ExtAllocateBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_QUERY_UI_REQUEST callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>