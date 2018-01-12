---
UID: NF:ntifs.FsRtlInitializeExtraCreateParameterList
title: FsRtlInitializeExtraCreateParameterList function
author: windows-driver-content
description: The FsRtlInitializeExtraCreateParameterList routine initializes an extra create parameter (ECP) context structure list.
old-location: ifsk\fsrtlinitializeextracreateparameterlist.htm
old-project: ifsk
ms.assetid: 79e56363-1098-42bb-8e6a-c4b4c76e7e7c
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlInitializeExtraCreateParameterList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitializeExtraCreateParameterList routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlInitializeExtraCreateParameterList
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlInitializeExtraCreateParameterList function



## -description
The <b>FsRtlInitializeExtraCreateParameterList</b> routine initializes an extra create parameter (ECP) context structure list. 



## -syntax

````
NTSTATUS FsRtlInitializeExtraCreateParameterList(
  _Inout_ PECP_LIST EcpList
);
````


## -parameters

### -param EcpList [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> structure to initialize. 


## -returns
<b>FsRtlInitializeExtraCreateParameterList</b> returns STATUS_SUCCESS if it successfully initialized the given <a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a> structure, and returns an error if it did not. 


## -remarks


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
The FsRtlInitializeExtraCreateParameterList routine is available starting with Windows 7. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitializeExtraCreateParameterList routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

