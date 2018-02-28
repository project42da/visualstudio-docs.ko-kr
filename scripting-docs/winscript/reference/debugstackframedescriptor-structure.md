---
title: "DebugStackFrameDescriptor 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- DebugStackFrameDescriptor
apilocation:
- scrobj.dll
helpviewer_keywords:
- DebugStackFrameDescriptor structure
ms.assetid: a86bcb99-41e4-4a26-a1dd-e1458fb73139
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 346f039ca96f2160d7ac28686e542b3d88a91dfb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugstackframedescriptor-structure"></a>DebugStackFrameDescriptor 구조체
스택 프레임을 열거하고 출력은 동일한 스레드에서 여러 열거자에 병합합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagDebugStackFrameDescriptor {  
   IDebugStackFrame *pdsf;  
   DWORD_PTR        dwMin;  
   DWORD_PTR        dwLim;  
   BOOL             fFinal;  
   IUnknown         *punkFinal;  
} DebugStackFrameDescriptor;  
```  
  
## <a name="members"></a>멤버  
 `pdsf`  
 스택 프레임 개체입니다.  
  
 `dwMin`  
 이 스택 프레임과 연결 된 물리적 주소 하위 범위를 컴퓨터 종속 표현입니다.  
  
 `dwLim`  
 이 스택 프레임과 연결 된 실제 주소 범위의 상한의 컴퓨터 종속 표현입니다.  
  
 `fFinal`  
 프레임 처리 되 고 있음을 나타내는 플래그입니다.  
  
 `punkFinal`  
 이 매개 변수가 없으면 `NULL`병합 현재 열거자를 중지 하 고 새로 시작 해야 합니다. 개체에는 새 열거를 시작 하는 방법을 나타냅니다.  
  
## <a name="remarks"></a>설명  
 이 구조를 사용 하 여 여러 스크립트 엔진에서 스택 프레임을 정렬 하려면 프로세스 디버그 관리자. 일반적으로 스택 아래로 증가합니다. 따라서 스택 자라 아키텍처에는 주소가 있어야 2로 보완 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)