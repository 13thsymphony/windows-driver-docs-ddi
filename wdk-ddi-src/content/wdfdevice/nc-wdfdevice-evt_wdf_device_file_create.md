---
UID: NC.wdfdevice.EVT_WDF_DEVICE_FILE_CREATE
title: EVT_WDF_DEVICE_FILE_CREATE
author: windows-driver-content
description: A driver's EvtDeviceFileCreate callback function handles operations that must be performed when an application requests access to a device.
old-location: wdf\evtdevicefilecreate.htm
old-project: wdf
ms.assetid: ee44c0bf-1fca-442d-8871-df6079e89ced
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WDF_REL_TIMEOUT_IN_US
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtDeviceFileCreate
req.alt-loc: Wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_FILE_CREATE callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceFileCreate</i> callback function handles operations that must be performed when an application requests access to a device.



## -prototype

````
EVT_WDF_DEVICE_FILE_CREATE EvtDeviceFileCreate;

VOID EvtDeviceFileCreate(
  _In_ WDFDEVICE     Device,
  _In_ WDFREQUEST    Request,
  _In_ WDFFILEOBJECT FileObject
)
{ ... }
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Request [in]

A handle to a framework request object that represents a file creation request.


### -param FileObject [in]

A handle to a framework file object that describes a file that is being opened for the specified request. This parameter is <b>NULL</b> if the driver has specified <a href="wdf.wdf_fileobject_class">WdfFileObjectNotRequired</a> for the <b>FileObjectClass </b>member of the <a href="wdf.wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a> structure.


## -returns
None


## -remarks
The framework calls a driver's <i>EvtDeviceFileCreate</i> callback function when a user application or another driver opens the device to perform an I/O operation, such as reading or writing a file. 

The driver can pass the <i>Request</i> handle to <a href="wdf.wdfrequestgetparameters">WdfRequestGetParameters</a> to retrieve parameters that are associated with the file creation request. The parameters are stored in the <b>Parameters.Create</b> member of the <a href="wdf.wdf_request_parameters">WDF_REQUEST_PARAMETERS</a> structure. 

This callback function is called synchronously, in the context of the user thread that opens the device. 

To register an <i>EvtDeviceFileCreate</i> callback function, the driver must call the <a href="wdf.wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

For more information about framework file objects and the <i>EvtDeviceFileCreate</i> callback function, see <a href="wdf.framework_file_objects">Framework File Objects</a>.

To define an <i>EvtDeviceFileCreate</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceFileCreate</i> callback function that is named <i>MyDeviceFileCreate</i>, use the <b>EVT_WDF_DEVICE_FILE_CREATE</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_DEVICE_FILE_CREATE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_FILE_CREATE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_fileobject_config">WDF_FILEOBJECT_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_FILE_CREATE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

