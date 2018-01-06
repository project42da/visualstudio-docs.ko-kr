---
title: "로컬 값을 변경 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, changing values programmatically
ms.assetid: 8407d3df-d38a-4328-82d1-98084bef43ec
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 03e6acb4ee9756d0bbb14a6e3667375d32cafba9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="changing-the-value-of-a-local"></a>로컬 값 변경
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 값 필드에 새 값을 입력 한 경우는 **지역** 창에서 디버그 패키지가 문자열을 전달 (EE) 식 계산기에 입력 한 대로 합니다. EE 단순 값 또는 식을 포함할 수 있으며 결과 값의 연결 된 로컬에 저장 된이 문자열을 평가 합니다.  
  
 다음은 로컬 값을 변경 하는 프로세스의 개요입니다.  
  
1.  Visual Studio를 호출 하는 사용자가 새 값을 입력 한 후 [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) 에 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 로컬와 연결 된 개체입니다.  
  
2.  `IDebugProperty2::SetValueAsString`다음 작업을 수행합니다.  
  
    1.  값을 생성 하는 문자열을 평가 합니다.  
  
    2.  연결 된 바인딩합니다 [IDebugField](../../extensibility/debugger/reference/idebugfield.md) 개체를 가져옵니다는 [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) 개체입니다.  
  
    3.  일련의 바이트를 변환합니다.  
  
    4.  호출 [SetValue](../../extensibility/debugger/reference/idebugobject-setvalue.md) 디버깅 중인 프로그램에서 액세스할 수 있도록 메모리에 값의 바이트를 넣을 수 있습니다.  
  
3.  Visual Studio를 새로 고칩니다는 **지역** 표시 (참조 [표시 지역](../../extensibility/debugger/displaying-locals.md) 세부 정보에 대 한).  
  
 변수 값을 변경 하려면이 절차는 또한는 **조사식** 창을 제외 하는 `IDebugProperty2` 대신 사용 되는 지역 변수의 값과 관련 된 개체는 `IDebugProperty2` 로컬와 연결 된 개체 자체입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [값 변경 샘플 구현](../../extensibility/debugger/sample-implementation-of-changing-values.md)  
 MyCEE 샘플링을 사용 하 여 값을 변경 하는 과정을 단계별로 실행 되도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [로컬 항목 표시](../../extensibility/debugger/displaying-locals.md)