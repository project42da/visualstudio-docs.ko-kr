---
title: "방법: ClickOnce 응용 프로그램에 대한 파일 연결 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 파일 연결"
  - "파일 연결, ClickOnce 응용 프로그램"
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 응용 프로그램에 대한 파일 연결 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 하나 이상의 파일 확장명과 연결하여 사용자가 해당 형식의 파일을 열 때 응용 프로그램이 자동으로 시작되도록 할 수 있습니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 파일 확장명 지원을 추가하는 방법은 매우 간단합니다.  
  
### ClickOnce 응용 프로그램에 대한 파일 연결을 만들려면  
  
1.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 만들거나 기존 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 사용합니다.  
  
2.  메모장과 같은 텍스트 편집기 또는 XML 편집기에서 응용 프로그램 매니페스트를 엽니다.  
  
3.  `assembly` 요소를 찾습니다.  자세한 내용은 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)를 참조하십시오.  
  
4.  `fileAssociation` 요소를 `assembly` 요소의 자식으로 추가합니다.  `fileAssociation` 요소에는 다음과 같은 네 가지 특성이 있습니다.  
  
    -   `extension`: 응용 프로그램과 연결할 파일 확장명입니다.  
  
    -   `description`: Windows 셸에 나타나는 파일 형식에 대한 설명입니다.  
  
    -   `progid`: 레지스트리에서 표시하기 위해 파일 형식을 고유하게 식별하는 문자열입니다.  
  
    -   `defaultIcon`: 이 파일 형식에 사용할 아이콘입니다.  이 아이콘을 응용 프로그램 매니페스트에 파일 리소스로 추가해야 합니다.  자세한 내용은 [방법: ClickOnce 응용 프로그램에 데이터 파일 포함](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)을 참조하십시오.  
  
     `file` 및 `fileAssociation` 요소의 예제를 보려면 [\<fileAssociation\> 요소](../deployment/fileassociation-element-clickonce-application.md)를 참조하십시오.  
  
5.  둘 이상의 파일 형식을 응용 프로그램과 연결하려면 `fileAssociation` 요소를 추가합니다.  이때 각 파일 형식에 대해 `progid` 특성이 달라야 합니다.  
  
6.  응용 프로그램 매니페스트 작업이 끝나면 매니페스트에 다시 서명합니다.  이 작업은 명령줄에서 Mage.exe를 사용하여 수행할 수 있습니다.  
  
     `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
     자세한 내용은 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)를 참조하십시오.  
  
## 참고 항목  
 [\<fileAssociation\> 요소](../deployment/fileassociation-element-clickonce-application.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)