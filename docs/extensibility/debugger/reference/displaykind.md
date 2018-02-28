---
title: DisplayKind | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DisplayKind enumeration
ms.assetid: 940968c5-6065-4bda-8ee6-c31597db4d71
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 230be9a3c1d7e3bcbddc85bc37226a2a2baef6a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="displaykind"></a>DisplayKind
사용 되는 정보의 종류를 나타내는 유효한 값을 열거는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체 및 사용자에 게 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
typedef DWORD DisplayKind;  
```  
  
```csharp  
public enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 DisplayKind_Value  
 필드의 값입니다.  
  
 DisplayKind_Name  
 필드의 이름입니다.  
  
 DisplayKind_Type  
 필드 유형입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)