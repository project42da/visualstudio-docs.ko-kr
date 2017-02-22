---
title: "방법: 공통 출력 디렉터리로 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "빌드[Visual Studio], 공통 디렉터리"
  - "공통 디렉터리"
  - "출력 디렉터리"
ms.assetid: 1fcc2c48-07cb-4c4f-9556-36945e7dfc4e
caps.latest.revision: 7
caps.handback.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: 공통 출력 디렉터리로 빌드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 솔루션의 각 프로젝트를 솔루션 내의 자체 폴더에 빌드합니다.  프로젝트의 빌드 출력 경로를 변경하여 모든 출력이 같은 폴더에 배치되도록 할 수 있습니다.  
  
### 모든 솔루션 출력을 공용 디렉터리에 배치하려면  
  
1.  솔루션에서 한 프로젝트를 클릭합니다.  
  
2.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  
  
3.  프로젝트의 형식에 따라 **컴파일** 탭 또는 **빌드** 탭을 클릭하고 **출력 경로**를 솔루션의 모든 프로젝트에 사용할 폴더로 설정합니다.  
  
4.  솔루션의 모든 프로젝트에 대해 1\-3단계를 반복합니다.  
  
## 참고 항목  
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)   
 [방법: 빌드 출력 디렉터리 변경](../ide/how-to-change-the-build-output-directory.md)