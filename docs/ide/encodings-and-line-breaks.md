---
title: "인코딩 및 줄 바꿈 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.Encoding"
helpviewer_keywords: 
  - "편집기, 줄 바꿈"
  - "인코딩"
  - "줄 바꿈 문자"
  - "줄 바꿈"
  - "Visual Studio, 인코딩"
  - "Visual Studio, 줄 바꿈 문자"
ms.assetid: 8f9b3ffc-7b8d-44f4-87cb-dc29105be12d
caps.latest.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 8
---
# 인코딩 및 줄 바꿈
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 사용할 수의  **파일\/고급 저장 옵션** 유형의 줄 바꿈 문자 수를 결정 하는 설정을 선택 합니다.  동일한 설정을 사용 하 여 파일의 인코딩을 변경할 수 있습니다.  
  
> [!NOTE]
>  특정 유형의 개발 설정 설정한 경우 \(Visual Basic F\# 웹 개발\) 나타나지 않을 수 있습니다  **저장 고급 옵션** 메뉴에서.  설정을 변경 \(예를 들어 일반\)를 열고  **도구 가져오기 \/ 내보내기 설정 및**.  자세한 내용은  [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)참조하십시오.  
  
 Visual Studio 다음 문자는 행 분리 해석 됩니다.  
  
-   CRLF: 캐리지 리턴 \+ 줄 바꿈, 유니코드 문자 000D \+ 000A  
  
-   LF: 줄 바꿈, 유니코드 문자 000A  
  
-   NEL: 다음 줄, 유니코드 문자 0085  
  
-   LS: 줄 구분선, 유니코드 문자 2028  
  
-   PS: 단락 구분선, 유니코드 문자 2029  
  
 다른 응용 프로그램에서 복사 된 텍스트를 원래 인코딩 및 줄 바꿈 문자를 유지 합니다.  예를 들어, 메모장에서 텍스트를 복사 하 고 Visual Studio 텍스트 파일에 붙여 넣을 때 텍스트 메모장에서 있던 동일한 설정을 가집니다.  
  
 줄 바꿈 문자를 가진 파일을 열 때 일관성 없는 줄 바꿈 문자 정규화 해야 하는지 하 고 줄 바꿈 선택 유형을 묻는 대화 상자가 표시 될 수 있습니다.