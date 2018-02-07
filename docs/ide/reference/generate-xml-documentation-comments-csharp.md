---
title: "XML 문서 주석 생성 - 코드 생성(C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2025bd2-5984-4486-a61c-0a0933a735ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: b0a0ec1db54f57e14ddd412248f7a396336fe009
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2018
---
# <a name="generate-xml-documentation-comments-in-c"></a>C#에서 XML 문서 주석 생성 #
**대상:** 선택한 요소를 문서화하는 데 기본 XML을 즉시 생성할 수 있습니다. 

**시기:** Sandcastle과 같은 문서 도구에서 나중에 처리할 XML 문서 주석을 만들려고 합니다.

**이유:** 전체 주석 블록을 직접 수동으로 만들 수 있지만, 기본 템플릿과 추가 요소를 생성하면 시간이 절약되고 정확도가 향상됩니다. 

**방법:**

1. 문서화할 요소(예: 메서드) 위에 텍스트 커서를 놓습니다.

   ![문서화할 메서드](media/doc-highlight-cs.png)

1. 그런 다음 **///**(3개의 슬래시)를 입력하면 필요에 따라 기본 템플릿과 모든 추가 요소가 자동으로 만들어집니다.  예를 들어 메서드를 주석으로 처리할 경우 **\<summary\>** 태그뿐 아니라 메서드에 전달되는 모든 매개 변수의 **\<param\>** 태그와 메서드가 반환하는 항목을 문서화하는 **\<returns\>** 태그를 생성합니다.

   ![템플릿](media/doc-preview-cs.png)

1. 주석을 완료하고 필요하다고 생각되는 정보를 추가합니다.

   ![완료된 주석](media/doc-result-cs.png)

## <a name="see-also"></a>참고 항목

[코드 생성](../code-generation-in-visual-studio.md)  
[XML 문서 주석(C# 프로그래밍 가이드)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
