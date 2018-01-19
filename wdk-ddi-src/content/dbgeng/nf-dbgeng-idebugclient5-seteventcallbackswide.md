---
UID : NF:dbgeng.IDebugClient5.SetEventCallbacksWide
title : IDebugClient5::SetEventCallbacksWide method
author : windows-driver-content
description : The SetEventCallbacksWide method registers an event callbacks object with this client.
old-location : debugger\seteventcallbackswide.htm
old-project : debugger
ms.assetid : f5aecd1f-e0f2-47a9-aa70-767a42fefdff
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugClient5, IDebugClient5::SetEventCallbacksWide, SetEventCallbacksWide
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugClient5.SetEventCallbacksWide
req.alt-loc : dbgeng.h
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
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetEventCallbacksWide method
The <b>SetEventCallbacksWide</b> method registers an event callbacks object with this client.

## Syntax

````
HRESULT SetEventCallbacksWide(
  [in] PDEBUG_EVENT_CALLBACKS_WIDE Callbacks
);
````

## Parameters

`Callbacks`

Specifies the interface pointer to the event callbacks object to register with this client.


## Return Value

Depending on the implementation of the method <a href="https://msdn.microsoft.com/library/windows/hardware/ff550737">IDebugEventCallbacks::GetInterestMask</a> in the object specified by <i>Callbacks</i>, other values may be returned, as described in the Remarks section.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

## Remarks

If the value of <i>Callbacks</i> is not <b>NULL</b>, the method <b>IDebugEventCallbacks::GetInterestMask</b> is called.  If the return value is not S_OK, <b>SetEventCallbacks</b> and <b>SetEventCallbacksWide</b> have no effect and they return this value.

Each client can have at most one <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> or <b>IDebugEventCallbacksWide</b> object registered with it for receiving <a href="debugger.events#events#events">events</a>.

The <b>IDebugEventCallbacksWide</b> interface extends the COM interface <b>IUnknown</b>.  When <b>SetEventCallbacks</b> and <b>SetEventCallbacksWide</b> are successful, they call the <b>IUnknown::AddRef</b> method of the object specified by <i>Callbacks</i>.  The <b>IUnknown::Release</b> method of this object will be called the next time <b>SetEventCallbacks</b> or <b>SetEventCallbacksWide</b> is called on this client, or when this client is deleted. 

For more information about callbacks, see <a href="https://msdn.microsoft.com/9090a465-b6ab-4e99-8155-b0abdb729468">Callbacks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546601">GetEventCallbacks</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::SetEventCallbacksWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>