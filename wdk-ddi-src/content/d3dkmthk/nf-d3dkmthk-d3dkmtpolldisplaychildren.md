---
UID: NF.d3dkmthk.D3DKMTPollDisplayChildren
title: D3DKMTPollDisplayChildren function
author: windows-driver-content
description: The D3DKMTPollDisplayChildren function queries for connectivity status of all child devices of the given adapter.
old-location: display\d3dkmtpolldisplaychildren.htm
old-project: display
ms.assetid: 463831c1-d9b2-404d-91f3-78f495668fdf
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3DKMTPollDisplayChildren
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTPollDisplayChildren
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
---

# D3DKMTPollDisplayChildren function



## -description
The <b>D3DKMTPollDisplayChildren</b> function queries for connectivity status of all child devices of the given adapter.


## -syntax

````
NTSTATUS APIENTRY D3DKMTPollDisplayChildren(
  _In_ const D3DKMT_POLLDISPLAYCHILDREN *pData
);
````


## -parameters

### -param pData [in]

A pointer to a <a href="display.d3dkmt_polldisplaychildren">D3DKMT_POLLDISPLAYCHILDREN</a> structure that describes the parameters for querying for connectivity status of the adapter's child devices.

## -returns
<b>D3DKMTPollDisplayChildren</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Connectivity status was successfully retrieved.
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>The graphics adapter was stopped.

 

This function might also return other NTSTATUS values.

## -remarks
The OpenGL installable client driver (ICD) calls <b>D3DKMTPollDisplayChildren</b> to query for connectivity status of all of the adapter's child devices. The ICD sets the <b>NonDestructiveOnly</b> member of <a href="display.d3dkmt_polldisplaychildren">D3DKMT_POLLDISPLAYCHILDREN</a> to indicate whether <b>D3DKMTPollDisplayChildren</b> should be destructive (that is, cause visual artifacts). For typical polling, the ICD should set <b>NonDestructiveOnly</b> to <b>TRUE</b> to prevent the screen from flickering.

New child devices are enumerated to the Plug and Play (PnP) manager when PnP detects them. The devices are then listed in the device manager. If PnP determines that a child device was removed, the device is reported as a surprise removal. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Gdi32.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Gdi32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_polldisplaychildren">D3DKMT_POLLDISPLAYCHILDREN</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTPollDisplayChildren function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
