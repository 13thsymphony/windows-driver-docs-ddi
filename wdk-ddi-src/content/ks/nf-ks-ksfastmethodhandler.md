---
UID: NF.ks.KsFastMethodHandler
title: KsFastMethodHandler function
author: windows-driver-content
description: The KsFastMethodHandler function handles fast methods requested through IOCTL_KS_METHOD. It responds to all method identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.
old-location: stream\ksfastmethodhandler.htm
old-project: stream
ms.assetid: 829e96e7-7063-4de3-b13a-0b0d12ba1f44
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsFastMethodHandler
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsFastMethodHandler
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsFastMethodHandler function



## -description
The <b>KsFastMethodHandler</b> function handles fast methods requested through IOCTL_KS_METHOD. It responds to all method identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL.



## -syntax

````
BOOLEAN KsFastMethodHandler(
  _In_          PFILE_OBJECT     FileObject,
  _In_          PKSMETHOD        Method,
  _In_          ULONG            MethodLength,
  _Inout_       PVOID            Data,
  _In_          ULONG            DataLength,
  _Out_         PIO_STATUS_BLOCK IoStatus,
  _In_          ULONG            MethodSetsCount,
  _In_    const KSMETHOD_SET     *MethodSet
);
````


## -parameters

### -param FileObject [in]

Specifies the file object on which the request was made.


### -param Method [in]

Specifies the original method parameter. This will always be on FILE_LONG_ALIGNMENT, but may not be on FILE_QUAD_ALIGNMENT.


### -param MethodLength [in]

Specifies the length indicated by the caller of the method parameter.


### -param Data [in, out]

Specifies the original unaligned data parameter.


### -param DataLength [in]

Specifies the length indicated by the caller of the data parameter.


### -param IoStatus [out]

Specifies an aligned structure that is used to return error status and information.


### -param MethodSetsCount [in]

Indicates the number of method set structures being passed.


### -param MethodSet [in]

Specifies the pointer to the list of method set information.


## -returns
The <b>KsFastMethodHandler</b> function returns <b>TRUE</b> if the request is handled, or <b>FALSE</b> if the request is not handled. If the request is not handled, an IRP is generated. If the request was handled, the function sets the IoStatus-&gt;Information element to zero because of an internal error or the element is set by a method handler. The method handler also sets the IoStatus-&gt;Status field when the method is handled.


## -remarks
The owner of a method set can perform prefiltering or postfiltering of the method handling using the <b>KsFastMethodHandler</b> and <b>KsMethodHandler </b>functions. The <b>KsFastMethodHandler</b> function is used to process requests made through the fast I/O dispatch interface for Device Control. It is only used to process requests that can be fulfilled quickly. The <i>Wait</i> parameter of the fast I/O function is not passed and assumed to be <b>TRUE</b>.


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
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksmethodhandler">KsMethodHandler</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFastMethodHandler function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

