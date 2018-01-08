---
title: "공용 언어 런타임 식 계산기 작성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluators, tutorial
- expression evaluation, samples
- debugging [Debugging SDK], expression evaluators tutorial
ms.assetid: bd79d57f-8e0a-4e14-a417-0b1de28fa1b2
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d52a9dbed6cec64426247a0b92bff2b8ec98ec97
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="writing-a-common-language-runtime-expression-evaluator"></a>공용 언어 런타임 식 계산기를 작성합니다.
> [!IMPORTANT]
>  Visual Studio 2015에서 구현 하는 식 계산기의 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 샘플](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식 계산기 (EE) 구문을 처리 하는 디버그 엔진 (DE)의 일부와 디버깅 되는 코드가 생성 되는 프로그래밍 언어의 의미 체계는 합니다. 식 프로그래밍 언어의 컨텍스트 내에서 평가 되어야 합니다. 예를 들어 일부 언어에서 식 "A + B"은 "A의 합계와 B" 다른 언어와 같은 식을 "A 또는 B."를 의미할 수도 있습니다. 따라서 별도 EE 작성 해야 Visual Studio IDE에서 코드를 디버깅할 개체를 생성 하는 각 프로그래밍 언어입니다.  
  
 Visual Studio 디버그 패키지의 일부 측면 프로그래밍 언어의 컨텍스트에서 코드를 해석 해야 합니다. 예를 들어 경우 실행에서 중단에 사용자가 입력 한 모든 식 중단점을 한 **조사식** 창을 평가 하 고 표시 합니다. 사용자가에 식을 입력 하 여 지역 변수 값을 변경할 수는 또한는 **조사식** 창에는 **직접 실행** 창.  
  
## <a name="in-this-section"></a>섹션 내용  
 [공용 언어 런타임 및 식 계산](../../extensibility/debugger/common-language-runtime-and-expression-evaluation.md)  
 Visual Studio IDE에 소유 프로그래밍 언어를 통합 하는 경우는 EE 작성 독점 언어의 컨텍스트 내에서 식을 평가할 수 있는 허용 하는지 Microsoft intermediate language MSIL로 컴파일할 수에 대해 설명 디버그 엔진 작성 하지 않고.  
  
 [식 계산기 아키텍처](../../extensibility/debugger/expression-evaluator-architecture.md)  
 요청한 EE 인터페이스를 구현 하는 공용 언어 런타임 기호 공급자 (SP) 및 바인더 인터페이스를 호출 하는 방법을 설명 합니다.  
  
 [식 계산기 등록](../../extensibility/debugger/registering-an-expression-evaluator.md)  
 EE 등록 해야 자체 공용 언어 런타임 및 Visual Studio 런타임 환경 클래스 팩터리로 인식 합니다.  
  
 [식 계산기 구현](../../extensibility/debugger/implementing-an-expression-evaluator.md)  
 식의 계산 프로세스의 디버그 엔진 (DE), 기호 공급자 (SP), 바인더 개체 및 식 계산기 (EE)를 포함 하는 방법을 설명 합니다.  
  
 [로컬 항목 표시](../../extensibility/debugger/displaying-locals.md)  
 방법, 실행이 일시 중지, 디버그 패키지가 로컬 변수 및 인수 목록을 얻으려면 장치가 호출에 대해 설명 합니다.  
  
 [조사식 창 식 계산](../../extensibility/debugger/evaluating-a-watch-window-expression.md)  
 Visual Studio 디버그 패키지 조사식 목록에 각 식의 현재 값을 결정 하려면 DE를 호출 하는 방법에 대해 설명 합니다.  
  
 [로컬 항목 값 변경](../../extensibility/debugger/changing-the-value-of-a-local.md)  
 로컬 값을 변경에서 지역 창의 각 줄에 이름, 형식 및 지역 변수의 현재 값을 제공 하는 관련된 개체에 설명 합니다.  
  
 [형식 시각화 도우미 및 사용자 지정 뷰어 구현](../../extensibility/debugger/implementing-type-visualizers-and-custom-viewers.md)  
 시각화 도우미 형식 및 사용자 지정 뷰어를 지원 하도록 구성 요소에서 구현 해야 하는 인터페이스에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)