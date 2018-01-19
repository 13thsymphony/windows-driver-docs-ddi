---
UID : NE:ksmedia.KS_DVDCOPYSTATE
title : KS_DVDCOPYSTATE
author : windows-driver-content
description : The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.
old-location : stream\ks_dvdcopystate.htm
old-project : stream
ms.assetid : 4072eaf1-d4cc-4255-90c1-177d6d58bb0a
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KS_DVDCOPYSTATE, KS_DVDCOPYSTATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KS_DVDCOPYSTATE
req.alt-loc : ksmedia.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : KS_DVDCOPYSTATE
---

# KS_DVDCOPYSTATE Enumeration
The KS_DVDCOPYSTATE enumeration describes the progress of the DVD copyright protection initialization, authentication and key negotiation sequence.

## Syntax
````
typedef enum  { 
  KS_DVDCOPYSTATE_INITIALIZE                   = 0,
  KS_DVDCOPYSTATE_INITIALIZE_TITLE             = 1,
  KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED  = 2,
  KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED      = 3,
  KS_DVDCOPYSTATE_DONE                         = 4
} KS_DVDCOPYSTATE;
````

## Constants

<table>

<tr>
<td>KS_DVDCOPYSTATE_AUTHENTICATION_NOT_REQUIRED</td>
<td>Indicates that no authentication is required.</td>
</tr>

<tr>
<td>KS_DVDCOPYSTATE_AUTHENTICATION_REQUIRED</td>
<td>Indicates that authentication is required.</td>
</tr>

<tr>
<td>KS_DVDCOPYSTATE_DONE</td>
<td>Indicates that the copyright protection sequence is complete.</td>
</tr>

<tr>
<td>KS_DVDCOPYSTATE_INITIALIZE</td>
<td>Indicates that the full copyright protection sequence is starting.</td>
</tr>

<tr>
<td>KS_DVDCOPYSTATE_INITIALIZE_TITLE</td>
<td>Indicates that a title key copyright protection sequence is starting.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565147">KSPROPERTY_DVDCOPY_SET_COPY_STATE</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-_ks_dvdcopy_set_copy_state.md">KS_DVDCOPY_SET_COPY_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_DVDCOPYSTATE enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>