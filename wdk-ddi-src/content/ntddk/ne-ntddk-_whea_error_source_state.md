---
UID: NE.ntddk._WHEA_ERROR_SOURCE_STATE
title: _WHEA_ERROR_SOURCE_STATE
author: windows-driver-content
description: The WHEA_ERROR_SOURCE_STATE enumeration defines the different runtime states for an error source.
old-location: whea\whea_error_source_state.htm
old-project: whea
ms.assetid: 7be90712-9f6f-4998-a8ca-148ff900c82c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WHEA_ERROR_SOURCE_STATE, WHEA_ERROR_SOURCE_STATE, *PWHEA_ERROR_SOURCE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_ERROR_SOURCE_STATE
req.alt-loc: ntddk.h
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
---

# _WHEA_ERROR_SOURCE_STATE enumeration



## -description
The WHEA_ERROR_SOURCE_STATE enumeration defines the different runtime states for an error source.



## -syntax

````
typedef enum _WHEA_ERROR_SOURCE_STATE { 
  WheaErrSrcStateStopped  = 0x01,
  WheaErrSrcStateStarted  = 0x02
} WHEA_ERROR_SOURCE_STATE, *PWHEA_ERROR_SOURCE_STATE;
````


## -enum-fields

### -field WheaErrSrcStateStopped

The error source is stopped.


### -field WheaErrSrcStateStarted

The error source is started.


## -remarks
The <a href="whea.whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure contains a member of type WHEA_ERROR_SOURCE_STATE that indicates the runtime state of the error source.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.


</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="whea.whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_SOURCE_STATE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

