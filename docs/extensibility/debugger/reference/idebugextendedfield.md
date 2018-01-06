---
title: IDebugExtendedField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugExtendedField interface
ms.assetid: b491499c-af57-47da-87d6-34b7398f6591
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bc656814b355636e4bc4a9a362bd36b84c7d0786
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugextendedfield"></a>IDebugExtendedField
관리 코드 제네릭을 지 원하는 데 사용할 수 있는 필드의 형식을 확장 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugExtendedField : IDebugField  
```  
  
## <a name="methods"></a>메서드  
 메서드 외에도 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)|지정 된 확장된 필드 종류를 검색합니다.|  
|[IsClosedType](../../../extensibility/debugger/reference/idebugextendedfield-isclosedtype.md)|필드 폐쇄형된 형식을 나타내는지 여부를 확인 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll