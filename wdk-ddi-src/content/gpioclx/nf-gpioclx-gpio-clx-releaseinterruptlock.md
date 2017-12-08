---
UID: NF.gpioclx.GPIO_CLX_ReleaseInterruptLock
title: GPIO_CLX_ReleaseInterruptLock
author: windows-driver-content
description: The GPIO_CLX_ReleaseInterruptLock method releases an interrupt lock on the specified bank.
old-location: gpio\gpio_clx_releaseinterruptlock.htm
old-project: GPIO
ms.assetid: 195B9FA2-F7B2-4EA0-9D53-63E438666760
ms.author: windowsdriverdev
ms.date: 11/3/2017
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
req.iface: 
---

# GPIO_CLX_ReleaseInterruptLock function



## -description
<p>The <b>GPIO_CLX_ReleaseInterruptLock</b> method releases an interrupt lock on the specified bank.</p>


## -syntax

````
VOID GPIO_CLX_ReleaseInterruptLock(
  _In_ PVOID   Context,
  _In_ BANK_ID BankId
);
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>. The GPIO framework extension (GpioClx) passes this pointer value as a parameter to the callback functions that are implemented by the GPIO controller driver.</p>
</dd>

### -param BankId [in]

<dd>
<p>The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>This method releases the interrupt lock that the caller acquired in a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439482">GPIO_CLX_AcquireInterruptLock</a> method.</p>

<p>If the previous call to the <b>GPIO_CLX_AcquireInterruptLock</b> method raised the calling thread's IRQL, <b>GPIO_CLX_ReleaseInterruptLock</b> restores this IRQL to its original level.</p>

<p>If the <i>Context</i> parameter is NULL or points to an invalid GPIO device context, this method causes a bug check in debug builds of GpioClx.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gpioclx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Msgpioclxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh439482">GPIO_CLX_AcquireInterruptLock</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_ReleaseInterruptLock method%20 RELEASE:%20(11/3/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
