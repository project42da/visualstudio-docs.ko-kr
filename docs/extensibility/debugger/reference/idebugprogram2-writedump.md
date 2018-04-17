---
title: IDebugProgram2::WriteDump | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0b17d75ace19ac53cbcd229d7c15de573c1ecb8b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
덤프 파일에 씁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WriteDump(   
   DUMPTYPE  DumpType,  
   LPCOLESTR pszDumpUrl  
);  
```  
  
```csharp  
int WriteDump(   
   enum_DUMPTYPE  DumpType,  
   string         pszDumpUrl  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `DumpType`  
 [in] 값은 [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md) 예를 들어, 즉 덤프의 유형을 지정 하는 열거형 또는 long입니다.  
  
 `pszDumpUrl`  
 [in] 덤프를 작성 하는 URL입니다. 일반적으로 이것이의 형태로 `file://c:\path\filename.ext`, 하지만 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 현재 스택 프레임, 스택 자체, 프로그램 및 프로그램 담당 하는 메모리 가능에서 실행 중인 스레드 목록 프로그램 덤프를 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)