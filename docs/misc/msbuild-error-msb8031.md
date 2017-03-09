---
title: "MSBuild 오류 MSB8031 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSB8031"
ms.assetid: ebfaca51-fd91-4b04-8194-b4fdededd5fe
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB8031
MSB8031  
  
 MFC 프로젝트에서 MBCS 인코딩을 사용하려면 추가 라이브러리를 다운로드하고 설치해야 합니다.  
  
 MBCS 버전의 MFC DLL은 Visual Studio에 포함되지 않지만 Visual Studio 고객일 경우 다운로드 할 수 있는 MFC MBCS 추가 기능에서 사용할 수 있습니다.  추가 기능을 설치하지 않고 MBCS 문자 집합을 사용하는 MFC 프로젝트를 빌드하는 경우 링커는 Dll을 찾지 못하고 빌드는 생성되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  MSDN 다운로드 센터에서 [MBCS MFC DLL 추가 기능을 다운로드하거나](http://go.microsoft.com/fwlink/?LinkId=299009) 또는 다운로드가 실제로 도움이 될 경우, 프로젝트를 UNICODE 문자 집합으로 변환시킵니다.  
  
## 참고 항목  
 [MFC MBCS DLL 추가 기능](/visual-cpp/mfc/mfc-mbcs-dll-add-on)