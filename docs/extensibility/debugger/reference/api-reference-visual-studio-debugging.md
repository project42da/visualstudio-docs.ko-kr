---
title: "API 참조 (Visual Studio 디버깅) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], API reference
ms.assetid: e4e429da-3667-41f7-9158-a8207d13e91a
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9f6e3110ca4988fcc12e547f3bcd82c1026f3aeb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="api-reference-visual-studio-debugging"></a>API 참조 (Visual Studio 디버깅)
API, 구문 및 모든 API 요소에 대 한 사용법을 보여 주는 가이드의 개념 개요와 다양 한 코드 예제 참조 섹션에 포함 되어 있습니다. 모든 참조 범주별으로 나열 됩니다.  
  
 다음 표에서 일반적인 `HRESULT` 메서드에 의해 반환 되는 값입니다.  
  
|name|설명|값|  
|----------|-----------------|-----------|  
|S_OK|명령 실행 성공|0x00000000|  
|E_UNEXPECTED|예기치 않은 오류가 발생 했습니다.|0x8000FFFF|  
|E_NOTIMPL|구현되지 않았습니다.|0x80004001|  
|E_OUTOFMEMORY|작업을 완료 하는 메모리가 부족 합니다.|0x8007000E|  
|E_INVALIDARG|하나 이상의 인수가 잘못 되었습니다.|0x80070057|  
|E_NOINTERFACE|인터페이스입니다.|0x80004002|  
|E_POINTER|잘못 된 포인터입니다.|0x80004003|  
|E_HANDLE|핸들이 잘못 되었습니다.|0x80070006|  
|E_ABORT|작업이 중단 되었습니다.|0x80004004|  
|E_FAIL|예기치 않은 오류가 발생 했습니다.|0x80004005|  
|E_ACCESSDENIED|일반 액세스 거부 오류가 발생 합니다.|0x80070005|  
  
> [!NOTE]
>  경우는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 반환 메서드를 디버깅 `S_OK`, 매개 변수 포인터는 유효한 모두, 즉, 유효성 검사가 수행 되지 수행 하는에 out 매개 변수가 포인터 가정 때 `S_OK` 반환 됩니다.  
  
> [!NOTE]
>  잘못 된 또는 `NULL` [out] 매개 변수가 IDE에서 충돌이 발생할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스](../../../extensibility/debugger/reference/interfaces-visual-studio-debugging.md)   
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [디버깅을 위한 도우미 SDK](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Visual Studio 디버거 확장성](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)