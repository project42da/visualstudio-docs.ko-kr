---
title: 'Idiaframedata:: Execute | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8ad08fd9800fdc197d4218fa55c83487e132f25d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
스택 해제를 수행 하 고 스택 워크 프레임 인터페이스에서 결과 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT execute (   
   IDiaStackWalkFrame* frame  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `frame`  
 [in] [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) 프레임 레지스터의 상태를 유지 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 다음 표에서이 메서드에 대 한 가능한 반환 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|E_DIA_INPROLOG|프롤로그 코드에서 스택 프레임을 실행할 수 없습니다.|  
|E_DIA_SYNTAX|프레임 프로그램에서 발생 한 오류를 구문 분석 합니다.|  
|E_DIA_FRAME_ACCESS|메모리 액세스 레지스터 수 없습니다.|  
|E_DIA_VALUE|계산 값 (예를 들어 0으로 나누기)에 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버깅 중 스택 해제에 호출 됩니다. [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md) 개체는 레지스터에 업데이트를 수신 하 고 사용 되는 메서드를 제공 하는 클라이언트 응용 프로그램에 의해 구현 됩니다는 `execute` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)