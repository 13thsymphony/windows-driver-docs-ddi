---
UID: NS:ks.KSMETHOD_ITEM
title: KSMETHOD_ITEM
author: windows-driver-content
description: The KSMETHOD_ITEM structure describes a single method within a method set.
old-location: stream\ksmethod_item.htm
old-project: stream
ms.assetid: 79119458-a6a7-433e-9306-d7a56ca056c2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSMETHOD_ITEM, KSMETHOD_ITEM, *PKSMETHOD_ITEM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSMETHOD_ITEM
req.alt-loc: ks.h
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
req.typenames: KSMETHOD_ITEM, *PKSMETHOD_ITEM
---

# KSMETHOD_ITEM structure



## -description
The KSMETHOD_ITEM structure describes a single method within a method set.



## -syntax

````
typedef struct {
  ULONG        MethodId;
  union {
    PFNKSHANDLER MethodHandler;
    BOOLEAN      MethodSupported;
  };
  ULONG        MinMethod;
  ULONG        MinData;
  PFNKSHANDLER SupportHandler;
  ULONG        Flags;
} KSMETHOD_ITEM, *PKSMETHOD_ITEM;
````


## -struct-fields

### -field MethodId

Specifies the identifier of this method within its method set.


### -field MethodHandler

Pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkshandler.md">KStrMethodHandler</a> callback routine.


### -field MethodSupported

Specifies if this method is supported or not.


### -field MinMethod

Specifies the minimum size of buffer required to specify the method completely. This size is at least <b>sizeof</b>(KSMETHOD) bytes.


### -field MinData

Specifies the minimum size buffer required to specify the method data buffer. This buffer is used to read and/or write information related to the method.


### -field SupportHandler

Pointer to a minidriver-supplied <a href="..\ks\nc-ks-pfnkshandler.md">KStrSupportHandler</a> callback routine.


### -field Flags

Specifies the request type of this method request.

<table>
<tr>
<th>Value</th>
<th>Type of method request</th>
</tr>
<tr>
<td>
KSMETHOD_TYPE_NONE

</td>
<td>
Indicates that the <i>Data</i> buffer of the handler is not expected to be used. For buffered methods, although space is allocated, no data is copied to or from the system buffer. When in source mode (KSMETHOD_TYPE_SOURCE), no MDL is created.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_READ

</td>
<td>
Indicates that parameters are expected to be read from the <i>Data</i> buffer of the handler. When buffered, data is copied to the system buffer. When in source mode, the data is probed and locked for <b>IoReadAccess</b>.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_WRITE

</td>
<td>
Indicates that parameters are expected to be written to the <i>Data</i> buffer of the handler. When buffered, data is copied from the system buffer. When in source mode, the data is probed and locked for <b>IoWriteAccess</b>.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_MODIFY

</td>
<td>
Indicates that parameters are expected to be read and written to the <i>Data</i> buffer of the handler. The data passed in is overwritten by the data returned. This might imply that a structure passed in could be merely updated. When buffered, the data is copied to the system buffer, and copied back when the IRP is completed. When in source mode, the data is probed and locked for <b>IoModifyAccess</b>.

</td>
</tr>
<tr>
<td>
KSMETHOD_TYPE_SOURCE

</td>
<td>
Indicates that the method is to be processed in source mode. An MDL is allocated and the data is probed and locked. To indicate a buffered method, OR this flag with other flags from this list.

</td>
</tr>
</table>
 


## -remarks
A minidriver uses the KSMETHOD_ITEM structure to define methods in a method set. The minidriver implements methods and uses the <b>MethodHandler</b> member to point to these methods. A client can then use the IOCTL_KS_METHOD request along with the KSMETHOD structure to execute methods on a kernel streaming object that the minidriver handles. For more information, see <a href="https://msdn.microsoft.com/1d7bd6f4-0aaf-4d77-8132-f551fd2ecbd2">KS Methods</a>.


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
<a href="..\ks\nc-ks-pfnkshandler.md">KStrSupportHandler</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksfastmethod_item.md">KSFASTMETHOD_ITEM</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSMETHOD_ITEM structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

