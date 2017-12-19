---
UID: NF.storport.StorPortInitializeDpc
title: StorPortInitializeDpc function
author: windows-driver-content
description: The StorPortInitializeDpc routine initializes a StorPort DPC.
old-location: storage\storportinitializedpc.htm
old-project: storage
ms.assetid: 0a67304f-c746-46c1-87c4-5d027219e41f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortInitializeDpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortInitializeDpc
req.alt-loc: storport.h
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
req.product: Windows 10 or later.
---

# StorPortInitializeDpc function



## -description
The <b>StorPortInitializeDpc</b> routine initializes a StorPort DPC. 



## -syntax

````
VOID StorPortInitializeDpc(
  _In_  PVOID           DeviceExtension,
  _Out_ PSTOR_DPC       Dpc,
  _In_  PHW_DPC_ROUTINE HwDpcRoutine
);
````


## -parameters

### -param DeviceExtension [in]

Pointer to the per-adapter device extension. 


### -param Dpc [out]

Pointer to a buffer where a DPC object of type <a href="storage.stor_dpc">STOR_DPC</a> will be created. The caller must ensure that the size in bytes of this buffer is greater than or equal to <b>sizeof</b>(STOR_DPC). 


### -param HwDpcRoutine [in]

Pointer to the DPC routine that corresponds to the DPC object pointed to by <i>Dpc</i>. The prototype for this deferred routine is defined in Storport.h as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*PHW_DPC_ROUTINE) 
  IN PSTOR_DPC  Dpc,
  IN PVOID  HwDeviceExtension,
  IN PVOID  SystemArgument1,
  IN PVOID  SystemArgument2
  );</pre>
</td>
</tr>
</table></span></div>

## -returns
None. 


## -remarks
The <b>StorPortInitializeDpc</b> routine must be called during HBA initialization from within the miniport driver's <a href="storage.hwstorpassiveinitializeroutine">HwStorPassiveInitializeRoutine</a> routine. 

This routine is implemented using inline function definitions, so that miniport drivers that use this routine will not have to link to libraries that are dependent on the version of the operating system. Miniport drivers can use this routine without sacrificing backward compatibility with versions of the operating system that do not support DPCs in storage miniport drivers. 


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
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hwstorpassiveinitializeroutine">HwStorPassiveInitializeRoutine</a>
</dt>
<dt>
<a href="storage.stor_dpc">STOR_DPC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializeDpc routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

