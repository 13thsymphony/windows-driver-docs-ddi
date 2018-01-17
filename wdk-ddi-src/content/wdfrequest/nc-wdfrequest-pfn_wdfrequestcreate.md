---
UID: NC:wdfrequest.PFN_WDFREQUESTCREATE
title: PFN_WDFREQUESTCREATE function
author: windows-driver-content
description: The WdfRequestCreate method creates an empty framework request object.
old-location: wdf\wdfrequestcreate.htm
old-project: wdf
ms.assetid: 94329e5a-9efb-4e88-92a6-457098d1245f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFREQUESTCREATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, ReqDelete, RequestForUrbXrb, RequestSendAndForgetNoFormatting2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFREQUESTCREATE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestCreate</b> method creates an empty framework request object.



## -syntax

````
NTSTATUS WdfRequestCreate(
  _In_opt_ PWDF_OBJECT_ATTRIBUTES RequestAttributes,
  _In_opt_ WDFIOTARGET            IoTarget,
  _Out_    WDFREQUEST             *Request
);
````


## -parameters

### -param RequestAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the request object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param IoTarget [in, optional]

A handle to a framework I/O target object. This parameter is optional and can be <b>NULL</b>. If non-<b>NULL</b>, <b>WdfRequestCreate</b> verifies that the driver can eventually send the request to the specified I/O target.


### -param Request [out]

A pointer to a location that receives a handle to a framework request object. 


## -returns
<b>WdfRequestCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There are insufficient system resources to complete the operation.
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>The request's array of I/O stack locations is not large enough to allow the driver to send the request to the specified I/O target.

 

For a list of additional return values, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.



This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.





## -remarks
A framework-based driver can call <b>WdfRequestCreate</b> to create a new request that the driver subsequently passes to other framework functions for initialization. For example, a driver for a USB device might call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforread.md">WdfUsbTargetPipeFormatRequestForRead</a> to format a new read request.

A framework-based driver that communicates with WDM drivers might specify the contents of a request by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreatefromirp.md">WdfRequestCreateFromIrp</a>.

If a driver calls <b>WdfRequestCreate</b> to create a request object, it must not call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> for the request object. Instead, the driver must call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> when it has finished using the request object. For more information, see <a href="https://msdn.microsoft.com/ec5aef7a-110e-430c-902d-669ccc7095ac">Completing I/O Requests</a>.

By default, the new request object's parent is the framework driver object that the <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the request object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the request object when it has finished using the object; otherwise, the request object will remain until the I/O manager unloads your driver. 

For more information about calling <b>WdfRequestCreate</b>, see <a href="https://msdn.microsoft.com/4bd668ec-14fb-4999-9535-a49712a26ba6">Creating Framework Request Objects</a>.

The following code example creates an I/O target object, initializes a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure, and calls <b>WdfRequestCreate</b>. The new request object's parent is the I/O target object.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetrequestattributes.md">WdfDeviceInitSetRequestAttributes</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestcreatefromirp.md">WdfRequestCreateFromIrp</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

