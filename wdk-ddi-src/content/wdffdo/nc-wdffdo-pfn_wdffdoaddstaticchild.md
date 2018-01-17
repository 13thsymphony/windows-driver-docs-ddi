---
UID: NC:wdffdo.PFN_WDFFDOADDSTATICCHILD
title: PFN_WDFFDOADDSTATICCHILD function
author: windows-driver-content
description: The WdfFdoAddStaticChild method adds a specified device to a function driver's list of child devices that have been identified by static enumeration.
old-location: wdf\wdffdoaddstaticchild.htm
old-project: wdf
ms.assetid: 3e1c4469-7ae2-4ac8-8dfe-ff8c4cae3d20
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFFDOADDSTATICCHILD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfFdoAddStaticChild
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: AddPdoToStaticChildList, DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# PFN_WDFFDOADDSTATICCHILD function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoAddStaticChild</b> method adds a specified device to a function driver's list of child devices that have been identified by static enumeration.



## -syntax

````
NTSTATUS WdfFdoAddStaticChild(
  _In_ WDFDEVICE Fdo,
  _In_ WDFDEVICE Child
);
````


## -parameters

### -param Fdo [in]

A handle to a framework device object that represents the parent device.


### -param Child [in]

A handle to a framework device object that represents the child device.


## -returns
If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><i>Fdo</i> is not a handle to a function driver's device object.

 

The method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.


## -remarks
Drivers that use static bus enumeration can call <b>WdfFdoAddStaticChild</b>. For more information about static child lists, see <a href="https://msdn.microsoft.com/5731db82-2bc8-4a8d-98f1-3977845f572c">Enumerating the Devices on a Bus</a>.

If <b>WdfFdoAddStaticChild</b> returns an NTSTATUS value that <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a> evaluates as <b>FALSE</b>, the driver must call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> to delete the framework device object that represents the child device. The driver must not delete the framework device object after <b>WdfFdoAddStaticChild</b> returns STATUS_SUCCESS.

The following code example creates a framework device object that represents a new child device and adds the child device to the parent device's list of children. For the complete code example, see the <a href="wdf.sample_kmdf_drivers">KbFiltr</a> sample driver.


## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>
</dt>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitallocate.md">WdfPdoInitAllocate</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoAddStaticChild method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

