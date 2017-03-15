---
title: "ClickOnce에서 응용 프로그램 업데이트가 수행되는 방식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "ClickOnce 배포, 업데이트"
  - "응용 프로그램 배포[ClickOnce], 응용 프로그램 업데이트"
  - "업데이트, ClickOnce"
ms.assetid: d54313c2-cf0c-420d-b151-99953a95f0bb
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 9
---
# ClickOnce에서 응용 프로그램 업데이트가 수행되는 방식
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ClickOnce에서는 응용 프로그램의 배포 매니페스트에 지정된 파일 버전 정보를 사용하여 응용 프로그램의 파일을 업데이트할지 여부를 결정합니다.  업데이트가 시작된 후에는 *파일 패치*라는 기술을 사용하여 응용 프로그램 파일의 중복 다운로드를 방지합니다.  
  
## 파일 패치  
 응용 프로그램을 업데이트할 때 ClickOnce에서는 파일이 변경되지 않은 한 새 버전의 응용 프로그램 파일을 모두 다운로드하지 않습니다.  대신 현재 응용 프로그램의 응용 프로그램 매니페스트에 지정된 파일의 해시 서명과 새 버전의 매니페스트에 있는 서명을 비교하여  파일 서명이 다를 때만 새 버전을 다운로드합니다.  서명이 일치하면 파일 버전이 변경되지 않은 것입니다.  이 경우 ClickOnce에서는 기존 파일을 복사하여 새 버전의 응용 프로그램에서 사용합니다.  이 방법을 사용하면 파일이 한두 개만 변경된 경우에도 응용 프로그램 전체를 다시 다운로드할 필요가 없습니다.  
  
 파일 패치 기능은 요청 시 <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> 및 <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroupAsync%2A> 메서드를 사용하여 다운로드되는 어셈블리에도 사용할 수 있습니다.  
  
 Visual Studio를 사용하여 응용 프로그램을 컴파일하면 전체 프로젝트를 다시 빌드할 때마다 모든 파일에 대해 새 해시 서명이 생성됩니다.  이 경우 몇 개의 어셈블리만 변경되었더라도 클라이언트에 모든 어셈블리가 다운로드됩니다.  
  
 데이터로 표시되어 데이터 디렉터리에 저장된 파일에 대해서는 파일 패치가 실행되지 않습니다.  이러한 파일은 파일의 해시 서명에 관계없이 항상 다운로드됩니다.  데이터 디렉터리에 대한 자세한 내용은 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)를 참조하십시오.  
  
## 참고 항목  
 [ClickOnce 업데이트 전략 선택](../deployment/choosing-a-clickonce-update-strategy.md)   
 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)