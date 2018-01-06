---
title: "XML 문서 주석-코드 생성 (Visual Basic)를 생성 | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2025bd2-5984-4486-a61c-0a0933a735ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f975fa077fe64052b54875b07d029ece71e83372
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="generate-xml-documentation-comments-in-visual-basic"></a>Visual Basic의 XML 문서 주석 생성
**:** 즉시 기본 선택된 된 요소를 문서화 하는 데 필요한 XML을 생성할 수 있습니다. 

**경우:** XML 문서 주석 나중에 처리할 Sandcastle와 같은 설명서 도구 만들려고 한다고 합니다.

**하지만 이유:** 수동으로 만들 수 있습니다 전체 주석 블록을 직접 시간 저장 되 고 기본 템플릿 및 추가 요소를 생성 하 여 정확도 향상 합니다. 

**방법:**

1. 텍스트는 메서드, 예를 들어 문서를 요소 위에 커서를 놓습니다.

   ![문서에 대 한 메서드](media/doc_highlight.png)

1. 그런 다음 입력 **' '** (3 작은따옴표)를 자동으로 만들어집니다 기본 템플릿 및 추가 요소 필요에 따라 합니다.  예를 들어 메서드를 주석 처리 하는 경우 기반인는  **\<요약\>**  태그와 함께  **\<param\>**  되는 모든 매개 변수에 대 한 태그 메서드에 전달 된 및  **\<반환\>**  메서드가 반환 하는 기능을 문서화 하는 태그입니다.

   ![템플릿](media/doc_preview.png)

1. 메모를 완료 하 고 생각 될 추가 정보 필요는 추가 합니다.

   ![완료 된 주석](media/doc_result.png)

## <a name="see-also"></a>참고 항목
[XML (Visual Basic)를 사용 하 여 코드 문서화](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)  
[코드 생성(Visual Basic)](../code-generation-vb.md) 