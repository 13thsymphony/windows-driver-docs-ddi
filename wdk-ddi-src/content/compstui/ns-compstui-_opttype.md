---
UID : NS:compstui._OPTTYPE
title : _OPTTYPE
author : windows-driver-content
description : The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a property sheet option, if the option is specified by an OPTITEM structure.
old-location : print\opttype.htm
old-project : print
ms.assetid : 041dd438-e837-4912-bda7-de654204198b
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : _OPTTYPE, *POPTTYPE, OPTTYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : compstui.h
req.include-header : Compstui.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : OPTTYPE
req.alt-loc : compstui.h
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
req.typenames : "*POPTTYPE, OPTTYPE"
---

# _OPTTYPE structure
The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a <a href="https://msdn.microsoft.com/572330d6-1a1b-46fd-bfb4-be2b0990bca4">property sheet option</a>, if the option is specified by an <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure.

## Syntax
````
typedef struct _OPTTYPE {
  WORD      cbSize;
  BYTE      Type;
  BYTE      Flags;
  WORD      Count;
  WORD      BegCtrlID;
  POPTPARAM pOptParam;
  WORD      Style;
  WORD      wReserved[3];
  ULONG_PTR dwReserved[3];
} OPTTYPE, *POPTTYPE;
````

## Members

        
            `BegCtrlID`

            If <b>pDlgPage</b> in <a href="..\compstui\ns-compstui-_compropsheetui.md">COMPROPSHEETUI</a> identifies a CPSUI-supplied page, or if <b>DlgTemplateID</b> in <a href="..\compstui\ns-compstui-_dlgpage.md">DLGPAGE</a> identifies a CPSUI-supplied template, <b>BegCtrlID</b> is not used.

Otherwise, <b>BegCtrlID</b> must contain the first of a sequentially numbered set of Windows control identifiers. Control identifier usage is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.
        
            `cbSize`

            Size, in bytes, of the OPTTYPE structure.
        
            `Count`

            Specifies the number of <a href="..\compstui\ns-compstui-_optparam.md">OPTPARAM</a> structures to which <b>pOptParam</b> points. This member's value is dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.
        
            `dwReserved`

            Reserved, must be initialized to zero.
        
            `Flags`

            Optional bit flags that modify the option's characteristics. The following flags can be set in any combination.
        
            `pOptParam`

            Pointer to an array of <a href="..\compstui\ns-compstui-_optparam.md">OPTPARAM</a> structures describing the parameter values that a user can select for the option.
        
            `Style`

            Specifies flags that can be used to modify the option's display characteristics. The flags that can be specified are dependent on the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.
        
            `Type`

            Specifies the <a href="https://msdn.microsoft.com/3b3c002c-a201-4f81-b208-30864343409b">CPSUI option type</a>.
        
            `wReserved`

            Reserved, must be initialized to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | compstui.h (include Compstui.h) |