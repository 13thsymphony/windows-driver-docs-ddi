---
UID: NF.gpioclx.GPIO_CLX_ReleaseInterruptLock
title: GPIO_CLX_ReleaseInterruptLock function
author: windows-driver-content
description: The GPIO_CLX_ReleaseInterruptLock method releases an interrupt lock on the specified bank.
old-location: gpio\gpio_clx_releaseinterruptlock.htm
old-project: GPIO
ms.assetid: 195B9FA2-F7B2-4EA0-9D53-63E438666760
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO_CLX_ReleaseInterruptLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: gpioclx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GPIO_CLX_ReleaseInterruptLock
req.alt-loc: Msgpioclxstub.lib,Msgpioclxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Msgpioclxstub.lib
req.dll: 
req.irql: See Remarks.
---

# GPIO_CLX_ReleaseInterruptLock function



## -description
The <b>GPIO_CLX_ReleaseInterruptLock</b> method releases an interrupt lock on the specified bank.



## -syntax

````
VOID GPIO_CLX_ReleaseInterruptLock(
  _In_ PVOID   Context,
  _In_ BANK_ID BankId
);
````


## -parameters

### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>. The GPIO framework extension (GpioClx) passes this pointer value as a parameter to the callback functions that are implemented by the GPIO controller driver.


### -param BankId [in]

The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1.


## -returns
None.


## -remarks
This method releases the interrupt lock that the caller acquired in a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439482">GPIO_CLX_AcquireInterruptLock</a> method.

If the previous call to the <b>GPIO_CLX_AcquireInterruptLock</b> method raised the calling thread's IRQL, <b>GPIO_CLX_ReleaseInterruptLock</b> restores this IRQL to its original level.

If the <i>Context</i> parameter is NULL or points to an invalid GPIO device context, this method causes a bug check in debug builds of GpioClx.


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
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Msgpioclxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
See Remarks.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439482">GPIO_CLX_AcquireInterruptLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_ReleaseInterruptLock method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

