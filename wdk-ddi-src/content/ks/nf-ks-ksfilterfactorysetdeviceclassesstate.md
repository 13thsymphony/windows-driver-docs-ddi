---
UID: NF.ks.KsFilterFactorySetDeviceClassesState
title: KsFilterFactorySetDeviceClassesState function
author: windows-driver-content
description: The KsFilterFactorySetDeviceClassesState function enables or disables the device classes that have been registered by a given filter factory.
old-location: stream\ksfilterfactorysetdeviceclassesstate.htm
old-project: stream
ms.assetid: 66515f08-b652-4aa0-8f22-b5ff0a407d6a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsFilterFactorySetDeviceClassesState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsFilterFactorySetDeviceClassesState
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
req.irql: PASSIVE_LEVEL
---

# KsFilterFactorySetDeviceClassesState function



## -description
The <b>KsFilterFactorySetDeviceClassesState</b> function enables or disables the device classes that have been registered by a given filter factory.



## -syntax

````
NTSTATUS KsFilterFactorySetDeviceClassesState(
  _In_ PKSFILTERFACTORY FilterFactory,
  _In_ BOOLEAN          NewState
);
````


## -parameters

### -param FilterFactory [in]

A pointer to the <a href="stream.ksfilterfactory">KSFILTERFACTORY</a> for which to change device class status.


### -param NewState [in]

If set to <b>TRUE</b>, the device classes are enabled; if <b>FALSE</b>, they are disabled.


## -returns
<b>KsFilterFactorySetDeviceClassesState</b> returns STATUS_SUCCESS or an error code.


## -remarks
This function is available in Windows XP and DirectX 8.0 and later.


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
Version

</th>
<td width="70%">
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>