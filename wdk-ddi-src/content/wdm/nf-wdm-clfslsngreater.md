---
UID : NF:wdm.ClfsLsnGreater
title : ClfsLsnGreater function
author : windows-driver-content
description : The ClfsLsnGreater routine determines whether one LSN is greater than another LSN. The two LSNs must be from the same stream.
old-location : kernel\clfslsngreater.htm
old-project : kernel
ms.assetid : 77ad073e-5dac-4d89-869e-547e1aec25da
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ClfsLsnGreater routine [Kernel-Mode Driver Architecture], wdm/ClfsLsnGreater, ClfsLsnGreater, Clfs_e258803f-9e95-4601-9b4e-2d775836864b.xml, kernel.clfslsngreater
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Clfs.lib
req.dll : Clfs.sys
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ClfsLsnGreater function
The <b>ClfsLsnGreater</b> routine determines whether one LSN is greater than another LSN. The two LSNs must be from the same stream.

## Syntax

````
BOOLEAN ClfsLsnGreater(
  _In_ const CLFS_LSN *plsn1,
  _In_ const CLFS_LSN *plsn2
);
````

## Parameters

`plsn1`

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that supplies one of the LSNs to be compared.

`plsn2`

A pointer to a <a href="..\wdm\ns-wdm-_cls_lsn.md">CLFS_LSN</a> structure that supplies the other LSN to be compared.


## Return Value

<b>ClfsLsnGreater</b> returns <b>TRUE</b> if <i>plsn1</i> is strictly greater than <i>plsn2</i>; otherwise, it returns <b>FALSE</b>.

## Remarks

CLFS_LSN_NULL (the smallest LSN) and CLFS_LSN_INVALID (larger than any valid LSN) are valid arguments to <b>ClfsLsnGreater</b>.

LSNs from different streams are not comparable. Do not use <a href="..\wdm\nf-wdm-clfslsnequal.md">ClfsLsnEqual</a>, <b>ClfsLsnGreater</b>, and the like to compare LSNs from different streams.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-clfslsnnull.md">ClfsLsnNull</a>

<a href="..\wdm\nf-wdm-clfslsnequal.md">ClfsLsnEqual</a>

<a href="..\wdm\nf-wdm-clfslsnless.md">ClfsLsnLess</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsLsnGreater routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>