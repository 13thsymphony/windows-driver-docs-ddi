---
UID: NN:bidispl.IBidiRequestContainer
title: IBidiRequestContainer
author: windows-driver-content
description: The IBidiRequestContainer interface allows an application or other objects to compose and retrieve a list of bidi requests.
old-location: print\ibidirequestcontainer.htm
old-project: print
ms.assetid: 21dfcbe8-2fc1-4495-af54-5d4c83b8bb79
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IBidiRequestContainer, IBidiRequestContainer interface [Print Devices], IBidiRequestContainer interface [Print Devices], described, _win32_IBidiRequestContainer, bidispl/IBidiRequestContainer, gdi.ibidirequestcontainer, print.ibidirequestcontainer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: bidispl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: Windows Server 2003
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: Bidispl.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Bidispl.h
api_name:
-	IBidiRequestContainer
product: Windows
targetos: Windows
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# IBidiRequestContainer interface

The <b>IBidiRequestContainer</b> interface allows an application or other objects to compose and retrieve a list of bidi requests.

## Methods

<p>The <b>IBidiRequestContainer</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IBidiRequestContainer::AddRequest](nf-bidispl-ibidirequestcontainer-addrequest.md) | The AddRequest method adds a request to the request list. |
| [IBidiRequestContainer::GetEnumObject](nf-bidispl-ibidirequestcontainer-getenumobject.md) | The GetEnumObject method enumerates the bidi requests in a list. |
| [IBidiRequestContainer::GetRequestCount](nf-bidispl-ibidirequestcontainer-getrequestcount.md) | The GetRequestCount method gets the number of requests in the request list. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Windows XP |
| **Target Platform** | Windows |
| **Header** | bidispl.h |

## See Also

<a href="https://msdn.microsoft.com/42b5e6cf-b434-4734-86f3-b3b9d15ea468">Print Spooler Components</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545163">Bidirectional Communication Interfaces</a>



<a href="https://msdn.microsoft.com/b15b1aff-623e-4159-ab0f-ce386a1377eb">Bidirectional Communication Schema</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IBidiRequestContainer interface%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>