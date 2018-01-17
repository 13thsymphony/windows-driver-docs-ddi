---
UID: NF:wdfrequest.WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
title: WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function
author: windows-driver-content
description: The WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function sets a new IRP in a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location: wdf\wdf_request_reuse_params_set_new_irp.htm
old-project: wdf
ms.assetid: 3a18ec1b-be02-418a-8a38-deca7178ce30
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
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
req.alt-api: WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
req.alt-loc: wdfrequest.h
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
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> function sets a new IRP in a driver's <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure.



## -syntax

````
VOID WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP(
  _Inout_ PWDF_REQUEST_REUSE_PARAMS Params,
  _In_    PIRP                      NewIrp
);
````


## -parameters

### -param Params [in, out]

A pointer to a caller-supplied <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure.


### -param NewIrp [in]

A pointer to a caller-supplied <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure.


## -returns
None


## -remarks
If a driver's call to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a> specifies a new IRP structure, the driver must first call <a href="..\wdfrequest\nf-wdfrequest-wdf_request_reuse_params_init.md">WDF_REQUEST_REUSE_PARAMS_INIT</a> and then call <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> to initialize a WDF_REQUEST_REUSE_PARAMS structure.

The <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> function sets the structure's <b>NewIrp</b> member to the specified IRP pointer. It also sets the <b>WDF_REQUEST_REUSE_SET_NEW_IRP</b> flag in the structure's <b>Flag</b> member.

The following code example initializes a <a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a> structure, provides a new IRP structure for the I/O request, and then calls <a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestreuse.md">WdfRequestReuse</a>
</dt>
<dt>
<a href="..\wdfrequest\ns-wdfrequest-_wdf_request_reuse_params.md">WDF_REQUEST_REUSE_PARAMS</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdf_request_reuse_params_init.md">WDF_REQUEST_REUSE_PARAMS_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

