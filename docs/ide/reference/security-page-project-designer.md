---
title: "프로젝트 디자이너, 보안 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ProjectPropertiesSecurity"
  - "vb.XBAPProjectPropertiesSecurity"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "프로젝트 디자이너, 보안 페이지"
  - "프로젝트 디자이너의 보안 페이지"
ms.assetid: 641d9cd3-fa07-498a-8568-3c169bb4d3d5
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 34
---
# 프로젝트 디자이너, 보안 페이지
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**프로젝트 디자이너**의 **보안** 페이지는 [!INCLUDE[ndptecclick](../../deployment/includes/ndptecclick_md.md)] 배포를 사용하여 배포되는 응용 프로그램의 코드 액세스 보안 설정을 구성하는 데 사용됩니다.  자세한 내용은 [ClickOnce 응용 프로그램의 코드 액세스 보안](../../deployment/code-access-security-for-clickonce-applications.md)을 참조하십시오.  
  
 **보안** 페이지에 액세스하려면 **솔루션 탐색기**에서 프로젝트 노드를 클릭한 다음 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  **프로젝트 디자이너**가 나타나면 **보안** 탭을 클릭합니다.  
  
## 보안 설정  
 **ClickOnce 보안 설정 사용**  
 디자인 타임에 보안 설정을 사용할지 여부를 결정합니다.  이 옵션의 선택을 취소하면 **보안** 페이지의 다른 옵션을 모두 사용할 수 없습니다.  
  
> [!NOTE]
>  **게시** 마법사를 통해 응용 프로그램을 게시하는 경우에는 이 옵션이 자동으로 활성화됩니다.  
  
 이 옵션을 선택하면 **완전 신뢰 응용 프로그램** 또는 **부분 신뢰 응용 프로그램** 라디오 단추 중 하나를 선택할 수 있습니다.  
  
 이 옵션은 기본적으로 WPF 웹 브라우저 응용 프로그램 프로젝트에 대해 선택됩니다.  
  
 다른 모든 프로젝트 유형에 대해서는 이 옵션의 선택이 취소됩니다.  
  
 **완전 신뢰 응용 프로그램**  
 이 옵션을 선택하면 응용 프로그램은 클라이언트 컴퓨터에서 설치되거나 실행될 때 완전 신뢰 권한을 요청합니다.  응용 프로그램이 파일 시스템과 레지스트리 등의 리소스에 무제한으로 액세스할 수 있는 권한을 받게 되므로 가능하면 이 옵션을 사용하지 않아야 합니다.  
  
 이 옵션은 기본적으로 WPF 웹 브라우저 응용 프로그램 프로젝트에 대해 부분 신뢰로 설정됩니다.  
  
 다른 모든 프로젝트 유형에 대해서는 완전 신뢰로 설정됩니다.  
  
 **부분 신뢰 응용 프로그램**  
 이 옵션을 선택하면 응용 프로그램은 클라이언트 컴퓨터에서 설치되거나 실행될 때 부분 신뢰 권한을 요청합니다.  *부분 신뢰*에서는 요청한 코드 액세스 보안 권한이 허용된 작업만 실행됩니다.  보안 권한을 구성하는 방법에 대한 자세한 내용은 [ClickOnce 응용 프로그램의 코드 액세스 보안](../../deployment/code-access-security-for-clickonce-applications.md)을 참조하십시오.  
  
 **ClickOnce 보안 권한** 영역의 옵션을 구성하여 부분 신뢰 보안 설정을 지정할 수 있습니다.  
  
## ClickOnce 보안 권한  
 **설치할 응용 프로그램을 가져올 영역**  
 코드 액세스 보안 권한의 기본 집합을 지정합니다.  제한된 권한 집합의 경우에는 **인터넷** 또는 **로컬 인트라넷**을 선택하거나 사용자 지정 권한 집합을 구성하려면 **\(사용자 지정\)**을 선택합니다.  응용 프로그램이 영역에 부여된 것보다 많은 권한을 요청하는 경우 최종 사용자에 대한 ClickOnce 신뢰 프롬프트가 나타나 추가 권한을 부여합니다.  보안 권한을 구성하는 방법에 대한 자세한 내용은 [ClickOnce 응용 프로그램의 코드 액세스 보안](../../deployment/code-access-security-for-clickonce-applications.md)을 참조하십시오.  
  
 이 옵션은 기본적으로 WPF 웹 브라우저 응용 프로그램 프로젝트에 대해 **인터넷**으로 설정됩니다.  
  
 **권한 편집 XML**  
 응용 프로그램 매니페스트 템플릿\(app.manifest\)을 열어 **\(사용자 지정\)** 권한 집합에 대한 권한을 구성합니다.  
  
 **고급**  
 제한된 권한이 있는 응용 프로그램 디버깅에 대한 설정을 구성하는 데 사용되는 [고급 보안 설정 대화 상자](../../ide/reference/advanced-security-settings-dialog-box.md)를 엽니다.  이러한 설정은 디버깅하는 동안 확인되고 권한 예외는 응용 프로그램이 영역에 정의된 것보다 더 많은 권한이 필요할 수도 있음을 나타냅니다.  
  
## 참고 항목  
 <xref:System.Security.Permissions.WebBrowserPermission>   
 <xref:System.Security.Permissions.MediaPermission>   
 [ClickOnce 응용 프로그램의 코드 액세스 보안](../../deployment/code-access-security-for-clickonce-applications.md)   
 [방법: ClickOnce 보안 설정 사용](../../deployment/how-to-enable-clickonce-security-settings.md)   
 [방법: ClickOnce 응용 프로그램의 보안 영역 설정](../../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램에 대한 사용자 지정 권한 설정](../../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [방법: 제한된 권한으로 ClickOnce 응용 프로그램 디버깅](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [ClickOnce 보안 및 배포](../../deployment/clickonce-security-and-deployment.md)   
 [프로젝트 속성 참조](../../ide/reference/project-properties-reference.md)   
 [고급 보안 설정 대화 상자](../../ide/reference/advanced-security-settings-dialog-box.md)