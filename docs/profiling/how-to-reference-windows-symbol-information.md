---
title: "방법: Windows 기호 정보 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "성능 도구, 기호 서버"
  - "서버, 기호 서버"
  - "프로파일링 도구, 기호 서버"
  - "기호 서버"
ms.assetid: b7c67318-6be2-4b1e-a161-077b1f4a7c30
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: Windows 기호 정보 참조
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 프로파일링 도구는 기호 파일\(.pdb\)을 사용하여 프로그램 이진 파일의 함수 이름과 같은 기호 이름을 확인합니다.  이 항목에서 설명하는 단계를 수행하면 로컬 컴퓨터의 Windows 버전에 맞는 .pdb 파일을 자동으로 다운로드하여 업데이트할 수 있습니다.  
  
> [!NOTE]
>  이 설정은 기존 보고서에는 영향을 미치지 않습니다.  기호 서버를 지정한 후 만든 보고서에만 이 기호 정보가 사용됩니다.  
  
 자세한 내용은 [기호 파일\(.pdb\) 및 원본 파일 지정](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)을 참조하십시오.  
  
### Microsoft 기호 서버를 사용하려면  
  
1.  C:\\SymbolCache와 같이 기호 파일 정보를 저장할 폴더를 만듭니다.  
  
2.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
     **옵션** 대화 상자가 표시됩니다.  
  
3.  **디버깅** 트리를 확장한 다음 **기호**를 클릭합니다.  
  
4.  **기호 파일 \(.pdb\) 위치**에서 **Microsoft 기호 서버**를 선택합니다.  
  
5.  **기호 서버에서 이 디렉터리로 기호 캐시**에서 다음과 같이 1단계에서 만든 폴더의 경로를 입력합니다.  
  
     C:\\SymbolCache  
  
     줄임표 단추 \(**...**\)를 누르고 **폴더 찾아보기** 대화상자로 부터 디렉터리를 선택합니다.  
  
## 참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [방법: 기호 정보 직렬화](../profiling/how-to-serialize-symbol-information.md)