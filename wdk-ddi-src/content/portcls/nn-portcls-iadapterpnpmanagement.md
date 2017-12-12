---
UID: NN.portcls.IAdapterPnpManagement
title: IAdapterPnpManagement
author: windows-driver-content
description: IAdapterPnpManagement is an interface that adapters should implement and register if they want to receive PnP management messages.
old-location: audio\iadapterpnpmanagement.htm
old-project: audio
ms.assetid: A5EF8214-76D9-4F4E-A9FE-9374E0EDC9D2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PcUnregisterIoTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IAdapterPnpManagement
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# IAdapterPnpManagement interface



## -description
<code>IAdapterPnpManagement</code>  is an interface that adapters should implement and
 register if they want to receive PnP management messages.
 Register this interface with PortCls using 
 <a href="audio.pcregisteradapterpnpmanagement">PcRegisterAdapterPnpManagement</a>. Unregister this interface with PortCls using 
 <a href="audio.pcunregisteradapterpnpmanagement">PcUnregisterAdapterPnpManagement</a>.

IAdapterPnpManagement is available in Windows 10, version 1511 and later versions of Windows. 



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IAdapterPnpManagement</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface but does not have additional members.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>