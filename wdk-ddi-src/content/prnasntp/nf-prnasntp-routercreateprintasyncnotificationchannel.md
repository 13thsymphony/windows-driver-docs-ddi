---
UID: NF.prnasntp.RouterCreatePrintAsyncNotificationChannel
title: RouterCreatePrintAsyncNotificationChannel function
author: windows-driver-content
description: The RouterCreatePrintAsyncNotificationChannel function creates an asynchronous notification channel that is associated with a printer or print server.
old-location: print\routercreateprintasyncnotificationchannel.htm
old-project: print
ms.assetid: 11f9a438-861f-42ef-b4f5-f64b0b9d658a
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: RouterCreatePrintAsyncNotificationChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prnasntp.h
req.include-header: Prnasntp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RouterCreatePrintAsyncNotificationChannel
req.alt-loc: Spoolss.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
req.product: Windows 10 or later.
---

# RouterCreatePrintAsyncNotificationChannel function



## -description
The <code>RouterCreatePrintAsyncNotificationChannel</code> function creates an asynchronous notification channel that is associated with a printer or print server.



## -syntax

````
HRESULT RouterCreatePrintAsyncNotificationChannel(
  _In_  PCWSTR                            pName,
  _In_  PrintAsyncNotificationType        *pNotificationType,
  _In_  PrintAsyncNotifyUserFilter        eNotificationFilter,
  _In_  PrintAsyncNotifyConversationStyle eConversationStyle,
  _In_  IPrintAsyncNotifyCallback         *pCallback,
  _Out_ IPrintAsyncNotifyChannel          **ppIAsyncNotification
);
````


## -parameters

### -param pName [in]

A pointer to a null-terminated string that specifies the name of the printer or print server.


### -param pNotificationType [in]

A pointer to a GUID that represents the type of notifications sent through this channel.


### -param eNotificationFilter [in]

A filter for the session or user that receives the notifications.


### -param eConversationStyle [in]

The type of communication: unidirectional or bidirectional.


### -param pCallback [in]

A pointer to the callback function that is called to deliver the response notifications, when bidirectional communication is in effect. This parameter is ignored when unidirectional communication is in effect.


### -param ppIAsyncNotification [out]

A pointer to a variable that receives the address of the interface object that represents the notification channel.


## -returns
<code>RouterCreatePrintAsyncNotificationChannel</code> returns S_OK on success and returns a standard COM error code otherwise.


## -remarks
In some cases, you must release the channel that you created with the <code>RouterCreatePrintAsyncNotificationChannel</code> function by calling <b>Release</b> on IPrintAsyncNotifyChannel. For information about when to release a channel, see <a href="https://msdn.microsoft.com/3161342a-0737-4f3b-bb16-32d6949bceea">Notification Channel</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Prnasntp.h (include Prnasntp.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Spoolss.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Spoolss.dll</dt>
</dl>
</td>
</tr>
</table>