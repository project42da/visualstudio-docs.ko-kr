---
title: "보안 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "ClickOnce 개발[Visual Studio에서 Office 개발], 보안"
  - "응용 프로그램 배포[Visual Studio에서 Office 개발], 보안"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 보안"
  - "Visual Studio에서 Office 개발, 보안"
ms.assetid: c5ba86b1-e87f-4508-8c5a-1295681a9590
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# 보안 배포
  Office 솔루션을 만들면 프로젝트의 코드가 실행될 수 있도록 개발 컴퓨터가 자동으로 업데이트됩니다.  그러나 솔루션을 배포할 때는 인증서로 솔루션을 서명하거나 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] 신뢰 프롬프트 키를 사용하여 신뢰 여부를 결정하는 데 기반이 되는 증명 정보를 제공해야 합니다.  자세한 내용은 [Office 솔루션에 신뢰 부여](../vsto/granting-trust-to-office-solutions.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 문서 수준 사용자 지정의 경우 문서를 네트워크 위치에 배포하려면 Office 응용 프로그램의 보안 센터에서 신뢰할 수 있는 위치 목록에 해당 문서의 위치도 추가해야 합니다.  최종 사용자의 컴퓨터에서 문서 사용 권한을 설정하는 방법에 대한 자세한 내용은 [문서에 신뢰 부여](../vsto/granting-trust-to-documents.md)를 참조하십시오.  
  
## Office 솔루션에서 코드가 실행되지 않도록 지정  
 관리자는 레지스트리를 사용하여 컴퓨터에서 모든 Office 솔루션이 실행되지 않게 할 수 있습니다.  관리 코드 확장이 있는 Office 솔루션 열릴 때, Visual Studio 도구 Office 런타임 검사에 대 한 항목이 있는지 여부를 이름으로 `Disabled` 컴퓨터에서 다음 레지스트리 키 중 하나에서 존재 합니다.  
  
-   `HKEY_CURRENT_USER\Software\Microsoft\VSTO`  
  
-   `HKEY_LOCAL_MACHINE\Software\Microsoft\VSTO`  
  
 Office 솔루션에서 코드가 실행되지 않도록 하려면 이러한 레지스트리 키 중 하나 또는 둘 다에 `Disabled` 항목을 만들어서 `Disabled`에 대해 다음 데이터 형식 및 값 중 하나를 지정합니다.  
  
-   0\(영\) 이외의 문자열로 설정된 REG\_SZ 또는 REG\_EXPAND\_SZ  
  
-   0\(영\) 이외의 값으로 설정된 REG\_DWORD  
  
 Office 솔루션에서 코드가 실행되도록 설정하려면 `Disabled` 항목을 둘 다 0으로 설정하거나 레지스트리 항목을 삭제합니다.  
  
## 참고 항목  
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)   
 [Office 솔루션을 실행 또는 호스팅하도록 컴퓨터 준비](http://msdn.microsoft.com/ko-kr/be1b173f-7261-4d74-aa4e-94ccd43db8d8)   
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
  
  