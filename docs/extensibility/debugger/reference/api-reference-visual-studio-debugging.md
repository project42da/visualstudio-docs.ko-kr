---
title: "API 참조 (Visual Studio 디버깅) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], API 참조"
ms.assetid: e4e429da-3667-41f7-9158-a8207d13e91a
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# API 참조 (Visual Studio 디버깅)
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

참조 섹션 API 구문 및 모든 API 요소에 대 한 사용을 보여 주는 지침을 개념적으로 간략하게 하 고 제공 하는 코드 예제가 포함 되어 있습니다.  모든 참조는 범주에 따라 사전순으로 표시 됩니다.  
  
 다음 표에서 공통 `HRESULT` 메서드에 의해 반환 되는 값입니다.  
  
|Name|설명|값|  
|----------|--------|-------|  
|S\_OK|성공|0x00000000|  
|E\_UNEXPECTED|예기치 않은 오류가 발생 했습니다.|0x8000ffff는|  
|E\_NOTIMPL|구현되지 않았습니다.|0x80004001|  
|E\_OUTOFMEMORY|작업을 완료할 수 있는 메모리가 부족 합니다.|0x8007000E|  
|E\_INVALIDARG|하나 이상의 인수가 잘못된 경우|0x80070057|  
|E\_NOINTERFACE|지원 되지 않는 인터페이스입니다.|0x80004002|  
|E\_POINTER|잘못 된 포인터입니다.|0x80004003|  
|E\_HANDLE|핸들이 잘못 되었습니다.|0x80070006|  
|E\_ABORT|작업이 중단 되었습니다.|0x80004004|  
|E\_FAIL|예기치 않은 오류가 발생 했습니다.|0x80004005|  
|이 실패|일반 액세스 거부 오류입니다.|0x80070005|  
  
> [!NOTE]
>  경우는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버깅 방법을 반환 `S_OK`, 간주 됩니다이 부분은 매개 변수에 대 한 포인터를 유효한 지, 즉, 유효성 검사에 매개 변수에 대 한 포인터를 실시 됩니다 때 `S_OK` 반환 됩니다.  
  
> [!NOTE]
>  잘못 된 또는 `NULL` 매개 변수가 \[out\] IDE가 충돌 될 수 있습니다.  
  
## 참고 항목  
 [인터페이스](../../../extensibility/debugger/reference/interfaces-visual-studio-debugging.md)   
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [디버깅을 위한 SDK 도우미](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Visual Studio 디버거 확장성](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)