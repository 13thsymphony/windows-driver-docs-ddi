---
UID: NF.storport.StorPortEnablePassiveInitialization
title: StorPortEnablePassiveInitialization function
author: windows-driver-content
description: The StorPortEnablePassiveInitialization routine enables the miniport's HwStorPassiveInitializeRoutine callback routine to execute at PASSIVE_LEVEL during miniport initialization.
old-location: storage\storportenablepassiveinitialization.htm
old-project: storage
ms.assetid: 881253d2-b44d-4c41-ad72-b0143dc50803
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortEnablePassiveInitialization
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
req.alt-api: StorPortEnablePassiveInitialization
req.alt-loc: storport.h
req.ddi-compliance: StorPortEnablePassive, StorPortPassiveFromHwInit
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DIRQL
req.product: Windows 10 or later.
---

# StorPortEnablePassiveInitialization function



## -description
The <b>StorPortEnablePassiveInitialization</b> routine enables  the miniport's <a href="storage.hwstorpassiveinitializeroutine">HwStorPassiveInitializeRoutine</a> callback routine to execute at PASSIVE_LEVEL during miniport initialization.



## -syntax

````
BOOLEAN StorPortEnablePassiveInitialization(
  _In_ PVOID                          HwDeviceExtension,
  _In_ PHW_PASSIVE_INITIALIZE_ROUTINE HwPassiveInitialization
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the per-adapter device extension. 


### -param HwPassiveInitialization [in]

Pointer to a callback routine that the port driver calls at PASSIVE_LEVEL to initialize the DPCs that the miniport driver will use. For a description of this callback routine, see <a href="storage.hwstorpassiveinitializeroutine">HwStorPassiveInitializeRoutine</a>. 


## -returns
The <b>StorPortEnablePassiveInitialization</b> routine returns <b>TRUE</b> if the operating system supports DPCs, and <b>FALSE</b> if not. 


## -remarks
A miniport must call the <b>StorPortEnablePassiveInitialization</b> routine only from within <a href="storage.hwstorinitialize">HwStorInitialize</a>. Otherwise, <b>StorPortEnablePassiveInitialization</b> will return <b>FALSE</b> and the <a href="storage.hwstorpassiveinitializeroutine">HwStorPassiveInitializeRoutine</a> routine will not execute.

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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DIRQL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.storport_storportenablepassive">StorPortEnablePassive</a>, <a href="devtest.storport_storportpassivefromhwinit">StorPortPassiveFromHwInit</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.hwstorpassiveinitializeroutine">HwStorPassiveInitializeRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortEnablePassiveInitialization routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

