---
UID : NF:prnasntp.RouterCreatePrintAsyncNotificationChannel
title : RouterCreatePrintAsyncNotificationChannel function
author : windows-driver-content
description : The RouterCreatePrintAsyncNotificationChannel function creates an asynchronous notification channel that is associated with a printer or print server.
old-location : print\routercreateprintasyncnotificationchannel.htm
old-project : print
ms.assetid : 11f9a438-861f-42ef-b4f5-f64b0b9d658a
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : RouterCreatePrintAsyncNotificationChannel
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : prnasntp.h
req.include-header : Prnasntp.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RouterCreatePrintAsyncNotificationChannel
req.alt-loc : Spoolss.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Spoolss.lib
req.dll : Spoolss.dll
req.irql : 
req.typenames : "*PUSERDATA, USERDATA"
req.product : Windows 10 or later.
---


# RouterCreatePrintAsyncNotificationChannel function
The <code>RouterCreatePrintAsyncNotificationChannel</code> function creates an asynchronous notification channel that is associated with a printer or print server.

## Syntax

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

## Parameters

`pName`

A pointer to a null-terminated string that specifies the name of the printer or print server.

`pNotificationType`

A pointer to a GUID that represents the type of notifications sent through this channel.

`eNotifyFilter`



`eConversationStyle`

The type of communication: unidirectional or bidirectional.

`pCallback`

A pointer to the callback function that is called to deliver the response notifications, when bidirectional communication is in effect. This parameter is ignored when unidirectional communication is in effect.

`ppIAsynchNotification`




## Return Value

<code>RouterCreatePrintAsyncNotificationChannel</code> returns S_OK on success and returns a standard COM error code otherwise.

## Remarks

In some cases, you must release the channel that you created with the <code>RouterCreatePrintAsyncNotificationChannel</code> function by calling <b>Release</b> on IPrintAsyncNotifyChannel. For information about when to release a channel, see <a href="https://msdn.microsoft.com/3161342a-0737-4f3b-bb16-32d6949bceea">Notification Channel</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | prnasntp.h (include Prnasntp.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |