---
title: "MSBuild 오류 MSB3126 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GenerateManifest.FileAssociationsNotInstalled"
helpviewer_keywords: 
  - "MSB3126"
ms.assetid: 0c92cbb6-9100-4433-8113-f2f3a1432243
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3126
**MSB3126: 응용 프로그램이 파일 연결을 사용하고 있지만 설치되지 않은 것으로 표시됩니다.  웹 브라우저에 호스팅된 응용 프로그램과 같이 설치되지 않은 응용 프로그램에 대해서는 파일 연결을 사용할 수 없습니다.**  
  
 이 오류는 응용 프로그램이 파일 연결을 사용하도록 구성되어 있지만 응용 프로그램의 설치 모드가 온라인 전용으로 설정되어 있는 경우에 발생합니다.  온라인 전용 응용 프로그램은 대개 브라우저에서 실행되므로 파일 연결을 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   **설치 모드 및 설정**을 **오프라인으로도 응용 프로그램 사용 가능\(\[시작\] 메뉴에서 시작 가능\)**으로 설정합니다.  자세한 내용은 [방법: ClickOnce 오프라인 또는 온라인 설치 모드 지정](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)을 참조하십시오.  
  
## 참고 항목  
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)