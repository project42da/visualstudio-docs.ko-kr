---
title: "방법: ClickOnce 배포에 대 한 자세한 로그 파일을 지정 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- logs, ClickOnce deployment
- ClickOnce deployment, logging
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 6cac7764a941e88dd3901a3280e78717955e86b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>방법: ClickOnce 배포에 대한 자세한 로그 파일 지정
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]모든 배포에 대 한 활동 로그 파일을 유지 관리합니다. 이러한 로그를 설치, 초기화, 업데이트 및 제거와 관련 된 정보가 문서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 합니다. 세부 정보를 높이기 위해 하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 레지스트리 편집기를 사용 하 여 이러한 로그 파일에 대 한 쓰기 (**regedit.exe**) 자세한 정도 수준을 지정 합니다.  
  
> [!CAUTION]
>  레지스트리 편집기를 잘못 사용 하면 운영 체제를 다시 설치 해야 하는 심각한 문제가 발생할 수 있습니다. 레지스트리 편집기를 사용할 때는 주의하세요.  
  
 다음 절차에 대 한 자세한 정도 지정 하는 방법에 설명 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 로그 파일에서 현재 사용자입니다. 세부 정보 표시 수준의 줄이기 위해이 레지스트리 값을 제거 합니다.  
  
### <a name="to-specify-verbose-log-files"></a>자세한 로그 파일을 지정 하려면  
  
1.  열기 **Regedit.exe**합니다.  
  
2.  노드로 이동 `HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`합니다.  
  
3.  필요한 경우 라는 새 문자열 값을 만들고 `LogVerbosityLevel`합니다.  
  
4.  설정의 `LogVerbosityLevel` 값을 `1`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)