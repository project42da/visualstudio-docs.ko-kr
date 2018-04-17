---
title: '방법: SignTool.exe (ClickOnce)를 사용 하 여 파일 하 여 설치 | Microsoft Docs'
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
- ClickOnce applications, signtool.exe
- deploying applications [ClickOnce], re-signing setup.exe
- ClickOnce deployment, signtool.exe
- ClickOnce applications, re-signing setup.exe
- ClickOnce deployment, re-signing setup.exe
ms.assetid: 545a4005-d283-4110-9821-c78a9833c250
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 4be6438f16ddf86afdc8139491d081bcd2fce7a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-sign-setup-files-with-signtoolexe-clickonce"></a>방법: SignTool.exe를 사용하여 설치 파일에 서명(ClickOnce)
SignTool.exe를 사용하여 설치 프로그램(setup.exe)에 서명을 할 수 있습니다. 이 프로세스를 수행하면 최종 사용자 컴퓨터에 훼손된 파일이 설치되지 않습니다.  
  
 ClickOnce는 기본적으로 서명된 매니페스트 및 서명된 설치 프로그램을 포함합니다. 그러나 설치 프로그램의 매개 변수를 나중에 변경하려는 경우 설치 프로그램에 나중에 서명해야 합니다. 설치 프로그램에 서명을 한 후에 매개 변수를 변경하면 서명이 손상됩니다.  
  
 다음 절차에서는 서명되지 않은 매니페스트 및 서명되지 않은 설치 프로그램을 생성합니다. 그런 다음 Visual Studio에서 ClickOnce 서명을 사용하도록 설정하여 서명된 매니페스트를 생성합니다. 고객이 자신의 인증서로 실행 파일에 서명을 할 수 있도록 설치 프로그램은 서명되지 않은 상태로 유지합니다.  
  
### <a name="to-generate-an-unsigned-setup-program-and-sign-later"></a>서명되지 않은 설치 프로그램을 생성하고 나중에 서명을 하려면  
  
1.  매니페스트에 서명하는 데 사용할 인증서를 개발 컴퓨터에 설치합니다.  
  
2.  프로젝트를 선택 **솔루션 탐색기**합니다.  
  
3.  에 **프로젝트** 메뉴를 클릭 하 여 *p r o j* **속성**합니다.  
  
4.  에 **서명** 페이지 지우기 **ClickOnce 매니페스트 서명**합니다.  
  
5.  에 **게시** 페이지 **필수 구성 요소**합니다.  
  
6.  모든 필수 구성 요소를 선택 하 고 클릭 한 다음 확인 **확인**합니다.  
  
7.  에 **게시** 페이지에서 게시 설정을 확인 하 고 클릭 **지금 게시**합니다.  
  
     서명되지 않은 응용 프로그램 매니페스트, 서명되지 않은 배포 매니페스트, 버전별 파일 및 서명되지 않은 설치 프로그램이 게시 폴더 위치에 게시됩니다.  
  
8.  에 **게시** 페이지 **필수 구성 요소**합니다.  
  
9. 에 **필수 구성 요소** 대화 상자, 일반 **필수 구성 요소를 설치 하려면 설치 프로그램 만들기**합니다.  
  
10. 에 **게시** 페이지에서 게시 설정을 확인 하 고 클릭 **지금 게시**합니다.  
  
     서명된 응용 프로그램 매니페스트, 서명된 배포 매니페스트 및 버전별 파일이 게시 폴더 위치에 게시됩니다. 게시 프로세스는 서명되지 않은 설치 프로그램을 덮어쓰지 않습니다.  
  
11. 고객 사이트에서 명령 프롬프트를 엽니다.  
  
12. .exe 파일이 포함된 디렉터리로 변경합니다.  
  
13. 다음 명령을 사용하여 .exe 파일에 서명을 합니다.  
  
    ```  
    signtool sign /sha1 CertificateHash Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
     예를 들어 설치 프로그램에 서명하려면 다음 명령 중 하나를 사용합니다.  
  
    ```  
    signtool sign /sha1 CCB... Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [방법: 응용 프로그램 및 배포 매니페스트에 다시 서명](../deployment/how-to-re-sign-application-and-deployment-manifests.md)