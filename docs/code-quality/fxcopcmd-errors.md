---
title: "FxCopCmd 오류 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FxCopCmd errors
ms.assetid: bb614ed0-1b7c-4b56-99ae-da50ef6cfef9
caps.latest.revision: "12"
ms.author: gewarren
author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 48b082f5b00f260d2f8e2519a4551fab23dc1011
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="fxcopcmd-errors"></a>FxCopCmd 오류
FxCopCmd 심각한 되도록 모든 오류를 고려 하지 않습니다. FxCopCmd 부분 분석을 수행할 수 있는 충분 한 정보가 있으면 발생 하는 분석 및 보고서 오류를 수행 합니다. 32 비트 정수가 된 오류 코드에 오류에 해당 하는 숫자 값의 비트 조합 포함 되어 있습니다.  
  
 다음 표에서 FxCopCmd에서 반환 된 오류 코드를 설명 합니다.  
  
|Error|숫자 값|  
|-----------|-------------------|  
|오류 없이|0x0|  
|분석 오류|0 x 1|  
|규칙 예외|0x2|  
|프로젝트 로드 오류|0x4|  
|어셈블리 로드 오류|0x8|  
|규칙 라이브러리 로드 오류|0x10|  
|보고서 가져오기 로드 오류|0x20|  
|오류 출력|0x40|  
|명령줄 스위치 오류|0x80|  
|초기화 오류|0x100|  
|어셈블리 참조 오류|0x200|  
|BuildBreakingMessage|0x400|  
|알 수 없는 오류|0x1000000|  
  
 치명적 오류에 대 한 분석 오류가 반환 됩니다. 분석을 완료할 수를 나타냅니다. 해당 하는 경우 오류 코드는 또한 치명적인 오류의 근본 원인은 포함 합니다. 다음과 같은 오류를 생성합니다.  
  
-   분석이 수행할 수 없습니다 부족 하 여 입력에 의해 발생 합니다.  
  
-   분석에서 FxCopCmd에서 처리 되지 않은 예외가 발생 했습니다.  
  
-   지정한 프로젝트 파일 찾을 수 없거나 또는 손상 되었습니다.  
  
-   출력 옵션 지정 되지 않았거나 파일을 쓸 수 없습니다.  
  
    > [!NOTE]
    >  FxCopCmd "어셈블리에서 참조 한 오류" 코드 반환 0x200 자체은 오류가 아닌 경고 합니다. 이 반환 코드에는 누락 된 간접 참조를 찾을 수 있지만 처리 하기 위한 FxCopCmd 못했음을 나타냅니다. 경고는 분석 결과 일부 손상 되었을 수 가능성이 있다는 것 이며 다른 모든 반환 코드와 결합 된 경우를 오류로 반환 코드 "어셈블리에서 참조 한 오류"를 고려해 보세요.  
  
## <a name="see-also"></a>참고 항목  
 [코드 분석 응용 프로그램 오류](../code-quality/code-analysis-application-errors.md)