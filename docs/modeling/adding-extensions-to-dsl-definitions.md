---
title: "DSL 정의에 확장을 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07e133be-92ab-4936-a02b-45d2012bd0a6
caps.latest.revision: "6"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 77a631d7f245dfe6d324e2b392349b559447212f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-extensions-to-dsl-definitions"></a>DSL 정의에 확장 추가
DSL 정의 확장을 사용 하면 도메인 특정 언어 (DSL)의 확장 패키지를 만들 수 있습니다. 에 VSIX Visual Studio Integration Extension ()를 포함 하는 DSL 확장과 동일한 방식으로 DSL 사용자의 컴퓨터에 설치할 수 있습니다. 추가 기능 동적으로 활성화 하 고 수 실행 시 사용할 수 없습니다. Dsl 확장을 위해 명시적으로 디자인 될 필요가 없습니다 및 확장 확장된 DSL 변경 하지 않고에 나중에 또는 제 3 자가 디자인할 수 있습니다.  
  
 추가 기능은 다음과 같습니다.  
  
-   모델 및 프레젠테이션 요소에 대 한 속성  
  
-   셰이프와 연결선의 데코레이터  
  
-   클래스, 관계, 셰이프 및 연결선  
  
-   유효성 검사 제약 조건  
  
-   도구 상자 항목 및 탭  
  
 확장 된 DSL의 사용자 만들고 추가 기능을의 인스턴스가 포함 된 모델을 저장할 수 있으며 적절 한 확장을 설치한 다른 사용자가 읽을 수 있습니다. 확장을 설치 하지 않은 사용자가 추가 기능을 사용할 수 없지만 업데이트 하 고 추가 기능을 손실 하지 않고 모델을 저장할 수 있습니다.  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>참고 항목  
 [관련된 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
