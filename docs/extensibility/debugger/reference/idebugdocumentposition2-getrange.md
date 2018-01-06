---
title: IDebugDocumentPosition2::GetRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentPosition2::GetRange
helpviewer_keywords: IDebugDocumentPosition2::GetRange
ms.assetid: 91a06ee7-253a-4215-be22-04bf57305aa8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0b570591777eb00f200af7541d781fe2778e63ef
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentposition2getrange"></a>IDebugDocumentPosition2::GetRange
이 문서에 대 한 범위를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRange(   
   TEXT_POSITION* pBegPosition,  
   TEXT_POSITION* pEndPosition  
);  
```  
  
```csharp  
int GetRange(   
   TEXT_POSITION[] pBegPosition,  
   TEXT_POSITION[] pEndPosition  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pBegPosition`  
 [out에서] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조 시작 위치를 사용 하 여 입력 됩니다. 이 정보가 필요 하지 않은 경우이 인수를 null 값으로 설정 합니다.  
  
 `pEndPosition`  
 [out에서] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 구조 끝 위치를 사용 하 여 입력 됩니다. 이 정보가 필요 하지 않은 경우이 인수를 null 값으로 설정 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 위치 중단점에 대 한 문서 위치에 지정 된 범위는 실제로 코드를 적용 하는 문을 계속 검색 하려면 디버그 엔진 (DE)에 의해 사용 됩니다. 예를 들어, 다음 코드를 고려하세요.  
  
```  
Line 5: // comment  
Line 6: x = 1;  
```  
  
 줄 5 디버깅 중인 프로그램 코드가 영향을 줍니다. 다섯 번째 줄에 중단점을 설정 하는 디버거의 원하는 일정량 코드를 적용 하는 첫 번째 줄 앞으로 검색 DE 디버거 중단점 수 올바르게 배치 되는 추가 후보 줄을 포함 하는 범위를 지정 합니다. DE 중단점을 수락할 수 있는 줄을 찾을 때까지 해당 줄을 통해 앞으로 검색 한 다음 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)