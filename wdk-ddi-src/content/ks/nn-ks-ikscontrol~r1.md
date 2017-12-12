---
UID: NN.ks.IKsControl~r1
title: IKsControl
author: windows-driver-content
description: The IKsControl interface is a COM-style interface implemented on AVStream filters and pins.
old-location: stream\ikscontrol8.htm
old-project: stream
ms.assetid: 33eb0244-e0f3-4db7-b6df-2668e826fbd8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KsEdit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsControl
req.alt-loc: Ks.h
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
---

# IKsControl interface



## -description
The <b>IKsControl</b> interface is a COM-style interface implemented on AVStream filters and pins. It enables clients in kernel mode to access AVStream automation objects (properties, methods, and events). See the <a href="..\ks\nn-ks-ikscontrol~r1.md">IKsControl</a> kernel-streaming proxy COM interface for information about the kernel-mode equivalent of this interface.



## -syntax

````
    IKsControl *Control;

    if (NT_SUCCESS (
      KsPinGetConnectedPinInterface (
        Pin,
        IID_IKsControl,
        (PVOID *)&Control) )
    ) {
      Control -> KsProperty (...);
      Control -> Release ();
    }
````


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IKsControl</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IKsControl</b> also has these types of members:

The <b>IKsControl</b> interface has these methods.

Enables or disables an event.

Sends a method to a KS object.

Sets a property or retrieves property information.

 


## -members
The <b>IKsControl</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="stream.ikscontrol_ksevent2">KsEvent</a>
</td>
<td align="left" width="63%">
Enables or disables an event.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="stream.ikscontrol_ksmethod2">KsMethod</a>
</td>
<td align="left" width="63%">
Sends a method to a KS object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="stream.ikscontrol_ksproperty2">KsProperty</a>
</td>
<td align="left" width="63%">
Sets a property or retrieves property information.

</td>
</tr>
</table>Enables or disables an event.

Sends a method to a KS object.

Sets a property or retrieves property information.

 


## -remarks
Minidrivers typically acquire the <b>IKsControl</b> interface through a call to <a href="stream.kspingetconnectedfilterinterface">KsPinGetConnectedFilterInterface</a> or <a href="stream.kspingetconnectedpininterface">KsPinGetConnectedPinInterface</a>. Because this is a COM-style interface, the function call to obtain this interface calls the <b>QueryInterface</b> method, which in turn calls the <b>AddRef</b> method. Therefore, the minidriver does not have to perform these steps.

However, as soon as the client is finished with the <b>IKsControl</b> interface, it must release <b>IKsControl</b> with a call to the <b>Release</b> method.
    Minidrivers that are written in C manipulate the <b>IKsControl</b> interface as a structure that contains a pointer to a table of functions instead of a C++ abstract base class. 

A client that is written in C++ does the following:
    

However, a client that is written in C uses this code instead:

For more information, see <a href="https://msdn.microsoft.com/305039fe-0a00-4f3e-ae1a-61c50a2f2fb3">AVStream Overview</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nn-ks-ikscontrol~r1.md">IKsControl (Kernel Streaming Proxy)</a>
</dt>
<dt>
<a href="stream.kspingetconnectedpininterface">KsPinGetConnectedPinInterface</a>
</dt>
<dt>
<a href="stream.kspingetconnectedfilterinterface">KsPinGetConnectedFilterInterface</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl interface%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

