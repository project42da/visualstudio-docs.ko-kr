---
title: "방법: Office 솔루션에 서명 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- certificates [Office development in Visual Studio], Office solutions
- security [Office development in Visual Studio], signing Office solutions
- signing manifests [Office development in Visual Studio]
ms.assetid: d3df5ee6-f1b7-47ed-b7ee-8985679ee3af
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 88509ec452525647e4ce36b0c7e5e35574d6243f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sign-office-solutions"></a>방법: Office 솔루션에 서명
  솔루션에 서명할 인증서를 사용 하 여 증명 정보로 솔루션에 신뢰를 부여할 수 있습니다. 동일한 인증서를 사용 하 여 여러 솔루션에 대 한 및 추가 보안 정책 업데이트가 없는 모든 솔루션 신뢰 됩니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 응용 프로그램을 수동으로 편집 하는 경우 매니페스트 생성 및 편집 도구 (mage.exe 및 mageui.exe)를 사용 하 여 배포 매니페스트를 사용할 수는 매니페스트 다시 서명 해야 합니다. 자세한 내용은 [How to: Re-sign Application and Deployment Manifests](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests)을 참조하세요.  
  
## <a name="signing-by-using-a-certificate"></a>인증서를 사용 하 여 서명  
 인증서는 고유 키와 솔루션 게시자의 id를 포함 하는 파일입니다. 수 인증 기관에서 인증서를 구매 하거나 직접 인증서 있으며 서명 인증 기관.  
  
 Visual Studio 디버깅을 사용 하려면 임시 인증서를 사용 하 여 Office 솔루션에 서명 합니다. 하지 증명 정보로 배포 된 솔루션에서 임시 인증서를 사용 해야 합니다.  
  
#### <a name="to-sign-an-office-solution-by-using-a-certificate"></a>인증서를 사용 하 여 Office 솔루션 서명 하려면  
  
1.  에 **프로젝트** 메뉴를 클릭 하 여 *SolutionName***속성**합니다.  
  
2.  **시그니처** 탭을 클릭합니다.  
  
3.  선택 **ClickOnce 매니페스트 서명**합니다.  
  
4.  클릭 하 여 인증서를 찾은 다음 **저장소에서 선택** 또는 **파일에서 선택** 을 인증서로 이동 합니다.  
  
5.  올바른 인증서가 사용 되 고 있는지 확인 하려면 **자세히** 인증서 정보를 봅니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)   
 [Office 솔루션에 신뢰 부여](../vsto/granting-trust-to-office-solutions.md)   
 [프로젝트 디자이너, 서명 페이지](/visualstudio/ide/reference/signing-page-project-designer)  
  
  