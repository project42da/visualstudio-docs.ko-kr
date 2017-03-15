---
title: "방법: ClickOnce 배포에 대한 자세한 로그 파일 지정 | Microsoft Docs"
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
  - "ClickOnce 배포, 기록"
  - "로그, ClickOnce 배포"
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ClickOnce 배포에 대한 자세한 로그 파일 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 모든 배포의 작업 로그 파일을 유지 관리합니다.  이러한 로그에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포의 설치, 초기화, 업데이트 및 제거와 관련된 정보가 기록됩니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 이러한 로그 파일에 쓰는 정보를 늘리려면 레지스트리 편집기\(**regedit.exe**\)를 사용하여 자세한 정도를 지정합니다.  
  
> [!CAUTION]
>  레지스트리 편집기를 잘못 사용하면 심각한 문제가 발생하여 운영 체제를 다시 설치해야 할 수도 있습니다.  레지스트리 편집기를 사용할 때는 주의하십시오.  
  
 다음 절차에서는 현재 사용자에 대한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 로그 파일의 자세한 정도를 지정하는 방법을 보여 줍니다.  자세한 정도를 낮추려면 이 레지스트리 값을 제거합니다.  
  
### 자세한 로그 파일을 지정하려면  
  
1.  **Regedit.exe**를 엽니다.  
  
2.  `HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment` 노드로 이동합니다.  
  
3.  필요한 경우 `LogVerbosityLevel`이라는 새 문자열 값을 만듭니다.  
  
4.  `LogVerbosityLevel` 값을 `1`로 설정합니다.  
  
## 참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)