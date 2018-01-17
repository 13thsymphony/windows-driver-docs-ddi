---
UID: NC:wdfcollection.PFN_WDFCOLLECTIONCREATE
title: PFN_WDFCOLLECTIONCREATE function
author: windows-driver-content
description: The WdfCollectionCreate method creates a framework collection object.
old-location: wdf\wdfcollectioncreate.htm
old-project: wdf
ms.assetid: b185b1ca-6fd9-4508-b001-d1853f2948c2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFCOLLECTIONCREATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcollection.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfCollectionCreate
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---

# PFN_WDFCOLLECTIONCREATE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionCreate</b> method creates a framework collection object. 



## -syntax

````
NTSTATUS WdfCollectionCreate(
  _In_opt_ PWDF_OBJECT_ATTRIBUTES CollectionAttributes,
  _Out_    WDFCOLLECTION          *Collection
);
````


## -parameters

### -param CollectionAttributes [in, optional]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new collection object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param Collection [out]

A pointer to a location that receives a handle to the new collection object.


## -returns
<b>WdfCollectionCreate</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The caller supplied an invalid parameter value.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A collection object could not be allocated.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
After calling <b>WdfCollectionCreate</b> to create a framework collection object, a driver can call <a href="..\wdfcollection\nf-wdfcollection-wdfcollectionadd.md">WdfCollectionAdd</a> to add objects to the collection. 

By default, the new collection object's parent is the framework driver object that the <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the collection object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the collection object when it has finished using the object; otherwise, the object will remain until the I/O manager unloads your driver. 

For more information about object collections, see <a href="https://msdn.microsoft.com/e3f29be6-ee4c-487a-8c85-18be8b6a5cdc">Framework Object Collections</a>.

For a code example that uses <b>WdfCollectionCreate</b>, see <a href="..\wdfcollection\nf-wdfcollection-wdfcollectionadd.md">WdfCollectionAdd</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfcollection\nf-wdfcollection-wdfcollectionadd.md">WdfCollectionAdd</a>
</dt>
<dt>
<a href="..\wdfcollection\nf-wdfcollection-wdfcollectionremove.md">WdfCollectionRemove</a>
</dt>
<dt>
<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCollectionCreate method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

