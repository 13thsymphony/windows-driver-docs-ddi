---
UID: NF:dbgeng.IDebugControl4.GetEventFilterTextWide
title: IDebugControl4::GetEventFilterTextWide method
author: windows-driver-content
description: The GetEventFilterTextWide method returns a short description of an event for a specific filter.
old-location: debugger\geteventfiltertextwide.htm
old-project: debugger
ms.assetid: 76b0d865-a620-4ced-904c-d1d613dbadd1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl4, IDebugControl4::GetEventFilterTextWide, GetEventFilterTextWide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl4.GetEventFilterTextWide
req.alt-loc: dbgeng.h
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugControl4::GetEventFilterTextWide method



## -description
The <b>GetEventFilterTextWide</b>  method returns a short description of an event for a specific filter.



## -syntax

````
HRESULT GetEventFilterTextWide(
  [in]            ULONG  Index,
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG TextSize
);
````


## -parameters

### -param Index [in]

Specifies the index of the event filter whose description will be returned.  Only the specific filters have a description attached to them; <i>Index</i> must refer to a specific filter.


### -param Buffer [out, optional]

Receives the description of the specific filter.


### -param BufferSize [in]

Specifies the size, in characters, of the buffer that <i>Buffer</i> specifies.


### -param TextSize [out, optional]

Receives the size of the event description.  If <i>TextSize</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl><i>Index</i> did not refer to a specific filter.  This can occur if <i>Index</i> refers to an arbitrary exception filter.

 


## -remarks
For more information about <a href="debugger.events#event_filters#event_filters">event filters</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548398">GetSpecificFilterParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetEventFilterTextWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

