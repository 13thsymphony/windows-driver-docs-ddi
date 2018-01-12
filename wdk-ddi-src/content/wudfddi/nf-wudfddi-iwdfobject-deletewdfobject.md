---
UID: NF:wudfddi.IWDFObject.DeleteWdfObject
title: IWDFObject::DeleteWdfObject method
author: windows-driver-content
description: The DeleteWdfObject method deletes a previously created Microsoft Windows Driver Frameworks (WDF) object.
old-location: wdf\iwdfobject_deletewdfobject.htm
old-project: wdf
ms.assetid: a777b8df-e255-402a-aa55-14e5861b215f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFObject, IWDFObject::DeleteWdfObject, DeleteWdfObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFObject.DeleteWdfObject
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFObject::DeleteWdfObject method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DeleteWdfObject</b> method deletes a previously created Microsoft Windows Driver Frameworks (WDF) object.



## -syntax

````
HRESULT DeleteWdfObject();
````


## -parameters


## -returns
<b>DeleteWdfObject</b> returns S_OK if the operation succeeds. Otherwise, this method returns HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED) or one of the other error codes that are defined in Winerror.h. 

<b>DeleteWdfObject</b> returns S_OK if the operation succeeds. Otherwise, this method returns HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED) or one of the other error codes that are defined in Winerror.h. 

<b>DeleteWdfObject</b> returns S_OK if the operation succeeds. Otherwise, this method returns HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED) or one of the other error codes that are defined in Winerror.h. 


## -remarks
A driver is unable to delete some WDF objects. For example, the driver cannot delete a <a href="https://msdn.microsoft.com/6be47eac-d6e4-43d1-bf2d-d49dcb2273c0">framework device object</a> because the framework owns and controls device objects. For more information about the hierarchy of WDF objects, see <a href="https://msdn.microsoft.com/ffacca8f-4083-4998-83d2-7c31544eb497">Framework Object Hierarchy</a>. 

The driver typically deletes only WDF objects that it creates and owns. For more information about deleting framework objects, see <a href="https://msdn.microsoft.com/55ad8133-a70a-462f-87cd-6aeaffb0aec8">Managing the Lifetime of Objects</a>. 

However, when a parent object is deleted, all child objects are automatically deleted. For example, if the driver called <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> to create an I/O queue object, the newly created I/O queue becomes a child of the device object. The I/O queue object is then automatically deleted when the device object is deleted without the driver explicitly calling <b>DeleteWdfObject</b>.

For a code example of how to use the <b>DeleteWdfObject</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFObject::DeleteWdfObject method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

