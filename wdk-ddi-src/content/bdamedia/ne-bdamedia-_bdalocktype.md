---
UID: NE.bdamedia._BdaLockType
title: _BdaLockType
author: windows-driver-content
description: The BDA_LockType enumerated type contains values that specify lock types for a signal.
old-location: stream\bda_locktype.htm
old-project: stream
ms.assetid: 6119727a-05af-4a70-a321-5f0f2e439b93
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BdaLockType, BDA_LockType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bdamedia.h
req.include-header: Bdamedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_LockType
req.alt-loc: bdamedia.h
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

# _BdaLockType enumeration



## -description
The BDA_LockType enumerated type contains values that specify lock types for a signal. 


## -syntax

````
typedef enum _BdaLockType { 
  Bda_LockType_None          = 0x00,
  Bda_LockType_PLL           = 0x01,
  Bda_LockType_DecoderDemod  = 0x02,
  Bda_LockType_Complete      = 0x80
} BDA_LockType;
````


## -enum-fields

### -field Bda_LockType_None

The driver does not support any lock types. 

### -field Bda_LockType_PLL

The driver supports a phase-lock-loop (PLL) lock.

### -field Bda_LockType_DecoderDemod

The driver supports a decoder-demodulator lock.

### -field Bda_LockType_Complete

To be supplied.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bdamedia.h (include Bdamedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564369">KSPROPERTY_BDA_SIGNAL_LOCK_CAPS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff564370">KSPROPERTY_BDA_SIGNAL_LOCK_TYPE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_LockType enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
