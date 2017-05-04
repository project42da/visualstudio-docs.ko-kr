---
title: "Office 솔루션 공동 개발 | Microsoft Docs"
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
  - "공동 개발[Visual Studio에서 Office 개발]"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 공동 개발"
  - "Visual Studio에서 Office 개발, 공동 작업"
  - "소스 제어[Visual Studio에서 Office 개발]"
ms.assetid: c493354b-17d3-4e50-85f0-968b104bc978
caps.latest.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# Office 솔루션 공동 개발
  여러 개발자들은 다른 Visual Studio 프로젝트에서 공동 작업하는 것과 동일한 방식으로 Office 프로젝트에 대한 작업을 수행할 수 있습니다.  Visual Studio에서는 Office가 서로 다른 위치에 설치된 경우에도 각 컴퓨터에서 Microsoft Office 설치의 위치를 정확하게 찾을 수 있습니다.  그러나 유의해야 할 몇 가지 중요한 문제들이 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 디버그 속성은 공유되지 않습니다  
 디버그 속성은 소스 제어를 사용하는 여러 사용자 간에 공유되지 않습니다.  Visual Basic 및 Visual C\# 프로젝트에서는 디버깅 속성을 사용자별 파일\(*ProjectName*.vbproj.user 또는 *ProjectName*.csproj.user\)에 저장하며 이 파일은 소스 제어 대상이 아닙니다.  여러 사용자가 디버깅하는 경우 각각의 사용자는 직접 디버그 속성을 입력해야 합니다.  
  
 프로젝트가 소스 제어가 아닌 네트워크 공유 위치에 있는 경우에는 여러 공동 개발자가 솔루션을 열고 어셈블리를 테스트할 수 있도록 하기 위해 몇 가지 단계를 추가로 수행해야 합니다.  
  
## 소스 제어를 위해 모든 파일을 체크 아웃해야 합니다  
 프로젝트에 대해 소스 제어를 사용할 경우 코드 파일을 변경할 때마다 **솔루션 탐색기**의 코드 파일\(예: ThisDocument, ThisWorkbook 또는 ThisAddIn 코드 파일\)에 있는 모든 파일은 기본적으로 숨겨져 있더라도 체크 아웃해야 합니다.  최상위 수준 코드 파일만 체크 아웃하면 변경 내용이 손실될 수 있습니다.  
  
 변경한 후에는 모든 파일을 다시 체크 인하십시오.  프로젝트의 숨겨진 코드 파일에 대한 자세한 내용은 [Visual Studio 환경의 Office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md)를 참조하십시오.  
  
## 네트워크상의 간단한 공동 작업 보안  
 \\\\*Servername*\\*Sharename*과 같이 네트워크 위치에 있는 모든 문서 수준 솔루션의 경우 작업 중인 Microsoft Office 응용 프로그램의 신뢰할 수 있는 폴더 목록에 정규화된 위치를 추가해야 합니다.  기본 폴더의 하위 디렉터리를 포함하는 옵션을 선택하거나 신뢰할 수 있는 폴더 목록에 디버그 및 빌드 폴더만 추가합니다.  이 작업을 수행하는 방법에 대한 자세한 내용은 [문서에 신뢰 부여](../vsto/granting-trust-to-documents.md)를 참조하십시오.  
  
 빌드할 때 자동으로 생성되는 임시 인증서는 암호로 보호되지 않습니다.  이 인증서에는 개발자의 로그인 이름 및 기타 개인 정보가 들어 있습니다.  임시 인증서로 서명된 사용자 지정을 개발할 경우 다른 사용자가 이 정보에 액세스하지 못할 수 있습니다.  
  
## 참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 솔루션 빌드](../vsto/building-office-solutions.md)  
  
  