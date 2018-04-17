---
title: System.Deployment.Application을 사용 하는 ClickOnce 응용 프로그램을 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, debugging
- debugging, ClickOnce applications
- debugging, System.Deployment
- deploying applications [ClickOnce], debugging
ms.assetid: 86f31948-2ca8-47c0-8e8b-c2b817bbf79f
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: e637a8abf3255605415067d02fb474503c3de4a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-clickonce-applications-that-use-systemdeploymentapplication"></a>System.Deployment.Application을 사용하는 ClickOnce 응용 프로그램 디버깅
[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 사용 하면 응용 프로그램 업데이트 되는 방식을 구성할 수 있습니다. 그러나 사용 및 사용자 지정 해야 할 경우 고급 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 제공한 배포 개체 모델에 액세스 할 배포 기능을 <xref:System.Deployment.Application>합니다. 사용할 수는 <xref:System.Deployment.Application> 와 같은 고급 작업에 대 한 Api:  
  
-   응용 프로그램에서 "업데이트" 지금 "옵션을 만들기  
  
-   조건부, 다양 한 응용 프로그램 구성 요소에서 요청 시 다운로드  
  
-   응용 프로그램에 직접 통합 업데이트  
  
-   클라이언트 응용 프로그램은 최신 항상 보장  
  
 때문에 <xref:System.Deployment.Application> Api 응용 프로그램으로 배포 되는 경우에 작동 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 기술, 디버깅 하는 유일한 방법은 사용 하 여 응용 프로그램을 배포 하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를에 연결한 다음 디버깅 합니다. 디버거를 연결 하는 하기 어려울 수 있습니다 충분히 이른 시점의이 코드는 응용 프로그램이 시작 되 고 디버거를 연결할 수 전에 실행 하는 경우에 종종 실행 되기 때문입니다. 솔루션 검사 코드를 업데이트 하거나 요청 시 코드 하기 전에 나누기 (또는 Visual Basic 프로젝트에 대 한 중지)를 배치 하는 것입니다.  
  
 권장 되는 디버깅 방법은 다음과 같습니다.  
  
1.  시작 하기 전에 기호 (.pdb) 및 소스 파일은 보관 되어 있는지 확인 합니다.  
  
2.  응용 프로그램의 버전 1을 배포 합니다.  
  
3.  새로운 빈 솔루션을 만듭니다. **파일** 메뉴를 클릭 하 여 **새로**, 다음 **프로젝트**합니다. 에 **새 프로젝트** 열기 대화 상자는 **기타 프로젝트 형식** 노드를 선택 합니다는 **Visual Studio 솔루션** 폴더입니다. 에 **템플릿** 창 선택 **빈 솔루션**합니다.  
  
4.  이 새 솔루션에 대 한 속성에 보관 된 원본 위치를 추가 합니다. **솔루션 탐색기**, 솔루션 노드를 마우스 오른쪽 단추로 클릭 하 여 **속성**합니다. 에 **속성 페이지** 대화 상자에서 **소스 파일 디버그**, 보관된 된 소스 코드의 디렉터리를 추가 합니다. 그렇지 않으면 디버거 원본 파일 경로가.pdb 파일에 기록 되어 이후 만료 된 소스 파일을 찾이 됩니다. 만료 된 소스 파일을 사용 하는 디버거를 하는 경우 소스와 일치 하지 않는 알려 주는 메시지가 표시 됩니다.  
  
5.  디버거에서.pdb 파일을 찾을 수 있는지 확인 합니다. 경우에 응용 프로그램을 배포한 디버거 검색을 자동으로 됩니다. 이 항상 있는 어셈블리에 먼저 찾습니다. 그렇지 않은 경우 보관 파일 경로를 추가 해야 합니다는 **기호 파일 (.pdb) 위치** (에서이 옵션에 액세스 하는 **도구** 메뉴에서 클릭 **옵션**는 엽니다 **디버깅** 노드를 마우스 클릭 **기호**).  
  
6.  디버그 간에 어떤 일이 생기는 `CheckForUpdate` 및 `Download` / `Update` 메서드를 호출 합니다.  
  
     예를 들어 업데이트 코드 다음과 같을 수 있습니다.  
  
    ```  
        Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
            If My.Application.Deployment.IsNetworkDeployed Then  
  
                If (My.Application.Deployment.CheckForUpdate()) Then  
  
                    My.Application.Deployment.Update()  
                    Application.Restart()  
  
                End If  
  
            End If  
        End Sub  
    ```  
  
7.  버전 2를 배포 합니다.  
  
8.  버전 2에 대 한 업데이트를 다운로드할 때 버전 1 응용 프로그램에 디버거를 연결 하려고 시도 합니다. 또는 사용할 수 있습니다는 `System.Diagnostics.Debugger.Break` 메서드 또는 단순히 `Stop` Visual Basic의 합니다. 물론, 프로덕션 코드에서 이러한 메서드 호출을 하지 유지 해야 합니다.  
  
     Windows Forms 응용 프로그램을 개발 하는 중 이며 업데이트 논리가이 메서드에 대 한 이벤트 처리기 것에 있는 예를 들어 가정 합니다. 이 디버깅 하려면 단순히 연결 단추를 누르면 합니다 중단점을 설정 하기 전에 (적절 한 보관 된 파일 열고 여기서 중단점이 설정 되어 있는지 확인).  
  
 사용 하 여는 <xref:System.Deployment.Application.ApplicationDeployment.IsNetworkDeployed%2A> 호출할 속성에는 <xref:System.Deployment.Application> Api는 응용 프로그램을 배포 하는 경우에; Api 호출 되지 않도록에서 디버깅 하는 동안 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Deployment.Application>