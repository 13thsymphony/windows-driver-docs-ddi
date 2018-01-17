---
UID: NC:fltkernel.PFLT_COMPLETED_ASYNC_IO_CALLBACK
title: PFLT_COMPLETED_ASYNC_IO_CALLBACK
author: windows-driver-content
description: A minifilter driver that initiates an asynchronous I/O operation can specify a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK routine to be called when the operation is completed.
old-location: ifsk\pflt_completed_async_io_callback.htm
old-project: ifsk
ms.assetid: 920e4236-9078-41c6-befb-9e82accbfa59
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxpTrackReference
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFLT_COMPLETED_ASYNC_IO_CALLBACK
req.alt-loc: fltkernel.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# PFLT_COMPLETED_ASYNC_IO_CALLBACK callback



## -description
A minifilter driver that initiates an asynchronous I/O operation can specify a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK routine to be called when the operation is completed. 



## -prototype

````
typedef VOID ( *PFLT_COMPLETED_ASYNC_IO_CALLBACK)(
  _In_ PFLT_CALLBACK_DATA CallbackData,
  _In_ PFLT_CONTEXT       Context
);
````


## -parameters

### -param CallbackData [in]

Pointer to the callback data structure for the I/O operation. 


### -param Context [in]

Context pointer that the minifilter driver passed as a parameter to <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>, <a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>, or <a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>. 


## -returns
None 


## -remarks
When a minifilter driver calls <a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>, <a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a> or <a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a> to initiate an asynchronous I/O operation, the minifilter driver can optionally specify a callback routine to be called when the I/O operation is completed. This is done by specifying a routine of type PFLT_COMPLETED_ASYNC_IO_CALLBACK for the <i>CallbackRoutine</i> parameter. 

When the I/O operation is completed, this callback routine is called in an arbitrary thread context, at IRQL &lt;= DISPATCH_LEVEL. 

Because the PFLT_COMPLETED_ASYNC_IO_CALLBACK routine can be called at IRQL DISPATCH_LEVEL, it is subject to the following constraints: 

It cannot safely call any kernel-mode routines that require a lower IRQL. 

Any data structures used in this routine must be allocated from nonpaged pool. 

It cannot be made pageable. 

It cannot acquire resources, mutexes, or fast mutexes. However, it can acquire spin locks. 


## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltperformasynchronousio.md">FltPerformAsynchronousIo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFLT_COMPLETED_ASYNC_IO_CALLBACK function pointer%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

